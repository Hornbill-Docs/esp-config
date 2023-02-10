---
layout: article-toc
---
# Adding an email domain
Creating and configuring an email domain is a required part of providing email functionality within some of the Hornbill applications. The domain is primarily concerned with facilitating the outbound mail operation, delivering from the Hornbill instance to the outside world. 

## Topics covered
* Creating a new email domain
* Enabling DKIM
* Choosing a routing mode
* Performing an SPF test

## Before you begin
This guide takes you through administrative configurations.  The following will be needed to complete this guide:
* Admin User access
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration)
* A valid domain name

## Creating and managing your email domain
To create and configure a new email domain in Hornbill Configuration 

1. Search [Configuration](/esp-config/getting-started/using-configuration) for Email Domain
1. In the results, select Email Domain
1. Click on the `+ Add Outbound Route` button.

* **Domain Name** - The name that is used here must be a valid domain name. For example 'mycompany.com'
* **Enable processing incoming mail on this route** - Turning this on will allow any email that has been sent to this domain to be processed by the SMTP service and allow it to be routed to the appropriate mailbox.
* **Automatically Create Address for this route when a new mailbox is created** - When a new user is created a personal mailbox is created and associated with that user. When this feature is enabled, each new user will be automatically allocated an email address using this domain name. The Address Format can then be used to set the format of the username.
* **Address Format** - The Address Format to be used when a new personal mailbox is created. This is only available if you have enabled the option above to automatically create addresses for this route. The formats that can be selected are based on variations of the Firstname and Lastname of the user with the exception of the LoginID.
## Enable DKIM
DomainKeys Identified Mail (DKIM) is an email authentication method designed to make sure messages aren't altered in transit between the sending and recipient servers and to detect forged sender addresses in email (email spoofing), a technique often used in phishing and email spam.
### DKIM Selector
A DKIM selector is specified when the private/public key pair is created when DKIM is set up for the email domain (or email sender), and it can be any arbitrary string of text
### DKIM Key Size
Choose between 1024 and 2048 bits for your key size.

::: note
Once the Email Domain has been saved, you will be presented with a DKIM Key
:::

## Outbound Routing Mode
There are two methods of outbound routing available in Hornbill, Use DNS Routing and Use SMTP Smart Host. Select the one that is most desirable to you based on the descriptions below.

Outbound Routing Modes
Now that you have familiarised yourself with where and how Outbound Routing is configured in Hornbill Administration, the next step is to understand which Outbound Routing mode is most suitable for your organisation. The available modes are described below and the decision essentially comes down to what's dictated by your internal IT policies. If your policies don't limit your choice then it's simply what you prefer when it comes to maintaining this integration going forward.

### Option 1: Direct Outbound
If you wish to use the Direct Outbound method, this quite simply involves the addition of an SPF and TXT record to your DNS server, validating the record using the SPF Check button within the Hornbill Administration UI, and saving the configuration upon success. Please see the section below relating to the SPF/TXT record for more information.

When email is delivered using the Direct Outbound method, our servers will automatically negotiate the highest level of transport encryption supported by the remote SMTP server. This is completely automatic and is negotiated each and every time a new SMTP connection is made. We support the TLS 1.2, TLS 1.1, TLS 1.0, SSL 3.0 and Plain Text protocols, prioritised and negotiated for in that order
SPF/TXT Record
If you wish to configure “Use Direct Outbound” and the domain name used in the email from address is not live.hornbill.com, a SPF/TXT Record must be configured. The SPF/TXT record allows Hornbill to send email using the configured domain without risk of breaching any anti-spam/email source validation checks.

It is recommended that this is configured by a system admin to add this record to your DNS.


### Option 2: SMTP SmartHost
A smart host is a type of email message transfer agent that allows a Simple Mail Transfer Protocol (SMTP) server to route email via an intermediate mailserver rather than directly to the recipient's server. With this method, a mailserver within your organisation is configured to allow the relaying of emails from your Hornbill instance (based in our data centre) to your end users. With the relay configured, any outbound email will pass through your domain and therefore, from the recipients perspective, the source domain will correspond to that used in the "from address" that we configure within Hornbill.

To successfully complete the Email integration using this method you will need to:

1. Create an outbound route in Hornbill and configure the necessary details (as shown in the image below).
1. Configure a relay connector on your mail server (allowing relay from the appropriate origin IP stated below)
1. Configure any necessary firewall rules (allowing traffic from the appropriate origin IP) to allow communication from your Hornbill instance.

::: note
If you are not familiar with how to complete steps 2 and 3, please refer to the relevant vendor-specific documentation for your mail server and firewall interfaces.
:::

Origin IP Address
The origin IP that should be specified in any such firewall rules is one of the following and is dependent on the location of your instance. You should have both the Primary and Secondary IP for your geographical area:

Europe: - 87.117.243.10 OR 212.71.225.67 (If you are a UK or European customer, your instance will be located in our European data centre and any outbound mail will originate from here)
North America: - 69.174.249.200 OR 64.34.188.200 (If you are a North American or Canadian customer, your instance will be located in our North American data centre and any outbound mail will originate from here)
(More information about our data centres can be found in our FAQ: Hornbill Data Centres. If you are unable to find the answer you're looking for, please head over to the Hornbill forums and start a discussion).

The origin IP addresses are also contained in the "Email Integration Information" communication sent from your Product Specialist at the beginning of the Switch On.

Smart Host Details:
The information you will need to have to hand when specifying your SMART Host is indicated below:
SMART Host Configuration Form

::: note
Although we have expertise around our own platform and its email routing implementation, configuration, and behaviour, we use the language associated with the POP3, IMAP4, and SMTP standards and not the specific language and/or terminology of any specific vendors' mail server interfaces or platforms.
This means Hornbill's technical staff are not experts with the various mail server and firewall interfaces in use. Each organisations mail routing implementation can be unique to their organisation and it will be necessary for you to have someone internally with expertise and a working knowledge of your mail servers and firewalls within your own organisation. You should refer your technical email/network expert to this document which should provide them with sufficient information to allow the planning and configuration of email integration for your organisation.
:::

::: note
You will find a default domain entry (live.hornbill.com) comes already configured with your instance which allows you to test aspects of the Hornbill applications while you are organizing the email configuration required in your infrastructure.
:::