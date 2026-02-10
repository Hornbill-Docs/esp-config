---
layout: article-toc
keywords: custom role, user-created role, link a domain
---
# Shared mailboxes

Shared mailboxes allow your team to manage incoming and outgoing emails from a single, collective email address. This setup helps groups of users collaborate on communication without needing individual login credentials for the same account.

:::note
Every Hornbill instance includes two shared mailboxes. Additional mailboxes require a monthly subscription charge.
:::

## Before you begin

Before you set up a shared mailbox, ensure you have completed the following:

* **Configure a domain:** You must have a [domain](/esp-config/email/email-domains) in place and an outbound mail route configured. Creating a mailbox in Hornbill does not automatically create a new email domain.
* **Create a custom role:** You need at least one [custom role](/esp-config/email/shared-mailboxes#associated-roles) (also known as a user-created role) to grant users access to the mailbox.

## Mailbox details

Use the **Details** tab to define the basic identity of your mailbox.

* **Mailbox Name:** This is the internal reference name used within the Hornbill Platform. You cannot change this name after you create the mailbox.
* **Display Name:** This is the name recipients see when they receive an email from this mailbox. You can edit this name at any time.

## Inbound mail service

The **Inbound Mail Service** tab defines how Hornbill retrieves messages from your organization's mail server. Hornbill periodically checks your mail exchange to pull new messages into the platform.

Provide the following information:

* **Service:** The protocol Hornbill uses to retrieve messages (POP3 or IMAP4).
* **Server:** The name or IP address of your mail server.
* **Encryption:** The method used to secure communication between Hornbill and your server.
* **Port:** The communication port, which depends on your chosen protocol and encryption.
* **Username:** The username for the mail account.
* **Password:** The password for the mail account.

:::important
When Hornbill connects to your mail server, it retrieves all emails from the **Inbox** folder. Hornbill deletes these messages from your mail server once they are successfully downloaded to the platform. To keep copies on your mail server, ask your email administrator to create a rule that duplicates incoming messages to a different folder.
:::

## Addresses

You must specify a reply address to link your outbound mail route to the shared mailbox.

### Steps

1. Click **+ Add Address**.
2. Enter the **Alias**. This is the text that appears before the @ symbol.
3. Select your domain name from the dropdown list.
4. Click **Save**.
5. Select the checkbox next to the new address.
6. Click **Set as Default**.

### Expected result

A green dot appears next to the address, indicating it is now the default reply address for the mailbox.

## Status

The **Status** tab provides an overview of your mailbox folders, including message counts and storage size.

* **Empty Folder:** You can permanently delete all messages in a specific folder. Use this option carefully, as deleting messages may remove access to emails linked to specific tasks or records.

    :::tip
    [Advanced sytem settings](/esp-config/advanced-tools-and-settings/advanced-system-settings) are availble to automatically purge the **Deleted Items** and **Sent Items** folders after a selected period of time. These settings are `emails.purgeDeletedItemsAfter` and `emails.purgeSentItemsAfter`.
    :::

## Associated roles

To give your team access to the mailbox, you must create associate a custom role.

### Steps to associate a role

1. Open **Configuration** and search for **Manage Roles**.
2. Select **Manage Roles** from the Platform results.
3. Click **Create New Role** and enter the following details:
    * **Role ID:** Mailbox (Include the name of your shared mailbox).
    * **Privilege Level:** User.
    * **Type:** Security.
    * **Description:** Provide a brief note explaining that this role grants access to the specific mailbox.
4. Click **Create Role**.
5. In the **Shared Mailbox** field, select the mailbox you want to associate with this role.
6. Click **Save**.
7. Under **Shared Mailbox Rights**, select the permissions for users assigned to this role.

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

**Which protocol should I use, IMAP4 or POP3?**: When Hornbill integrates with your enterprise or public email system for shared mailboxes, we only use your mail server to transport mail. Once we read a mail message from your server and move it safely into our database, we delete the message on the remote server. So in this context, both POP3 and IMAP4 do the exact same job. If your server supports IMAP4, this would be the recommended protocol. IMAP4 is a more modern and flexible protocol that allows for instant mail notifications instead of polling for mail.

**Why does Hornbill delete mail from my mail server?**: Hornbill stores all emails it receives into its shared mailboxes in a database. Once your mail messages and attachments are in our database, they are as safe as the rest of your data on our platform. One of the problems with IMAP and POP3 with the mail systems that implement these protocols is there is generally a finite amount of storage available for mail. So the question about how to keep storage use at manageable levels becomes a complication and an administrative overhead. To combat this, many systems impose storage limits and forced message deletion policies. Another good reason is the technical details of how the IMAP and POP3 protocols are implemented. As data sets become large on your mail system, it takes more and more time and network bandwidth to synchronize between Hornbill and your mail system. For these reasons, it works a lot better and is the maintenance-free option to move the messages from your mail server to our platform.

**Will messages from folders other than the Inbox folder be deleted from my mail server during import to Hornbill**: No, only messages in the Inbox folder are retrieved and moved to the Hornbill shared mailbox.  Messages in any other folder in your own mailbox will be left alone. If you want to retain a copy of the inbound emails on your mailbox, we recommend you ask you email system administrator to add some rules to the mailbox to make a copy of all incoming messages into another folder (e.g. Inbox Archive).
