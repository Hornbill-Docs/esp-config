---
layout: article-toc
keywords: custom role, user-created role
---
# Shared mailboxes
Email in Hornbill is received by and sent from shared mailboxes. Shared mailboxes  allow a group of users to share a single mailbox for both outgoing and incoming emails, all using a common email address.

:::note
Your first two shared mailboxes are included with every Hornbill instance. Additional mailboxes are subject to an additional monthly subscription charge.
:::

## Topics covered
* [Before you begin](/esp-config/email/shared-mailboxes#before-you-begin)
* [Details](/esp-config/email/shared-mailboxes#details)
* [Inbound Mail Service](/esp-config/email/shared-mailboxes#inbound-mail-service)
* [Addresses](/esp-config/email/shared-mailboxes#addresses)
* [Status](/esp-config/email/shared-mailboxes#status)
* [Associated Roles](/esp-config/email/shared-mailboxes#associated-roles)
* [FAQs](/esp-config/email/shared-mailboxes#faqs)


## Before you begin
* **Have you configured a domain for your new shared mailbox?** Prior to [linking an outbound mail route](/esp-config/email/shared-mailboxes#addresses), you must have already [configured your outbound mail route](/esp-config/email/email-domains).
    * Prior to configuring your outbound mail route, you must have a domain in place. Creating a new mailbox in Hornbill creates the ability to send and receive email in a shared mailbox, but it does not create a new domain for you. 
* **Do you have a user-created role available for this shared mailbox?** You must have at least one user-created role available so that you can [associate a role to the mailbox](/esp-config/email/shared-mailboxes#associated-roles). A user-created role (also known as a custom role) is what gives users access to a shared mailbox. To learn more, see [User-created roles](/esp-config/organizational-data/roles#user-created-roles).

## Details
This tab is where the basic details of the mailbox are specified:

* **Mailbox Name.** This is used to reference the mailbox within the Hornbill Platform when there is a need to specify a mailbox in certain application settings. Once the mailbox is created, this name cannot be changed.
* **Display Name.** This is what the recipients of the email will see when they receive an email from Hornbill. This can be edited at any time.

## Inbound Mail Service
In this tab, you tell Hornbill where it will retrieve email messages. Remember, in a typical setup, email messages are not sent directly to your Hornbill instance; rather, they are retrieved periodically from a mail account that  resides on your organization's mail exchange. The information Hornbill needs is as follows:

* **Service.** The protocol that Hornbill will use to retrieve the messages. Hornbill supports POP3 and IMAP4.
* **Server.** The name or IP address of the mail server where the mail account is located.
* **Encryption.** The encryption method used in the communication between Hornbill and your mail server.
* **Port.** The port over which communication will take place. This is dictated by the encryption method and protocol used.
* **Username.** The mail account username.
* **Password.** The mail account password.

::: important
As soon as a successful connection is established with the mailbox on your mail server, Hornbill will immediately retrieve all the emails that reside in the Inbox folder.  All of these messages will be **deleted** from the server once they are downloaded to Hornbill.

Deletion of messages **ONLY** applies to messages that are in the Inbox folder; messages in other folders are not processed. 

If you have a requirement for the messages to remain on your mail server, you should ask your email system administrator to implement rules that duplicate any message sent to this mail account to another folder/location.
:::

## Addresses
This tab is where you specify a reply address --- the address that recipients will see when they receive email from Hornbill. This reply address also has another important function within the Hornbill Platform: it links the outbound mail route to the shared mailbox.

**To link an outbound mail route (domain):**
1. Click **+ Add Address**.
1. Specify the alias. The alias forms everything to the left of the @ symbol in your reply address.
1. From the dropdown, select the domain name. This list contacts all the outbound routes (domains) you have configured in Hornbill.
1. Click **Save**.
1. Select the checkbox to the left of the address, and then click **Set as Default**.
A green dot now appears to the right of the address to indicate that this is the default address.

## Status
This tab provides an overview of the mailbox folders.

## Associated Roles
In this tab, you provide access to a shared mailbox by creating and associating one or more roles. Once a role is associated with a shared mailbox, users can then be assigned to the roles. The only type of role that can be associated with a shared mailbox is a user-created (custom) role.

**To create a custom role for a shared mailbox:**
1. Open Configuration and search for *Manage Roles*.
1. Within the results under Platform, select **Manage Roles**.
1. Click **Create New Role** and populate the fields as follows:
    * **Role ID**: Mailbox – *[The name of your shared mailbox]*
    * **Privilege Level**: User
    * **Type**: Security
    * **Description**: This role will be used to grant access to the *[the name of your shared mailbox]*
1. Click **Create Role**.
1. In the Shared Mailbox field, select the shared mailbox that this role will be associated with.
1. Click **Save**.
1. Under *Shared Mailbox Rights*, select the rights that will apply to the users who are assigned this role.

### Suggested rights for a typical user
The following set of rights allows a user to perform all the common actions required to process messages that are received by the shared mailbox. It allows a user to view and manage the contents of the shared mailbox.

* Can get folder properties
* Can get message
* Can flag message
* Can delete message
* Can add file attachment
* Can send message
* Can edit message
* Can search message

### Minimum rights for sending an email
The following set of rights only allows an agent to send a message from the Hornbill Platform. It does not allow the user to view or process the contents of the shared mailbox.

* Can send message
* Can add file attachment

## FAQs

**Which protocol should I use, IMAP4 or POP3?**<br>When Hornbill integrates with your enterprise or public email system for shared mailboxes, we only use your mail server to transport mail. Once we read a mail message from your server and move it safely into our database, we delete the message on the remote server. So in this context, both POP3 and IMAP4 do the exact same job. If your server supports IMAP4, this would be the recommended protocol. IMAP4 is a more modern and flexible protocol that allows for instant mail notifications instead of polling for mail.

**Why does Hornbill delete mail from my mail server?**<br>Hornbill stores all emails it receives into its shared mailboxes in a database. Once your mail messages and attachments are in our database, they are as safe as the rest of your data on our platform. One of the problems with IMAP and POP3 with the mail systems that implement these protocols is there is generally a finite amount of storage available for mail. So the question about how to keep storage use at manageable levels becomes a complication and an administrative overhead. To combat this, many systems impose storage limits and forced message deletion policies. Another good reason is the technical details of how the IMAP and POP3 protocols are implemented. As data sets become large on your mail system, it takes more and more time and network bandwidth to synchronize between Hornbill and your mail system. For these reasons, it works a lot better and is the maintenance-free option to move the messages from your mail server to our platform.

**Will messages from folders other than the Inbox folder be deleted from my mail server during import to Hornbill**<br>No, only messages in the Inbox folder are retrieved and moved to the Hornbill shared mailbox.  Messages in any other folder in your own mailbox will be left alone. If you want to retain a copy of the inbound emails on your mailbox, we recommend you ask you email system administrator to add some rules to the mailbox to make a copy of all incoming messages into another folder (e.g. Inbox Archive).