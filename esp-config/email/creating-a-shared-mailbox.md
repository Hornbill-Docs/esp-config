---
layout: article-toc
---
# Creating a shared mailbox
Shared mailboxes are created to allow a group of users to share a single mailbox for both outgoing and incoming email, all using a common email address. All messages that are sent from, or received by your Hornbill instance will reside within a mailbox.

:::note
The first two shared mailboxes are free, but any more mailboxes are subject to an additional monthly subscription charge.
:::


Correct the Inbound Service details provided:
Service: POP3
Server: 78.129.173.121
Encryption: TLS
Port: 110
Authentication: Classic
Username: support-<instancename>@live.hornbill.com
Password: Cloud to provide in email

Add the email address to shared mailbox and make default
Change Outbound Domain to SPF
Create a new role for the mail account and associate it to key users


Your new Hornbill instance is equipped with a default mailbox (helpdesk), the configuration of which can be amended or alternatively you can create an entirely new Shared Mailbox, the choice is yours.
Shared Mailboxes are located in Hornbill Administration > Home > System > Email > Shared Mailboxes.


Configuring a Shared Mailbox
Once a Shared Mailbox has been created, it will be necessary to work through a number of tabs and complete some further configuration:

Mailbox Details
This is where the basic details of the mailbox are specified:

Mailbox Name: This is used to reference the mailbox within the Hornbill Platform when there is a need to specify a mailbox in certain application settings. Once the mailbox is created this cannot be changed.
Display Name: This is what the recipients of email will see when they receive an email from Hornbill. This can be edited at any time.
Adding an Inbound Mail Service
This tab is where we tell Hornbill where it will retrieve email messages. Remember, in a typical setup, email messages are not sent directly to your Hornbill instance but are retrieved periodically from a mail account that will reside on your organizations mail exchange. The information Hornbill needs is as follows:

Service: the industry standard Protocol that Hornbill will use to retrieve the messages. Hornbill Supports POP3 or IMAP4.
Server: the name or IP address of the mail server where the mail account is located.
Encryption: the encryption method used in the communication between Hornbill and your mail server.
Port: the port over which communication will take place. this will be dictated by the encryption method and Protocol used.
Username:the mail account username.
Password: the mail account password.

PLEASE NOTE: As soon as a successful connection is established to the desired mailbox on your mail server, Hornbill will immediately retrieve any mail that resides in the Inbox, and as per the protocols, will delete any messages from the server once it has downloaded them to Hornbill. If you have any need for the messages to remain on the exchange server, you should ask your mail administrator to implement some rules that duplicates any messages sent to this mail account to another folder/location.

The connection to any existing live mail account should be planned to take place at the end of the Switch On to avoid any competition for email between existing service desk applications and Hornbill Service Manager. For the purposes of testing inbound mail functionality, we advise setting up a temporary mail account on your existing mail server that Hornbill can connect to.

Linking an Outbound Mail Route (Domain)
The "Addresses" tab is where we specify a "reply address" i.e. the address that recipients will see when the receive email from Hornbill. This reply address also has another important function within the Hornbill Platform which is to link the outbound mail route to the Shared Mailbox. Prior to performing this step, it will be necessary to configure your Outbound Mail Route, click here here for details.
Click "Add Address"
Specify the alias (this is what forms everything to the left of the '@' symbol in your reply address).
From the pick list select the domain name. This pick list contacts all the Outbound Routes (Domains) you have configured in Hornbill (See the wiki page on Outbound Mail Routing for more detail).
Click "Save"
Mark the check box to the left of the Address, and set this as the default by clicking the "tick" button towards the top right.
A green dot should now appear to the right of the address to indicate that this is the default address.
Mailbox Status
The "Status" tab shows provides an overview of the mailbox folders.

Associated Roles
This tab shows which Security Roles give access to this particular Shared Mailbox.


Technical Information
E-Mail Protocol Support
Frequently Asked Questions
Which protocol should I use, IMAP4 or POP3?
When Hornbill integrates with your enterprise or public e-mail system for shared mailboxes we only use your mail server to transport mail. Once we read a mail message from your server and move it safely into our database we delete the message on the remote server so in this context both POP3 and IMAP4 do the exact same job. That being said we would recommend that if your server supports it you use IMAP4 simply because its a more modern and more flexible protocol that allows us amongst other things to get instant mail notifications instead of polling for mail (which is the only option we have with POP3).
Why does Hornbill delete mail from my mail server?
Hornbill stores all emails it receives into its shared mailboxes into a database, once your mail messages and attachments are in our database they are as safe as the rest of your data on our platform. One of the problems with IMAP and POP3 with the mail systems that implement these protocols is there is generally a finite amount of storage available for mail, so the question about how to keep storage use at manageable levels becomes a complication and an administrative overhead, and to combat this, many systems impose storage limits and forced message deletion policies. Another good reason is the technical details of how the IMAP and POP3 protocols are implemented. As data sets become large on your mail system, it takes more and more time and network bandwidth to synchronize between Hornbill and your Mail system. For these reasons it works a lot better and is the maintenance free option to move the messages from your mail server to our platform.