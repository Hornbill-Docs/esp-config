---
layout: article-toc
---
# About user accounts

## Topics covered

* [Accessing user accounts](/esp-config/organizational-data/user-accounts/about-user-accounts#accessing-user-accounts)
* [Types of user accounts](/esp-config/organizational-data/user-accounts/about-user-accounts#types-of-user-accounts)
* [Ways to create user accounts](/esp-config/organizational-data/user-accounts/about-user-accounts#ways-to-create-user-accounts)
* [About archiving users vs. suspending users](/esp-config/organizational-data/user-accounts/about-user-accounts#about-archiving-users-vs-suspending-users)
* [Reference: account information](/esp-config/organizational-data/user-accounts/about-user-accounts#reference-account-information)

## Accessing user accounts

You can use the [Configuration](/esp-config/getting-started/using-configuration) Search to access the user list.

**To access the user list:**

1. Search Configuration for `Users`.
1. In the results list, select `Manage Users`.

**To find individual user accounts:**

1. Search Configuration for either the user ID or part of the user's full name.
1. In the results list, select the matching user.

## Types of user accounts

Hornbill users are categorized into two types: full and basic.

### Full user

Full user accounts are for those that require access to one or more of the available Hornbill applications. The number of user accounts is governed by your paid subscriptions. You will be allowed to create user accounts as long as you have enough subscriptions available.

### Basic user

Basic user accounts are for people who are internal to your organization and who will consume the content and services that are delivered by the Hornbill applications.  Basic accounts can be used within applications to associate with entities such as Service Manager requests, assets, sites, and documents, and also provide login access to the Employee Portal.

:::tip
Accounts can be either promoted or demoted between these two types of accounts after they have been created. This can be done by changing the user type when viewing the account record.
:::

For a detailed explanation of the different account types, see [Hornbill Platform Account Types](/esp-fundamentals/security/account-types).

## Ways to create user accounts

* **Manual creation.** Within Configuration, accounts can be manually created.  [Manual creation](/esp-config/organizational-data/user-accounts/users) is typically used when there is a need for initial accounts during a new implementation.  These might be used for testing or for special accounts that would not be included in an automated import and synchronization from an external source such as Microsoft Active Directory.  
* **CSV import.** From the list of accounts, a simple [CSV import](/esp-config/organizational-data/user-accounts/csv-user-import) is provided. This is only for the creation of new accounts and does not provide updates to existing accounts.
* **Auto-provisioning.** [Auto-provisioning](/esp-config/security/sso/auto-provisioning) takes advantage of SSO using an external identity provider (IDP), such as Microsoft Active Directory Federation Services.  If a user is authenticated using an IDP and a Hornbill account does not exist, the account will be automatically created using a template and the user seamlessly gains access to Hornbill.
* **Import and synchronization tools.** The most common way of managing accounts is by using an import and synchronization tool.  These include [LDAP Import](/data-imports-guide/users/ldap/overview), [Entra ID Import](/data-imports-guide/users/azure/overview), [Database Import](/data-imports-guide/users/database/overview), and [Google User Import](/data-imports-guide/users/google/overview).

## About archiving users vs. suspending users

The Status field in a user's account information holds a status of *Active*, *Suspended*, or *Archived*

### What's the difference between *Suspended* and *Archived*?

Suspending a user account is a security control. For example, you may want to temporarily take away someone's  access to Hornbill. Another example might be that if a user has made too many failed attempts at entering their password, the system automatically suspends the user account. Suspending an account is generally temporary, and the user is still considered a user of the system. However, they cannot log in while they are suspended.

Archiving a user account is generally what you do when someone is no longer using Hornbill, for example, if they leave their job. Even though they have left the company, you want to keep references to their basic user information so that historical logs, posts, request updates, and so on are still referencing their user account. But an archived user is considered a non-user for the purpose of logging in, making assignment, and so on. Un-archiving a user is functionally equivalent to adding and setting up a new user on Hornbill.

### What happens to *Archived* users?

When you set a user status to *Archived*, you effectively streamline your active user list, ensuring that searches for current users are more relevant to the present. Despite being archived, these users are not permanently deleted; you can access them via the dropdown filter by selecting the **Archived**** option. This enables you to maintain a comprehensive record of past associations for future reference, if necessary.

Archiving a user is permanent. When a user is archived, all the application subscriptions they may have had to various applications or services will be automatically removed, freeing up those allocated subscriptions. This is because their membership in any associated roles, groups, or teams within your organization will also be revoked as part of the archiving process.

For more information, see [Account Management](/esp-config/organizational-data/user-accounts/users#account-management)

## Reference: account information

### Details

This is the fundamental user account information and is where you can view and manage the specific properties of a user.

#### Basic Information

A user can manage these properties independently of the system administrator via "My Profile". The majority of the properties are self-explanatory but the less intuitive ones are described below:

* **User ID.** The user ID is the primary key of a Hornbill user account and is used to build all the associations to other records in the database. It must be unique to a user account. Once created, it cannot be changed.
* **Logon ID.** This is used when a user logs into Hornbill when prompted to provide a username and password. This also has an important part to play in the Single Sign On (SSO)mechanism. The Logon ID must be unique to a user account and it can be edited or changed at any time.
* **Employee ID.** This field is designed to store the unique value by which an employee might be identified within your organization. This might be an HR reference, employee number, or payroll number. This field can be referenced in workflows to look up a user. The Employee ID must be unique to a user account and it can be edited or changed at any time.
* **Hide User Account from Co-worker Directory.** This option is mostly used for administrative accounts that don't represent a physical user. This will hide the account from the Co-worker Directory list and most user searches and filters.
* **Home Organization.** See [Organizations](/esp-config/organizational-data/user-accounts/about-user-accounts#organizations) below.
* **Handle.** A user's handle is displayed in various places when the user interacts with the applications installed on the Hornbill platform. This could be a nickname or a preferred name, however many organizations opt for a "first name" + "last name" approach.
* **Manager.** This field makes an association with another Hornbill user account. When a manager is specified, it means that certain functionality within the Hornbill apps can be leveraged. To name one example: it is possible to set a variable in a workflow to automatically assign authorization tasks to an individual's manager.
* **Availability.** Users can set their Availability status via the "My Profile" page along with a supporting message. This will be displayed to other Hornbill users when they search for this user.
* **Status.** Each Hornbill account is subject to a "user status". This may be *Active*, *Suspended*, or *Archived*.

    :::tip
    Archived user accounts do not consume a subscription allocation.
    :::

#### Location

In this section, you can associate a user to a location and specify the country where they are located. A user can manage these properties independently of the system administrator via "My Profile". The site field is driven by a drop-down menu which is driven by the list of sites that you configure in Hornbill. If this is empty, it will mean that you have not yet configured any [locations](/esp-config/organizational-data/locations).

:::tip
It is only possible to associate a user to a single location. It is a one-to-one relationship.
:::

#### Regional Settings

The regional settings specify the various regional properties of a user. These settings influence how a user is presented with region-specific information in the Hornbill user interface. The date and time formats will influence how a user sees date and time values in Workspaces, Requests, and throughout the various other applications installed on the Hornbill platform. A user can manage these properties independently of the system administrator via "My Profile".

#### Security Settings

Here you can configure options that control how the user logs into Hornbill.

* **Disable direct login.** Prevent this user account from being logged into using the Direct Login function.
* **Disable direct login password reset.** Prevent this user account from being able to use the Password Reset Request feature of Direct Login.
* **Disable device pairing on user profile.** Prevent this user account from being able to pair to other devices from which they can log in using the mobile app.

#### Change Password

A system administrator can reset the password on behalf of the user. If Single Sign On (SSO) is in use, the password set here is not relevant because any authentication will be done via your identity provider based on the contents of your directory.

Hornbill has a range of system settings that allow you to set a password policy. For example, you can set certain criteria that enforce the format of a password, such as a minimum length.

**To configure password policy settings:**

1. Navigate to **Configuration > Platform Configuration > Advanced Tools & Settings > Advanced System Settings**.
1. Find all the available password policy settings using the following string in the search filter: `security.user.passwordPolicy`.
1. Make adjustments using the ON/OFF toggle for each setting you want to configure.

### About

The About section is a continuation of the user's basic information. This section allows you to manage extended properties that complete a user's profile. A user has the ability to manage these properties independently of the system administrator via "My Profile".

### Roles

Here you can view and manage roles for individual users.

### Custom Fields

A user account features several unallocated fields (Attributes 1-8) commonly known as *custom fields*. These can be used to store information beyond the user properties provided.

### API Keys

An [API key](/esp-config/integration/api-keys) is typically used in conjunction with one of Hornbill's import utilities to avoid the need to specify passwords in configuration files that will be located outside of Hornbill. Each of the Hornbill import utilities must perform their actions in the context of a user account; to do this an API key must be created. It is good practice to create and use API keys in conjunction with bespoke development work and integration with other systems that involve information being passed into your Hornbill instance from these other systems.

### Devices

Registered devices are created to allow a user to access Hornbill using the Hornbill mobile app on a mobile device.  Any devices that a user has registered will be listed in this tab. While a system administrator is currently unable to register a device on behalf of a user, the system administrator has the power to de-register the device if the user has left the organization or the device has been reallocated.

### Organizations

Here you can view the [Hornbill groups](/esp-config/organizational-data/organization) that a user is currently associated with, and if necessary, associate the user with more groups. A user can be a member of multiple groups; it is a one-to-many relationship.

#### Home Organization

A user can also be assigned a home organization. When in the **Organization** tab of a user account, you can select an organization of type Company; on doing so, the **Set Home Organization** button is enabled. Click this button to set the selected organization as the user's home organization.

The home organization is used in conjunction with the company settings on the Employee Portal. Unique company branding can be configured for each company, and when a user with a set home organization views the Employee Portal, they will be presented with the branding that has been defined for this company.

### Workspaces

When collaborating via the Hornbill platform, a user may create many workspaces. This tab allows a system administrator to view the workspaces that the user has created, and if necessary, re-assign ownership.
