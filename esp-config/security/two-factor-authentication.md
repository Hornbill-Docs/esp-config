---
layout: article-toc
---
# Two-factor authentication

Hornbill supports two-factor authentication (2FA) for both user and guest accounts. 

2FA can be made mandatory for every account, made mandatory for individual accounts, or left to be enabled on an account-by-account basis.

Hornbill provides 2FA either via an Emailed code or Authenticator App of the user's choice (For example Microsoft's Authenticator or Google Authenticator) 

## Before you begin
* Hornbill must have an [email domain](/esp-config/email/adding-an-email-domain#creating-an-email-domain) set up for outbound routing
* Users must have a valid email address on their account to use Email 2FA
* 2FA is only applicable to the web apps.  It is not available on the native mobile apps.
* When using SSO, Hornbill 2FA is not used. Instead, 2FA should be set up using your identity provider if the option is available.  This applies to mandatory 2FA as well, making 2FA mandatory in Hornbill does not add a second factor to accounts that sign in through SSO.

## How Two-Factor Authentication Works
With Two-factor Authentication (2fa) enabled, when a user (guest) logs in to Hornbill, they will be prompted to enter a 6-digit authentication code.

The user retrieves this code from an email sent to their account's email address or via the Authenticator App, and uses it to complete the log in process.

![2FA Code](/_books/esp-config/security/images/two-fa.png)

## Settings
2FA settings are set in Advanced System Settings.  

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by part or all of the setting name 
:::

|Name|Description|Default|
|-|-|-|
|security.guest.2fa.timeout|The number of seconds a 2FA challenge token remains valid (in seconds)|300|
|security.user.2fa.timeout|The number of seconds a 2FA challenge token remains valid (in seconds)|300|
|security.guest.2fa.mandatory|When enabled, two-factor authentication is required of every guest contact logging into a portal|false|
|security.user.2fa.mandatory|When enabled, two-factor authentication is required of every user account|false|
|security.guest.2fa.defaultMethod|The method applied to a guest contact that has no 2FA method of its own when 2FA is mandatory.  Either `totp` or `email`|totp|
|security.user.2fa.defaultMethod|The method applied to a user account that has no 2FA method of its own when 2FA is mandatory.  Either `totp` or `email`|totp|

::: tip
Leave the `defaultMethod` settings as `totp` unless every account is known to hold a valid email address.  An account with no email address cannot use Email 2FA, and if it is the mandatory default that account will be unable to log in.
:::

## Making 2FA mandatory
Two-factor authentication can be made mandatory for everyone, or for chosen accounts.  Where 2FA is mandatory the account holder cannot turn it off, and cannot switch to a different method once they have one.

### For every account
1. Using the Configuration search, type `security.user.2fa.mandatory` for user accounts, or `security.guest.2fa.mandatory` for guest contacts.
1. Set the value to `true`.
1. Save Changes.

### For an individual user account
1. Using the Configuration search, type the name of the user.
1. In the list of results, select the user name.
1. On the Details tab of the user account, locate the Security Settings section.
1. Enable `Make two-factor authentication mandatory`.
1. Save Changes.

An account carrying this option is mandatory whether or not `security.user.2fa.mandatory` is enabled, so it can be used to require 2FA of selected people while leaving everyone else free to choose.  There is no equivalent per-contact option for guest contacts, for whom `security.guest.2fa.mandatory` is the whole policy.

### What happens to accounts that have never used 2FA
Making 2FA mandatory does not require you to set a method on each account first.  An account that has no 2FA method of its own is challenged using the relevant `defaultMethod` setting the next time it logs in:

* **Authenticator App** (`totp`, the default) - the account is shown a QR code during login and enrolls the Authenticator App of their choice as part of signing in.  Nothing needs to be held on the account beforehand.
* **Email** (`email`) - a code is sent to the address on the account.  Accounts with no email address cannot log in under this setting.

## Enabling 2FA on individual accounts
Where 2FA is not mandatory, it can be enabled on an individual account.  The available choices are:
* **Disabled**<br>2FA is not enabled.
* **Email**<br>2FA is enabled.  Authentication codes are sent to the users by email.
* **Authenticator App**<br>2FA is enabled.  Authentication codes are available in the Authenticator App of the user.

### How to enable Email 2FA on a user account
1. Using the Configuration search, type the name of the user to be changed to 2FA.
1. In the list of results, select the user name.
1. On the Details tab of the user account, locate the Security Settings section.
1. Under Two-Factor Authentication select `Email`.
1. Save Changes.

### How to enable Email 2FA on a guest account
1. Using the Configuration search, type `Guest`.
1. In the list of results, click on `Guest Accounts`.
1. In the list of guest accounts, select the account to be changed to 2FA.
1. Click on the Two-Factor Authentication icon in the toolbar.
1. Select `Email`.

### How to enable 2FA on the Authenticator App
Unlike Email which can be configured without the user, the Authenticator app requires the user to scan a QR code in the Authenticator app of their choice so must be completed by the user. 
1. Login as the User
1. Go to the Users Profile Settings Authentication tab
1. Change Type to Authenticator App
1. Follow the On Screen prompts to Scan the QR code in your chosen Authenticator App then Enter the One time code in the fields provided

::: tip
Where 2FA is mandatory for an account this tab will not let the user turn 2FA off or move to a different method.  An account that has not yet set a method can still use it to enroll, and a user already using the Authenticator App can still re-scan a QR code to move to a replaced device.
:::
