---
layout: article-toc
---
# Manually Creating Users
Within Configuration, user accounts can be manually created. Manual creation is typically used when there is a need for initial accounts during a new implementation. These might be used for testing or for special accounts that would not be included in an automated import and synchronization from an external source such as Microsoft Active Directory.

## Before You Begin
* Administrative access to [Configuration](/esp-config/getting-started/using-configuration).
* An understanding of user account types.
* It's recommended to have an organization group structure in place.

## Topics Covered
* Manual account creation.
* Mandatory fields.
* Basic user account management.

## Quick Steps
1. Open Configuration and search for `users` and select `Manage Users` from the results list
1. On the Tool Bar click the `Create New User` button
1. Complete the mandatory fields along with any other additional information that you wish to add
1. Click on the `Create User` button.

## Basic Information

### User ID vs Login ID
* **User ID**<br>The user ID is the primary key of a Hornbill user account and is used to build all the associations to other records in the database. It must be unique to a user account. Once created it cannot be changed.  Avoid using anything that has the potential to change. This is a mandatory field.
* **Logon ID**<br>The Logon ID is used when a user logs into Hornbill when prompted to provide a username and password. This also has an important part to play in the Single Sign On mechanism. The Logon ID must be unique to a user account. The Login ID can be edited or changed at any time.

::: tip
When the Login ID is populated, a user can no longer use their User ID to log in.
:::

### Mandatory Fields
For an account to be created, all mandatory fields must be completed. Mandatory fields are marked with a vertical red line.
* User ID
* First Name
* Handle
* Password

## Account Management

### Delete accounts
Deleting a user completely removes the account from Hornbill and cannot be reversed. Deleting a user should only be used when the user has not had any interaction in Hornbill. This can be used to remove accounts that have been mistakenly added or uploaded. This option is only available when the user who performs the deletion has been allocated the Super User Role.

### Reactivate Users
When one or more users have been suspended or archived, you can select these users from the list and reactivate them.

### Suspend Users
The suspension of a user prevents the account from logging on to Hornbill. Other Hornbill users will be able to continue to interact with a suspended account. Suspended users can be reactivated. A user can be automatically suspended by providing too many incorrect passwords at login.

### Archive Users
Archiving a user prevents the account from logging on to Hornbill and will also prevent other users from interacting with this account. Historic contributions within the collaboration features will be intact and visible, but they will no longer be available as a co-worker. This is the recommended option for when someone leaves. Archived users can be reactivated.