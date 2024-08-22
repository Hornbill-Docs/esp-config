---
layout: article-toc
---
# Shared mailboxes
Shared mailboxes are created to allow a group of users to share a single mailbox for both outgoing and incoming emails, all using a common email address.

:::note
The first two shared mailboxes are included with every instance. Additional mailboxes are subject to an additional monthly subscription charge.
:::


## Before you begin
* At least one [user created role](/esp-config/organizational-data/roles#custom-roles) needs to be available.  User created roles are used to provide access between users and a shared mailbox.

## Mailbox Details
This is where the basic details of the mailbox are specified:

* **Mailbox Name**<br>This is used to reference the mailbox within the Hornbill Platform when there is a need to specify a mailbox in certain application settings. Once the mailbox is created this cannot be changed.
* **Display Name**<br>This is what the recipients of the email will see when they receive an email from Hornbill. This can be edited at any time.

## Adding an Inbound Mail Service
This tab is where we tell Hornbill where it will retrieve email messages. Remember, in a typical setup, email messages are not sent directly to your Hornbill instance but are retrieved periodically from a mail account that will reside on your organizations mail exchange. The information Hornbill needs is as follows:

* **Service**<br>The protocol that Hornbill will use to retrieve the messages. Hornbill supports POP3 or IMAP4.
* **Server**<br>The name or IP address of the mail server where the mail account is located.
* **Encryption**<br>The encryption method used in the communication between Hornbill and your mail server.
* **Port**<br> the port over which communication will take place. this will be dictated by the encryption method and Protocol used.
* **Username**<br>The mail account username.
* **Password**<br>The mail account password.

::: important
As soon as a successful connection is established with the mailbox on your mail server, Hornbill will immediately retrieve all the emails that reside in the Inbox folder.  All of these messages will be **deleted** from the server once they are downloaded to Hornbill.

Deletion of messages **ONLY** applies to messages that are in the Inbox folder, messages in other folders are not processed. 

If you have a requirement for the messages in remain on your mail server, you should ask your email system administrator to implement some rules that duplicate any message sent to this mail account to another folder/location.
:::

## Linking an Outbound Mail Route (Domain)
The "Addresses" tab is where we specify a "reply address" i.e. the address that recipients will see when the receive email from Hornbill. This reply address also has another important function within the Hornbill Platform which is to link the outbound mail route to the Shared Mailbox. Prior to performing this step, it will be necessary to [configure your Outbound Mail Route](/esp-config/email/email-domains).

1. Click **Add Address**.
1. Specify the alias. The alias forms everything to the left of the '@' symbol in your reply address.
1. From the pick list, select the domain name. This pick list contacts all the Outbound Routes (Domains) you have configured in Hornbill.
1. Click **Save**.
1. Mark the check box to the left of the Address, and set this as the default by clicking the "tick" button at the top right.
A green dot should now appear to the right of the address to indicate that this is the default address.

## Mailbox Status
The "Status" tab provides an overview of the mailbox folders.

## Associated Roles
Providing access to a shared mailbox is done by creating and associating one or more roles. Once a role is associated with a shared mailbox, users can then be assigned to the roles. A shared mailbox can only be associated with a user-created role.

### Create a New Shared Mailbox Role
If a role for a shared mailbox has not previously been created, you will need to create a role before you can provide access to users.
1. Open Configuration and search for `Manage Roles`.
1. Within the results under Platform select `Manage Roles`.
1. Click the `Create New Role` button (located to the top right of the list) and populate the fields as follows:
    * **Role ID**: Mailbox – *(The name of your shared mailbox)*
    * **Privilege Level**: User
    * **Type**: Security
    * **Description**: This role will be used to grant access to the *(The name of your shared mailbox)*
1. Click on the `Create Role` button.
1. In the Shared Mailbox field, select the shared mailbox that this role will be associated with.
1. Click **Save**.
1. Under the `Shared Mailbox Rights`, select the rights that will apply to the users who are assigned this role.

#### Suggested rights for a typical user
This set of rights allows a user to perform all the common actions required to process messages that are received by the Shared Mailbox. It allows a user to view and manage the contents of the shared mailbox.

* Can get folder properties
* Can get message
* Can flag message
* Can delete message
* Can add file attachment
* Can send message
* Can edit message
* Can search message

#### Minimum rights for sending an email
This set of rights only allows an agent to send a message from the Hornbill Platform. It does not allow the user to view or process the contents of the shared mailbox.

* Can send message
* Can add file attachment

## Frequently Asked Questions

1. **Which protocol should I use, IMAP4 or POP3?**<br>When Hornbill integrates with your enterprise or public e-mail system for shared mailboxes, we only use your mail server to transport mail. Once we read a mail message from your server and move it safely into our database, we delete the message on the remote server. So in this context, both POP3 and IMAP4 do the exact same job. If your server supports IMAP4, this would be the recommended protocol. IMAP4 is a more modern and flexible protocol that allows for instant mail notifications instead of polling for mail.
1. **Why does Hornbill delete mail from my mail server?**<br>Hornbill stores all emails it receives into its shared mailboxes in a database. Once your mail messages and attachments are in our database, they are as safe as the rest of your data on our platform. One of the problems with IMAP and POP3 with the mail systems that implement these protocols is there is generally a finite amount of storage available for mail. So the question about how to keep storage use at manageable levels becomes a complication and an administrative overhead. To combat this, many systems impose storage limits and forced message deletion policies. Another good reason is the technical details of how the IMAP and POP3 protocols are implemented. As data sets become large on your mail system, it takes more and more time and network bandwidth to synchronize between Hornbill and your mail system. For these reasons, it works a lot better and is the maintenance-free option to move the messages from your mail server to our platform.
1. **Will messages from folders other than the Inbox folder be deleted from my mailserver during import to Hornbill**<br>No, only messages in the Inbox folder are retrievd and moved to the Hornbill shared mailbox.  Messages in any other folder on your own mailbox will be loeft alone. If you want to retain a copy of the inbound emails on your mailbox, we reccomenned you ask you email system administrator to add some rules to the mailbox to make a copy of all incoming messages into another folder (i.e. Inbox Archive) on your mailbox.