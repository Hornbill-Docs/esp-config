---
layout: article-toc
---
# Creating and managing accounts

## Before you begin
* Administrative access to Configuration
* An Understanding of roles
* It's recommended to have an organization group structure in place

## Topics covered
* Manual account creation
* Settings
* Adding roles
* Password Policies
* Two factor authentication


## Manual creation
1. Open Configuration and search for `users` and select `Manage Users` from the results list
1. On the Tool Bar click the `Create New User` button
1. Complete the mandatory fields along with any other additional information that you wish to add
1. Click on the `Create User` button.

## Templates
User templates are used to create a standard set of settings which can then be used to create user accounts through auto provisioning or when users are manually created. An example of using an identity provider would be to use Active Directory Services to authenticate with Hornbill. When this authentication happens, if a user account does not exist in Hornbill it will be automatically created using this template.

## Account Management

### Delete accounts
Deleting a user completely removes the account from Hornbill and cannot be reversed. Deleting a user should only be used when the user has not had any interaction in Hornbill. This can be used to remove accounts that have been mistakenly added or uploaded. This option is only available when the user who performs the deletion has allocated the Super User Role.

### Reactivate Users
When one or more users have been suspended or archived, you can select these users from the list and reactivate them.

### Suspend Users
The suspension of a user prevents the account from logging on to Hornbill. Other Hornbill users will be able to continue to interact with a suspended account. Suspended users can be reactivated. A user can be automatically suspended by providing too many incorrect passwords at login.

### Archive Users
Archiving a user prevents the account from logging on to Hornbill and will also prevent other users from interacting with this account. Historic contributions within the collaboration features will be intact and visible, but they will no long be available as a co-worker. This is the recommended option for when someone leaves. Archived users can be reactivated.



## User ID vs Login ID

## To do
1. Roles
1. Sites
1. Organization Group Membership
1. Set Home Organization
