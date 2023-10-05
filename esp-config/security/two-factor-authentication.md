---
layout: article-toc
---
# Two-factor authentication

Hornbill supports two-factor authentication (2FA) for both user and guest accounts. 

2FA can either be enabled for all accounts, or on an account-by-account basis.

## Before you begin
* Hornbill must have an [email domain](/esp-config/email/adding-an-email-domain#creating-an-email-domain) set up for outbound routing
* Users must have a valid email address on their account
* 2FA is only applicable to the web apps.  It is not available on the native mobile apps.
* When using SSO, Hornbill 2FA is not used. Instead, 2FA should be set up using your identity provider if the option is available.

## How Two-Factor Authentication Works
With Two-factor Authentication (2fa) enabled, when a user (guest) logs in to Hornbill, they will be prompted to enter a 6-digit authentication code.

The user retrieves this code from an email sent to their account's email address, and uses it to complete the log in process.

![2FA Code](/_books/esp-config/security/images/2fa.png)

## Settings
Enabling 2FA is done in Advanced System Settings.  

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by part or all of the setting name 
:::

|Name|Description|Default|
|-|-|-|
|security.guest.2fa.timeout|The number of seconds a 2FA challenge token remains valid (in seconds)|300|
|security.user.2fa.timeout|The number of seconds a 2FA challenge token remains valid (in seconds)|300|


## 2FA mode optional
When either the user or guest mode settings are set to `optional` the option to enable 2FA on an individual user account is available.
* **Disabled**<br>2FAis not enabled.
* **Email**<br>2FA is enabled.  Authentication codes are sent to the users by email.

### How to enable 2FA on a user account
1. Using the Configuration search, type the name of the user to be changed to 2FA.
1. In the list of results, select the user name.
1. On the Details tab of the user account, locate the Security Settings section.
1. Under Two-Factor Authentication select `Email'.
1. Save Changes.

### How to enable 2FA on a guest account
1. Using the Configuration search, type `Guest`.
1. In the list of results, click on `Guest Accounts`.
1. In the list of guest accounts, select the account to be changed to 2FA.
1. Click on the Two-Factor Authentication icon in the toolbar.
1. Select `Email`.
1. Select `Save`.
