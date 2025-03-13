---
layout: article-toc
---
# Email domains
Creating and configuring an email domain is a required part of providing email functionality within some of the Hornbill applications. The domain is primarily concerned with facilitating the outbound mail operation, delivering email from the Hornbill instance to the outside world. 

## Topics covered
* Creating a new email domain.
* Enabling DKIM.
* Choosing a routing mode.
* Performing an SPF test.

## Before you begin
This article takes you through administrative configurations. In order to create and configure an email domain, you need:
* the Hornbill Admin (User) role.
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration).
* A fully qualified domain name for outgoing email.
* A working knowledge of the mail servers and firewalls within your organization.

## Creating an email domain
**To create and configure a new email domain in Configuration:** 

1. Search [Configuration](/esp-config/getting-started/using-configuration) for *email domain*.
1. In the results, select Email Domains.
1. Click **+ Add Outbound Route**.
1. Configure the outbound mail route using the information that follows.
1. (Optional) To enable DomainKeys Identified Mail, see [Enabling DKIM](/esp-config/email/email-domains#enabling-dkim).
1. There are two methods of outbound routing available in Hornbill. Choose either [DNS routing](/esp-config/email/email-domains#option-1-dns-routing) or [SMTP smart host](/esp-config/email/email-domains#option-2-smtp-smart-host).

### Details
* **Domain Name.** This must be a valid domain name. For example, mycompany.com.
* **Enable processing of incoming mail on this route.** When this is ON, any email that has been sent to this domain is allowed to be processed by the SMTP service and routed to the appropriate mailbox.
* **Automatically create an address for this route when a new mailbox is created.** When a new user is created, a personal mailbox is created and associated with that user. When this is ON, each new user will be automatically allocated an email address using this domain name. The Address Format dropdown can then be used to set the format of the username.
* **Address Format.** This is used when a new personal mailbox is created. This is only available if you have enabled the option above to automatically create addresses for this route. The formats that can be selected are based on variations of the Firstname and Lastname of the user, with the exception of the LoginID.

## Enabling DKIM
DomainKeys Identified Mail (DKIM) is an email authentication method designed to make sure messages aren't altered in transit between the sending and recipient servers and to detect forged sender addresses in email (email spoofing), a technique often used in phishing and email spam.
* **DKIM Selector.** When you enable DKIM, you must specify a DKIM selector to identify the specific private/public key pair for the email domain (or email sender). It can be any arbitrary string of text.
* **DKIM Key Size.** Choose between 1024 and 2048 bits.

::: note
Once the domain has been saved, you will be presented with a DKIM key.
:::

## Outbound routing mode
There are two methods of outbound routing available in Hornbill.  Make your choice based on the descriptions below.

### Option 1: DNS Routing
**To use DNS routing:**
1. Add an SPF and TXT record to your DNS server.
1. Validate the record by clicking **Test SPF**.
1. After a successful test, click on **Create Route**.

:::tip
If your domain name is set to **live.hornbill.com** an SPF/TXT record is not required.
:::

#### SPF/TXT record
The SPF/TXT record allows Hornbill to send emails using the configured domain without the risk of breaching any anti-spam/email source-validation checks. An SPF/TXT record must be configured by someone in your organization that manages your DNS records.

The following record is to be added: 
> include:_spf.hornbill.com

An example SPF/TXT record would be: 
> v=spf1 include:_spf.hornbill.com ~all

On all outbound email for this domain, Hornbill checks that the SPF/TXT record has the  '''include:_spf.hornbill.com''' section set. If not, the mail will refuse to send. This check is put in place to ensure Hornbill is allowed to send email as the given domain and to prevent abuse such as someone sending email pretending to be from a domain they do not own.

:::note
SPF and TXT are types of DNS records that should be set. Although SPF has been officially deprecated, it still may be used; so it is a good idea to set it. The main record that needs to be added is the TXT version.
:::

<!--
To confirm that the include has been added to a TXT/SPF record it is possible to check using this 3rd party website http://mxtoolbox.com/SuperTool.aspx?action=spf (Hornbill takes no responsibility for 3rd party websites).
-->

#### Encryption
When an email is delivered, our servers will automatically negotiate the highest level of transport encryption supported by the remote SMTP server. This is completely automatic and is negotiated every time a new SMTP connection is made. We support the TLS 1.2, TLS 1.1, TLS 1.0, SSL 3.0, and Plain Text protocols, prioritized and negotiated for in that order.  

### Option 2: SMTP smart host
A smart host is a type of email message transfer agent that allows a Simple Mail Transfer Protocol (SMTP) server to route email via an intermediate email server rather than directly to the recipient's server. With this method, an email server within your organization is configured to allow the relaying of emails from your Hornbill instance (based in our data center) to your end users. With the relay configured, any outbound email will pass through your domain, and therefore, from the recipient's perspective, the source domain will correspond to that used in the From address that we configure within Hornbill.

**To complete the email integration using this method:**
1. Create an outbound route in Hornbill and configure the necessary details.
1. Configure a relay connector on your mail server (allowing relay from the appropriate origin IP stated below).
1. Configure any necessary firewall rules (allowing traffic from the appropriate origin IP) to allow communication from your Hornbill instance.

::: note
If you are not familiar with how to complete Steps 2 and 3, see the relevant vendor-specific documentation for your mail server and firewall interfaces.
:::

#### Firewall - origin IP address
The origin IP that should be specified in any such firewall rules is one of the following and is dependent on the location of your instance. You should have both the primary and secondary IP for your geographical area:

* **Europe.** `87.117.243.10` or `212.71.225.67`<br>If you are a UK or European customer, your instance will be located in our European data center and any outbound mail will originate from these IP addresses.
* **North America.** `69.174.249.200` or `64.34.188.200`<br>If you are a North American customer, your instance will be located in our North American data center and any outbound mail will originate from these IP addresses.

::: note
You will find a default domain entry (live.hornbill.com) comes already configured with your instance which allows you to test aspects of the Hornbill applications while you are organizing the email configuration required in your infrastructure.
:::

## Sending email from a custom domain
Because Hornbill is a cloud solution, when sending emails from your Hornbill instance, you may want to send those emails from your corporate domain rather than a .hornbill.com sub-domain. 

There are two configuration possibilities to achieve that:
* [SPF standard](/esp-config/email/email-domains#using-the-sender-policy-framework-spf-standard)
* [SMTP smart host](/esp-config/email/email-domains#using-smtp-smart-host)

### Using the Sender Policy Framework (SPF) standard
This is the most straightforward scheme to implement. Simply add your domain to the Hornbill instance and ensure that your DNS includes a directive in your SPF policy to tell external mail servers that you are authorizing mail messages coming from our servers to be from someone@yourdomain.com. Because of automated SPF checks done by our servers during configuration, you can set this up without assistance from Hornbill.

For further information, see:
* http://www.ietf.org/rfc/rfc4408.txt
* http://www.open-spf.org/FAQ

### Using SMTP smart host
Instead of our servers taking care of mail routing, we can simply route all outbound emails for your specified domain to an SMTP-relaying server of your choice. Typically, this is your own enterprise SMTP server, which you must provide us access to (generally by creating special firewall rules to enable our servers to connect).

## FCrDNS
This is known as Forward-Confirmed reverse DNS (FCrDNS). This means that the hostname's A record must match the reverse DNS (PTR) record for the IP (and vice versa). This was a historic attempt to ensure that the sender owned the domain and the DNS record. In reality, it never really worked once cloud services or multi-tenant systems became a reality with multiple SMTP servers serving many customers and having resilience. It was dropped by all but two lists years ago.

Therefore, as with many other cloud vendors, we are advising our customers and their email recipients to avoid using any blacklist that implements FCrDNS. If this is not possible, our advice is to configure Hornbill to use your own smart host rather than the live.hornbill.com-provided smart host.
