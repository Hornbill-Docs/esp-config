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
* Hornbill Admin User access
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration)
* A fully qualified domain name for outgoing email
* A working knowledge of your mail servers and firewalls within your own organization

## Creating an email domain
To create and configure a new email domain in Configuration 

1. Search [Configuration](/esp-config/getting-started/using-configuration) for Email Domain
1. In the results, select Email Domain
1. Click on the `+ Add Outbound Route` button.

### Details
* **Domain Name**<br>
The name that is used here must be a valid domain name. For example 'mycompany.com'
* **Enable processing incoming mail on this route**<br>
Turning this on will allow any email that has been sent to this domain to be processed by the SMTP service and allow it to be routed to the appropriate mailbox.
* **Automatically create address for this route when a new mailbox is created**<br>
When a new user is created a personal mailbox is created and associated with that user. When this feature is enabled, each new user will be automatically allocated an email address using this domain name. The Address Format can then be used to set the format of the username.
* **Address Format**<br>
The Address Format is to be used when a new personal mailbox is created. This is only available if you have enabled the option above to automatically create addresses for this route. The formats that can be selected are based on variations of the Firstname and Lastname of the user with the exception of the LoginID.

### Enable DKIM
DomainKeys Identified Mail (DKIM) is an email authentication method designed to make sure messages aren't altered in transit between the sending and recipient servers and to detect forged sender addresses in email (email spoofing), a technique often used in phishing and email spam.
* **DKIM Selector**<br>
A DKIM selector is specified when the private/public key pair is created when DKIM is set up for the email domain (or email sender), and it can be any arbitrary string of text
* **DKIM Key Size**<br>
Choose between 1024 and 2048 bits for your key size.

::: note
Once the domain has been saved, you will be presented with a DKIM Key
:::

## Outbound Routing Mode
There are two methods of outbound routing available in Hornbill.  Select the one that is most desirable to you based on the descriptions below.

### Option 1: DNS Routing
If you wish to use DNS Routing, this requires the following steps.

1. Add an SPF and TXT record to your DNS server
1. Validating the record using the `Test SPF` button 
1. After a successful test, click on the `Create Route` button 

When an email is delivered, our servers will automatically negotiate the highest level of transport encryption supported by the remote SMTP server. This is completely automatic and is negotiated each and every time a new SMTP connection is made. We support the TLS 1.2, TLS 1.1, TLS 1.0, SSL 3.0, and Plain Text protocols, prioritized and negotiated for in that order.  The SPF/TXT record allows Hornbill to send emails using the configured domain without the risk of breaching any anti-spam/email source validation checks.

::: note
If the domain name is set to live.hornbill.com, a SPF/TXT Record is not required.
:::

### Option 2: SMTP SmartHost
A smart host is a type of email message transfer agent that allows a Simple Mail Transfer Protocol (SMTP) server to route email via an intermediate e-mail server rather than directly to the recipient's server. With this method, an e-mail server within your organization is configured to allow the relaying of emails from your Hornbill instance (based in our data center) to your end users. With the relay configured, any outbound email will pass through your domain, and therefore, from the recipient's perspective, the source domain will correspond to that used in the "from address" that we configure within Hornbill.

To successfully complete the Email integration using this method you will need to:

1. Create an outbound route in Hornbill and configure the necessary details.
1. Configure a relay connector on your mail server (allowing relay from the appropriate origin IP stated below)
1. Configure any necessary firewall rules (allowing traffic from the appropriate origin IP) to allow communication from your Hornbill instance.

::: note
If you are not familiar with how to complete steps 2 and 3, please refer to the relevant vendor-specific documentation for your mail server and firewall interfaces.
:::

#### Firewall - Origin IP Address
The origin IP that should be specified in any such firewall rules is one of the following and is dependent on the location of your instance. You should have both the Primary and Secondary IP for your geographical area:

* **Europe**<br>`87.117.243.10` or `212.71.225.67`<br>If you are a UK or European customer, your instance will be located in our European data center and any outbound mail will originate from these IP addresses.
* **North America**<br>`69.174.249.200` or `64.34.188.200`<br>If you are a North American customer, your instance will be located in our North American data center and any outbound mail will originate from these IP addresses.

::: note
You will find a default domain entry (live.hornbill.com) comes already configured with your instance which allows you to test aspects of the Hornbill applications while you are organizing the email configuration required in your infrastructure.
:::