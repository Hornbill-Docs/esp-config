# Selecting the best method to create users
This document looks at the different options and methods for adding users to Hornbill. Depending on your environment and requirements, there are several different approaches for adding users to Hornbil which can be anything from the manual creation of a single user to the automated provisioning of users from a scheduled import.

## Quick check
* [I just need to create one user.](/esp-config/organizational-data/user-accounts/user-creation-options#create-an-individual-user-account)
* [I need to do a one-time import from a CSV file](/esp-config/organizational-data/user-accounts/user-creation-options#create-multiple-user-accounts-using-csv-upload).
* [I want to schedule an import of users from Microsoft Active Directory](/esp-config/organizational-data/user-accounts/user-creation-options#hornbill-user-import-utilities).
* [I want to schedule an import of users from an external data source](/esp-config/organizational-data/user-accounts/user-creation-options#hornbill-user-import-utilities).
* [I want accounts to be automatically created when users log in using SAML authentication.](/esp-config/organizational-data/user-accounts/user-creation-options#auto-provisioning-via-sso) 


## Create an individual user account
When either a single user or a small handful of users is needed, [manually adding user accounts](/esp-config/organizational-data/user-accounts/users) can be the most practical option when you are dealing with a small number.

* Often used to create the first few accounts that will be used when initially setting up a Hornbill instance.
* Use to add an individual user that is not automatically added as part of a scheduled import.
* Manually adding accounts does not include any configuration options for automatic updates to the account.
* Done using the platform configuration. No additional configuration is required.

## Create multiple user accounts using CSV upload
When a large number of user accounts need to be created, a [CSV upload](/esp-config/organizational-data/user-accounts/csv-user-import) can be a quick and simple way to achieve this. A CSV template is provided which includes some of the standard fields that are required to create a new user account.

* A user account is created when the upload is initiated via Hornbill Administration.
* The account is created using the contents of the CSV template selected.
* The CSV upload is designed only for the creation of new accounts. It is not capable of updating existing user accounts.
* This particular CSV import cannot be scheduled.

## Hornbill user import utilities
Application User and Basic User accounts can be created based on the content of another data source such as your Directory Service or an MSSQL database using one of Hornbill's Open integration Utilities. A user import utility is the preferred choice for an implementation involving Service Manager. All Hornbill user import utilities can be scheduled to create and update user accounts.

* These can be scheduled using Windows Scheduler.
* Options to allow for both create and update of users.
* Installed within your environment and securely connects to your Hornbill instance.
* Ability to maintain a greater range of user account properties.
* Ability to make associations between user accounts and site records and also department (group) membership based on the contents that exist in your directory services.
* A user account is created at the time the chosen utility is scheduled to run.

The available User Import tools include:

* **LDAP User Import**. This utility provides a simple, safe and secure way to create new Hornbill User Accounts and update existing ones by synchronizing with accounts held in your [Active Directory](/data-imports-guide/users/ldap/overview) or other industry standard LDAP capable directory service.
* **SQL User Import**. This utility provides a simple, safe and secure way to create user accounts on the Hornbill platform by synchronizing with accounts held in your [Database](/data-imports-guide/users/database/overview).
* **Entra ID User Import**. The utility provides a simple, safe and secure way to create user accounts on the Hornbill platform by synchronizing with accounts held in [Entra ID](/data-imports-guide/users/azure/overview).

## Auto provisioning via SSO
The creation of user accounts can be automated as part of the Single Sign-on (SSO) configuration meaning no physical import is required if SAML is available. Your users are [self-provisioned automatically](/esp-config/security/sso/auto-provisioning) when they first navigate to your Hornbill instance.

* No Import of users required. Accounts are created as they login
* Site associations are limited to a single site specified in the Auto-Provisioning template.
* Only one user template can be used in conjunction with a Hornbill Security profile (Single sign-on configuration).
* Updates to existing user accounts are supported
* The account is created based on the contents of your directory services transported through the attributes specified in the outgoing claim of your Identity Provider. The directory attribute-to-Hornbill mappings are stored in the Hornbill SSO Profile.

