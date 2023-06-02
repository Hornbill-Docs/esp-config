---
layout: article-toc
---
# Password policies
The password policy settings enforce a number of requirements when creating or updating a password for a user account. 

## Where password policies are applied
* All user and guest account (contact) authentication.
* When a user tries to manually change their password on their profile.
* During LDAP user import, a built-in password generator creates passwords that use these policies.

:::tip
Hornbill policies are not applied when using Single sign-on (SSO). Identity providers used for SSO should provide their own policies.
:::

## Settings
Hornbill's password policies are managed through the Password Policy settings.

To make changes to a Policy, update the settings.

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by part or all of the setting name. 
:::

### User Password Policy Settings
|Name|Description|Default|
|-|-|-|
|security.user.passwordPolicy.checkBlacklists|Checks the password blacklists* to make sure the password is not excluded form use on this system|Off|
|security.user.passwordPolicy.checkPersonalInfo|Checks to make sure that the password does not contain the users ID or name|Off|
|security.user.passwordPolicy.minimumLength|The minimum length a password must be. Set to ZERO to disable minimum length enforcement|8|
|security.user.passwordPolicy.mustContainLowerCase|The minimum number of lower case letters a password should contain|0|
|security.user.passwordPolicy.mustContainNumeric|The minimum number of numeric characters a password should contain|0|
|security.user.passwordPolicy.mustContainSpecial|The minimum number of special characters a password should contain. A special character is anything that is not [a-z][A-Z][0-9]|0|
|security.user.passwordPolicy.mustContainUpperCase|The minimum number of upper case letters a password should contain|0|
|security.user.passwordPolicy.passwordBlockHistoricCount|The number of previous passwords to store and check when setting a new password.|10|
|security.user.passwordPolicy.passwordExpires|The number of days a password should expire after being set. If set to ZERO (0) then the password does not expire|0|
|security.user.passwordPolicy.passwordMinimumAge|The number of days a password once set must be used before it can be changed again. If set to ZERO (0) then it can be changed any time|0|
|security.user.passwordPolicy.requireOldPasswordForReset|If set to true, a user must enter their old password in order to be able to reset their password|On|
|security.user.passwordPolicy.userResetResponseTimeout|The number of seconds a user initiated password reset request token remains valid.|86400|

### Guest Password Policy Settings
|Name|Description|Default|
|-|-|-|
|security.guest.passwordPolicy.checkBlacklists|Checks the password blacklists* to make sure the password is not excluded form use on this system|Off|
|security.guest.passwordPolicy.checkPersonalInfo|Checks to make sure that the password does not contain the users ID or name|Off|
|security.guest.passwordPolicy.minimumLength|The minimum length a password must be. Set to ZERO to disable minimum length enforcement|8|
|security.guest.passwordPolicy.mustContainLowerCase|The minimum number of lower case letters a password should contain|0|
|security.guest.passwordPolicy.mustContainNumeric|The minimum number of numeric characters a password should contain|0|
|security.guest.passwordPolicy.mustContainSpecial|The minimum number of special characters a password should contain. A special character is anything that is not [a-z][A-Z][0-9]|0|
|security.guest.passwordPolicy.mustContainUpperCase|The minimum number of upper case letters a password should contain|0|
security.guest.passwordPolicy.userResetResponseTimeout|The number of seconds a guest initiated password reset request token remains valid. The default value is 24 hours (86400)|86400|

::: note
***Blacklists**:  Lists of the top hacked or most commonly used passwords are provided by SplashData, NordPass, and Imperva. These lists are maintained by Hornbill, and will be periodically updated as new lists are provided.  
:::