# E-mail Protocol Support
Hornbill is designed to interoperate with public and enterprise class e-mail systems and supports the following well understood, industry-strength network protocols for the transmission and reception of open standards based e-mail messages. All documented standards with their respective encryption and security features are supported.

## Supported E-Mail Protocols Matrix
| | Plain Text | SSL | TLS | Notes  |
|---|---|---|---|---|
| **POP3** | 110 |   |   | Defined in RFC 1939  |
| **POP3** |   |   | 110 | Defined in RFC 2595  |
| **POP3** |   | 995 |   | Full description is “pop3 protocol over TLS/SSL (was spop3)  |
| **IMAP4** | 143 |   |   | IMAP Version 4 as defined in RFC 2060  |
| **IMAP4** |   | 993 |   | Full description is “imap4 protocol over TLS/SSL”. Use this port instead of the now depreciated TCP port 585 “imap4-ssl”.  |
| **IMAP4** |   |   | 143 | Using TLS explicit STARTTLS with IMAP Version 4 as defined in RFC 2595  |
| **SMTP** | 25 |   |   | Incoming SMTP mail, generally the mail server will not route mail outside of the internal mail network so the mail server can not be used as a spam distributor.  This is generally were most mail-related security restrictions are placed for incoming mail.  |
| **SMTP** |   | 465 |   | The use of this port has become a typical port for accepting incoming mail over SSL. Port 465 for SMTPS shows up in Appendix A of the 1996 "SSL Protocol Version 3.0" draft-standard published by Netscape hereThe SSL Protocol Version 3.0. Unfortunately, the use of this port never became a standard, the port is not registered with the IANA for SMTPS, it’s instead registered for URD – “URL Rendezvous Directory for SSM” by Cisco. So while port 465 may be used in some places the recommended approach is to use TLS encryption (STARTTLS) on submission port 587 or standard port 25 instead.  |
| **SMTP** |   | 587 |   | RFC 2476 Message Submission. Used by mail users authenticated in the mail server you are connecting to in order to send outbound mail. In other words, the mail server will act as a router and send mail on behalf of the user. It will also place sent mail into the "sent-items" folder of the authenticated users mailbox. This is defined in RFC 2476  |
| **SMTP** |   |   | 25 | Incoming SMTP mail but with the option to negotiate a secure SMTP channel using the STARTTLS command in order that the data is encrypted. Standard defined in RFC 3207 |

:::tip
As a general rule, there is better support for the TLS encryption schemes than there are for XXXoverSSL variants. The use of the standards plain ports with an encryption negotiate is compatible with more systems and networks generally. However, some older mail servers, or services that use another tool such as stunnel or ssh only support XXXoverSSL.
:::

## Verified Mail Server Compatibility
The following matrix shows the verified connectivity options for a number of different mail servers. Verified means we test for this as part of our automated confidence and regression testing scheme.

|| Exchange Server 2007 | Exchange Server 2010 | Postfix+Dovecot (Linux x86) | Google Mail | Yahoo! Mail | Office365.com  |
|---|---|---|---|---|---|---|
| **POP3-Plain** | Yes | Yes | Yes | No | No | No  |
| **POP3-SSL** | Yes | Yes | Yes | Yes | Yes | Yes  |
| **POP3-TLS** | Yes | Yes | Yes | No | No | Yes  |
| **IMAP4-Plain** | Yes | Yes | Yes | No | No | No  |
| **IMAP4-SSL** | Yes | Yes | Yes | Yes | Yes | Yes  |
| **IMAP4-TLS** | Yes | Yes | Yes | Yes | Yes | Yes  |
| **SMTP-Plain** | Yes | Yes | Yes | Yes | Yes | Yes  |
| **SMTP-SSL** <sup>1</sup> | No <sup>2</sup> | No <sup>2</sup> | No | Yes | No | No |
| **SMTP-SUBMISSION-TLS** | Yes | Yes | Yes | Yes | Yes | Yes  |
| **SMTP-SUBMISSION-SSL** | No <sup>2</sup>  | No <sup>2</sup>  | No | Yes | No | No |
| **SMTP-TLS** | Yes | Yes | Yes | Yes | Yes | Yes |

Notes:
1. SMTP over SSL (or SMTPS) typically listening on port 465 is not supported by most systems. This was a standard-to-be that never made it. Explicit SSL implementations (using STARTTLS) took over as the standard.
2. It is NOT possible get Exchange Server to listen for SMTP on port 465 with SSL encryption.

    Microsoft Exchange does not support SMTP over SSL (SMTPS). It is possible to make any SMTP virtual server or receive connector listen on port 465, but that will not achieve the goal of secure SMTP (SMTPS) because SSL is not supported. Why is this? There are two types of SSL used on the standard internet mail protocols: "explicit" and "implicit". Initially, most of the SSL implementations were implicit, meaning that a dedicated port for SSL was used and an SSL negotiation had to take place before communications could begin. As a well known example, consider HTTP, which is on port 80 by default, but HTTPS (HTTP over SSL) is on port 443.

    Several years ago, the Internet community decided that a dedicated port should not be required for SSL because it made systems more complicated. Instead a new standard was devised based on the idea of explicit SSL. Unlike implicit SSL, explicit SSL is negotiated by the specific protocol after the plain text connection is made, most commonly using the STARTTLS command.

    Netscape had already chosen 465 as the SMTPS port, but Exchange Server had no SSL functionality in its SMTP implementation. By the time the Exchange team added SSL support it was obvious that explicit SSL was a better solution than implicit SSL. Most other SMTP server and client vendors have implemented the STARTTLS command as well, so there never was much need to support port 465, which wasn't an official Internet standard anyway. To this day, no version of Exchange Server supports implicit SSL for SMTP. Telling an Exchange Receive connector or SMTP virtual server to listen on port 465 does not change this fact. Therefore, you need to use a client that supports STARTTLS on port 25. If you can't use port 25, the next logical choice is 587, which is the standard port for client SMTP submissions. There aren't many modern clients that don't support STARTTLS on 25, so adding support for implicit SSL has not been necessary. It should be noted that MS Exchange POP3 and IMAP4 implementations have always supported implicit SSL but as of Exchange Server 2007, there is now full support for explicit SSL for these two protocols as well.
    Information sourced from http://technet.microsoft.com/en-us/magazine/2007.11.exchangeqa.aspx

<!-- 3. The systems that are known to work have been tested but are not included for automated testing either because its not practical to have the system in our test environment or because the system is external to our test environment and can not be guaranteed to be available and/or accessible when our tests are run. -->

<!-- https://wiki.hornbill.com/index.php?title=E-Mail_Protocol_Support -->