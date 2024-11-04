---
layout: article-toc
---
# About User Accounts

## Topics Covered
* Account types
* Ways to create accounts

## Accessing User Accounts
The [Configuration](/esp-config/getting-started/using-configuration) Search can be used to access the user list.
1. Search Configuration for `Users`.
1. In the results list select `Manage Users`.

Individual user accounts can also be searched
1. Search Configuration for either the user ID or part of the user's full name.
1. In the results list select the matching user.



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


## Account Information

### Details
This is the fundamental user account information and is where you can view and manage the specific properties of a user.

#### Basic Information
A user can manage these properties independently of the system administrator via "My Profile". The majority of the properties are self-explanatory but the less intuitive ones are described below:

* **User ID**<br>The user ID is the primary key of a Hornbill user account and is used to build all the associations to other records in the database. It must be unique to a user account. Once created it cannot be changed.
* **Logon ID**<br>The Logon ID is used when a user logs into Hornbill when prompted to provide a username and password. This also has an important part to play in the Single Sign On mechanism. The Logon ID must be unique to a user account. The Login ID can be edited or changed at any time.
* **Employee ID**<br>This field is designed to store the unique value by which an employee might be identified within your Organization. This might be an HR reference, Employee Number, or Payroll Number. This field can be referenced in business processes to lookup a user. The Employee ID must be unique to a user account and it can be edited or changed at any time.
* **Hide User Account from Co-worker Directory**<br>This option is mostly used for administrative accounts that don't represent a physical user. This will hide the account from the Co-worker Directory list and most user searches and filters.
* **Home Organization**<br>See the section on [Organizations](/esp-config/organizational-data/user-accounts/about-user-accounts#organizations) below.
* **Handle**<br>A user's handle is displayed in various places when the user interacts with the applications installed on the Hornbill Platform. This could be a nickname or a preferred name however many organizations opt for a "first name" + "last name" approach.
* **Manager**<br>This field makes an association with another Hornbill user account. When a manager is specified it means that certain functionality within the Hornbill apps can be leveraged. To name one example; it is possible to set a variable in Business Process to automatically assign authorization tasks to an individual's manager.
* **Availability**<br>Hornbill offers the ability for a user to set their Availability Status via the "My Profile" page along with a supporting message. This will be displayed to other Hornbill users when they search for this user.
* **Status**<br>Each Hornbill Account is subject to a "User Status". This may be "Active", "Suspended" or "Archived". 

:::tip
Archived user accounts do not consume a subscription allocation.
:::

#### Location
In this section, you can associate a user to a location and specify the country where they are located. A user can manage these properties independently of the system administrator via "My Profile". The site field is driven by a drop-down menu which is driven by the list of sites that you configure in Hornbill. If this is empty it will mean that you have not yet configured any [locations](/esp-config/organizational-data/locations). 

:::tip
It is only possible to associate a user to a single location. It is a one-to-one relationship.
:::

#### Regional Settings
The regional settings specify the various regional properties of a user. These settings influence how a user is presented with region-specific information in the Hornbill user interface i.e. the date and time formats will influence how a user sees date and time values in Workspaces, Requests, and throughout the various other applications installed on the Hornbill Platform. A user can manage these properties independently of the System Administrator via "My Profile".

#### Security Settings
Configure options that control how the user logs into Hornbill.

* **Disable direct login**<br>Prevent this user account from being logged into using the Direct Login function.
* **Disable direct login password reset**<br>Prevent this user account from being able to use the Password Reset Request feature of Direct Login.
* **Disable device pairing on user profile**<br>Prevent this user account from being able to pair to other devices from which they can log in using the mobile app.

#### Change Password
A System administrator can reset the password on behalf of the user. If Single Sign On is in use, the password set here is not relevant as any authentication will be done via your identity provider based on the contents of your directory. Hornbill has a range of system settings that allow you to set a password policy i.e. you can set certain criteria that enforces the format of a password such as a minimum length. Password Policy Settings can be found in Configuration > Platform Configuration > Advanced System Settings under the section Advanced Tools & Settings. Using the following string in the search filter will provide you with the available password policy settings: security.user.passwordPolicy

### About
The "About" section is a continuation of the Users Basic Information and allows you to manage extended properties that complete a user's Profile. A user has the ability to manage these properties independently of the System Administrator via "My Profile".

### Roles
Roles for an individual user can be viewed and managed.

### Custom Fields
A user account features several unallocated fields (Attributes 1-8) commonly known as "custom fields". These can be used to store information beyond the user properties provided.

### API Keys
An [API key](/esp-config/integration/api-keys) is typically used in conjunction with one of Hornbill's import utilities to avoid the need to specify passwords in configuration files that will be located outside of Hornbill. Each of the Hornbill import utilities must perform their actions in the context of a user account and to do this an API key must be created. It is good practice to create and use API keys in conjunction with bespoke development work and integration with other systems that involve information being passed into your Hornbill instance from these other systems.

### Devices
Registered devices are created to allow a user to access Hornbill using the Hornbill Mobile App on a mobile device.  Any devices that a user has registered will be listed in this tab. While a system administrator is currently unable to register a device on behalf of a user, the system administrator has the power to de-register the device if the user has left the organization or the device has been reallocated.

### Organizations
Here it is possible to view the [Hornbill groups](/esp-config/organizational-data/organization) that a user is currently associated with and if necessary associate the user with more groups. 
A user can be a member of multiple groups i.e. it is a one-to-many relationship.

#### Home Organization
A user can also be assigned a home organization. When in the Organization tab of a user account, you can select an organization of type "Company" and on doing so the button to "Set Home Organization" will enable. Click on this button to set the selected organization as the user's home organization.

The Home Organization is used in conjunction with the Company Settings on the Employee Portal. Unique company branding can be configured for each Company and when a user with a set Home Organization views the Employee Portal, they will be presented with the branding that has been defined for this Company.

### Workspaces
When Collaborating via the Hornbill Platform, a user may create many Workspaces. This tab allows a system administrator to view the Workspaces that the user has created and if necessary re-assign ownership.
