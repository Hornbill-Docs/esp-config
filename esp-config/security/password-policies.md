---
layout: article-toc
---
# Password policies
The password policy settings allow you to enforce a number of options for requirements when creating a new password for a user account.

## Where password policies are used
* Password policies only apply to user accounts, and not external guest accounts (contacts)
* When a user tries to manually change their password on their profile
* The LDAP user import automatically creates passwords using a built-in password generator that follows these policies
* Hornbill policies are not applied when using Single sign-on (SSO). Identity providers used for SSO should provide their own policies.

## Settings
All of Hornbill's password policies are managed through settings.

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by part or all of the setting name 
:::

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

::: note
***Blacklists**:  Lists of the top hacked or most commonly used passwords are provided by SplashData, NordPass, and Imperva. These lists are maintained by Hornbill, and will be periodically updated as new lists are provided.  
:::