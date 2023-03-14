---
layout: article-toc
---
# Two factor authentication

Hornbill supports two-factor authentication for both user and guest accounts. Two factor authentication (2FA) can be enabled by the system administrator to either force 2FA for all accounts, or to allow 2FA to be required on an account-by-account basis.

::: note
When using SSO, Hornbill 2FA is not used, instead your identity provider should provide the 2FA capability should that be required.
:::

To enable 2fA for users using Hornbill Direct Login

Search the admin area for "2fa user", and configure the two settings according to your preferences. Chose 'optional' mode if you want to enabled 2FA on an account by account basis. Chose 'required' mode if you want to make 2FA mandatory for all accounts globally.
If you have chosen 'optional' mode, you will need to go into each user account you wish to enable 2FA for, and in the Details tab, scroll down to the 2 Factor Authentication field, and choose Enabled
To enable 2fA for guests using Hornbill Direct Login

Search the admin area for "2fa guest", and configure the two settings according to your preferences. Chose 'optional' mode if you want to enabled 2FA on an account by account basis (t.b.a). Chose 'required' mode if you want to make 2FA mandatory for all accounts globally.
If you have chosen 'optional' mode, you will need to go into the guest accounts list, select the account(s) and press the 2FA button (the shield with tick icon), to set the 2FA mode for that account(s).

## How Two-Factor Authentication Works
When enabled, if a user (guest) logs in using direct login with their normal credentials, instead of being logged in, the login page will change and prompt with instructions to enter a 6-digit authentication code. This authentication code will be sent to the user (or guest) account using their primary email address, the email will look similar to the image below. Simply type that code when prompted to complete the second phase of the authentication and the user (guest) will be logged in as usual.