---
layout: article-toc
---
# About User Accounts

## Topics Covered
* Account types
* Ways to create accounts

## User Account Types
Hornbill users are categorized into two types, full and basic.

### Full User
User accounts are for those that require access to one or more of the available Hornbill applications. The number of user accounts is governed by your paid subscriptions. You will be allowed to create user accounts as long as you have enough subscriptions available.

### Basic User
Basic accounts are for people who are internal to your organization and who will consume the content and services that are delivered by the Hornbill applications.  Basic accounts can be used within applications to associate with entities such as Service Manager requests, assets, sites, and documents, and also provide login access to the Employee Portal. 

:::tip
Accounts can be either promoted or demoted between these two types of accounts after they have been created. This can be done by changing the user type when viewing the account record.
:::

For a detailed explanation of the different account types please read the fundamentals of [Hornbill Platform Account Types](/esp-fundamentals/security/account-types).

## Ways To Create User Accounts
* **Manual creation**<br>Within Configuration, accounts can be manually created.  [Manual creation](/esp-config/organizational-data/user-accounts/users) is typically used when there is a need for initial accounts during a new implementation.  These might be used for testing or for special accounts that would not be included in an automated import and synchronization from an external source such as Microsoft Active Directory.  
* **CSV import**<br>From the list of accounts, a simple [CSV import](/esp-config/organizational-data/user-accounts/csv-user-import) is provided. This is only for the creation of new accounts and does not provide updates to existing accounts.
* **Auto-provisioning**<br>[Auto-provisioning](/esp-config/security/sso/auto-provisioning) takes advantage of single sign-on using an external identity provided (IDP), such as Microsoft Active Directory Federation Services.  If a user is authenticated using an IDP and a Hornbill account does not exist, the account will be automatically created using a template and the user seamlessly gains access to Hornbill. 
* **Import and synchronization tools**<br>The most common way of managing accounts is by using an import and synchronization tool.  These include [LDAP Import](/data-imports-guide/users/ldap/overview), [Entra ID Import](/data-imports-guide/users/azure/overview), [Database Import](/data-imports-guide/users/database/overview), and [Google User Import](/data-imports-guide/users/google/overview).
