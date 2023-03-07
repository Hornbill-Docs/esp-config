---
layout: article-toc
---
# Creating and managing users

## Before you begin
* Administrative access to Configuration
* An Understanding of user roles
* Download AD tools
* Active Directory Services
* It's recommended to have an organization group structure in place

## Topics covered
* Account types
* Ways to create accounts
* User templates
* Manual account creation
* Settings
* Passwords - requirements and 2 factor
* Auto-provisioning
* Adding roles
* AD imports
* Password Policies
* Two factor authentication

## Account Types
Hornbill Accounts are categorized into user and basic accounts. User accounts are used for full access to Hornbill and the different available apps.  These accounts require a subscription to login. Basic accounts are typically used for Employee Portal access only and are subscription free. 

### User Accounts
User accounts are for those that require access to one or more of the available Hornbill applications. The number of user accounts is governed by your paid for subscriptions. You will be allowed to create user accounts as long as you have enough subscriptions available.

### Basic Accounts
Basic accounts are for people that are internal to your organization who will consume the content and services that are delivered by the Hornbill applications.  This is typically done  through the Employee Portal or email.

:::tip
Accounts can be either promoted or demoted between these two types of accounts after they have been created. This can be done by changing the user type when viewing the account record.
:::

## Ways to create accounts
* **Manual creation**<br>Within Configuration, accounts can be manually created.  Manual creation is typically used when there is a need for initial accounts during a new implementation.  These might be used for testing or for special accounts that would not be included in an automated import and synchronization from an external source such as Microsoft Active Directory.  
* **CSV import**<br>From the list of accounts, a simple CSV import is provided. This is only for the creation of new accounts and does not provide updates to existing accounts.
* **Auto-provisioning**<br>This feature takes advantage of single sign-on using an external identity provided (IDP), such as Microsoft Active Directory Federation Services.  If a user is authenticated using an IDP and a Hornbill account does not exist, the account will be automatically created using a template and the user seamlessly gains access to Hornbill. 
* **Import and synchronization tools**<br>The most common way of managing accounts is by using an import and synchronization tool.  These include LDAP Import, Azure Import, Database Import, and Google User Import.

## Manually creating accounts
1. Open Configuration and search for `users` and select `Manage Users` from the results list
1. On the Tool Bar click the `Create New User` button
1. Complete the mandatory fields along with any other additional information that you wish to add
1. Click on the `Create User` button.

## User ID vs Login ID

## To do
1. Roles
1. Sites
1. Organization Group Membership
1. Set Home Organization
1. Creating from template
