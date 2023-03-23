---
layout: article-toc
---
# Two-factor authentication

Hornbill supports two-factor authentication (2FA) for both user and guest accounts. 2FA can be enabled by the system administrator to either force 2FA for all accounts, or to allow 2FA to be required on an account-by-account basis.

## Before you begin
* Hornbill must have an [email domain](/esp-config/email/adding-an-email-domain#creating-an-email-domain) set up for outbound routing
* Users must have a valid email address setup on their account
* 2FA is only applicable to the web apps.  It is not available on the native mobile apps.
* When using SSO, Hornbill 2FA is not used. Instead, 2FA should be set up using your identity provider if the option is available.

## How Two-Factor Authentication Works
When enabled, if a user (guest) logs in using direct login with their normal credentials, instead of being logged in, the login page will change and prompt with instructions to enter a 6-digit authentication code. This authentication code will be sent to the user (guest) account using their primary email address, the email will look similar to the image below. Simply type that code when prompted to complete the second phase of the authentication and the user (guest) will be logged in as usual.

![2FA Code](/_books/esp-config/security/images/2fa.png)

## Settings
Enabling 2FA is done using platform settings.  

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by part or all of the setting name 
:::

|Name|Description|Default|
|-|-|-|
|security.guest.2fa.mode|Sets the Two-Factor Authentication Mode: `disabled` - not enabled, `optional` - enabled on an account-by-account basis, `mandatory` - forced on all accounts|disabled|
|security.guest.2fa.timeout|The number of seconds a 2FA challenge token remains valid (in seconds)|300|
|security.user.2fa.mode|Sets the Two-Factor Authentication Mode: `disabled` - not enabled, `optional` - enabled on an account-by-account basis, `mandatory` - forced on all accounts|disabled|
|security.user.2fa.timeout|The number of seconds a 2FA challenge token remains valid (in seconds)|300|


## 2FA mode optional
When either the user or guest mode settings are set to `optional` the option to enable 2FA on an individual user account becomes available.
* **Disabled**<br>2FA will not be used
* **Email**<br>2FA will be enabled and sent to the user by email

### How to enable 2FA on a user account
1. Using Configuration search using the name of the user to be changed to 2FA
1. In the results list, click on the user name
1. On the Details tab of the user account, locate the Security Settings section
1. Under Two-Factor Authentication select `Email'
1. Click on `Save Changes`

### How to enable 2FA on a guest account
1. Using Configuration search on the text `Guest`
1. In the results list, click on `Guest Accounts`
1. In the list of guest accounts, select the account to be changed to 2FA
1. Click on the Two-Factor Authentication icon in the toolbar
1. Select `Email`
1. Click `Save`