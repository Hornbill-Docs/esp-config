---
layout: article-toc
---
# Configuring Single Sign-On Profiles
The Hornbill platform supports single sign-on as well as policy-based transparent auto provisioning and data updates of both user and guest accounts thus providing enterprise-class user identity integration with your organizations core IT directory services.

## Topics covered
- Setting up meta data
- Configuring your identity provider
- Managing your SSO Certificate

## Before you begin
- Make sure you read and understand the [Understanding Single Sign-On (SSO) in Hornbill](/esp-fundamentals/security/single-sign-on)
- Admin access to Hornbill Configuration
- An Identity Provider that supports SAML 2.0

## Accessing Single Sign-On Profiles
- Open Configuration and search for `sso` and select `SSO Profiles` from the results
 
## Download the Hornbill SSO Meta data

The Service Provider (Hornbill) meta data files needed for configuring your IdP can be downloaded from your Hornbill instance.  In order to successfully configure your Identity Provider (IdP) you will need details of your Hornbill instance. The Service Provider meta data files contain such things as the Service Provider Entity Id and Assertion Consumer Service (ACS) binding that your IdP needs to communicate during the authentication process.

To get your Hornbill instance meta data files, log into Hornbill Administration and navigate to Home > system > Security > SSO Profiles. Located towards the top left of the list are buttons labeled __User__ and __Mobile Catalog__. Clicking each of these will download the Hornbill meta data file for the associated Service URL.

- __USER__<br>Contains information for https://live.hornbill.com/[your instance name]
- __MOBILE CATALOG__<br>Contains information for https://mcatalog.hornbill.com/[your instance name]

![Download SAML Metadata](/_books/esp-config/security/images/saml-metadata.png)

### Manually configuring your IdP
Sometimes your IdP will require manual configuration.  In this case you should use the values provided in the __SAML Properties (manual configuration)__ information.

* Entity ID 
* Reply URL
* Sign-On URL

![Download SAML Metadata](/_books/esp-config/security/images/saml-manual-config-props.png)

## Configure your Identity Provider
The Hornbill SSO implementation follows the [SAML 2.0:2005](https://saml.xml.org/saml-specifications) specification so will work with any commercial or internally developed identity provider that correctly supports this standard. We have tried to make Hornbill as flexible as possible in terms of configuration and compatibility with the standard. 

Here is a link to the official standards documentation: [SAML 2.0:2005](https://saml.xml.org/saml-specifications)


![Download SAML Metadata](/_books/esp-config/security/images/saml-config.png)


The following identity providers are known to have been configured and work with the Hornbill platform (we will expand this list as we integrate successfully with other systems).

* Microsoft Active Directory Federation Services (ADFS 2.0)
* Azure Single Sign On
* Ping Identity
* SSO Circle
* Shibboleth Identity Provider
* OpenAthens (EduServ)

As you might expect, different vendors may use different terminology to describe the configuration required in the IdP but typical examples are "Service Provider Profile" or "Relying Party Trust" (see below for Example IDP configurations and references). It is likely that you will need an entry in your IdP to represent each of the Hornbill Service URL's (i.e. admin, live, and service).

### Example IdP Configurations
* Microsoft ADFS 2.0
* Microsoft Azure - There's a Hornbill app in the Azure Gallery to help with the setup of Hornbill single sign-on using Azure AD as its identity provider.

:::note
When creating an Azure Enterprise Application entry for Hornbill, the tutorial provided by Microsoft has the following step:<br><br>
`In the Identifier (Entity ID) text box, type a URL using the following pattern:
https://<SUBDOMAIN>.hornbill.com/<INSTANCE_NAME>/lib/saml/auth/simplesaml/module.php/saml/sp/metadata.php/saml`<br><br>
This URL is no longer valid and should be replaced with the following: xxx . Confirmation of the correct URL is available via the metadata accessible within the SSO profile configuration section in the Hornbill admin portal. We are currently liaising with Microsoft to have this information updated.
:::

## SSO Certificate Expiry Reminders

Digital certificates generated and used by your Identity Provider typically have an expiry date. Once a digital certificate has expired, and assuming you have not disabled the Time and Cert valid checks (which you should only ever do for troubleshooting), then you will no longer be able to login using SSO. As it is easily forgotten, your Hornbill instance will run a certificate reminder schedule in advance of your signing certificate expiring, acting as a reminder and prompt for you to update the certificates in your SSO Profile(s).

Read more about [how the reminder schedule works](/esp-fundamentals/security/single-sign-on#sso-digital-certificates) here.


## SSO Auto Certificate Renewal

In order to eliminate manual administrative overhead, it is possible to configure your Hornbill instance to automatically update the public certificates from your SAML identity provider instead of having to do this manually each time the certificate is renewed on your identity provider.

Read more about [how SSO Auto Certificate Renewals Work](/esp-fundamentals/security/single-sign-on#sso-auto-certificate-renewal) here.

:::note
Expired SSO certificates stored in the SSO profile on your Hornbill instance are automatically removed 30 days after their expiry, if, a newer certificate has already been imported. 
:::

### Configuring Auto Certificate Renewal
Configuration is as simple as providing the metadata URL and enabling the feature. So long as our servers can reach the metadata page over HTTPS this should just work. There are no special configurations required on your Identity Provider, apart from the assumption that your Identity Provider is auto-renewing its certificates periodically.  You can also test this import manually by pressing the reload button to the right of the URL.  You also need to make sure that the '''Auto Update Certificates''' option of your SSO profile is turned on. 

### SSO Auto Certificate Renewal and SSO Certificate Expiry Reminders
When you configure automatic certificate renewal, you may or may not get one or more certificate expiry reminder emails, this depends on how your Identity Provider auto certificate renewal policy is set up in relation to the [SSO Certificate Expiry Reminder Schedule](/esp-fundamentals/security/single-sign-on#how-the-schedule-works). In practice a certificate renewal occurs somewhere around 20-days prior to the expiry date, as shown in the below example (look at the old cert expiry date and the new cert start date), so in this case, you would receive the first courtesy notification in the SSO Certificate Expiry Reminder schedule, and then 10 days later your certs would be renewed, and you would not receive any further notifications. However, each setup is different so if you start to receive the warning or urgent notifications while you have auto certificate renewal enabled, you should investigate further.

### Expired Certificate Auto Deletion
Certificates that have expired are marked as "expired" and will be displayed in red to indicate this, and are no longer used for verification. Expired certificates are left on the SSO profile for 180 days, after which time, the expired certificates are automatically, and permanently deleted from the SSO profile.

:::tip
When auto certificate renewal is enabled, Hornbill will check for new certificates once ever 24 hours. You can check this manually at any time by pressing the reload button here:
![SAML Metadata Reload](/_books/esp-config/security/images/sso-cert-check.png)
:::


## SSO Troubleshooting and Common Issues
Hornbill's Single Sign On implementation is designed to present you with helpful error messages in situations where something may not be quite right. 

### The public certificate used for signing the assertion is not known to the service provider
A common cause of this error message is that the signing certificate stored in your Identity provider has been renewed and therefore no longer matches the SSO certificate you have stored in Hornbill against your SSO profile. Some Identity Providers automatically renew signing certificates periodically. This specific error message indicates that the signing certificate given to Hornbill by your identity provider does not match any of the certificates currently stored in the Hornbill SSO Profile. This can be rectified by uploading a new certificate key to the Hornbill SSO Profile or enabling Auto Certificate Renewal.

### Unable to Validate User Credentials
This error occurs when Hornbill was unable to find a match for the user information sent from the identity provider. When the identity provider successfully authenticates a user, it sends information to Hornbill which Hornbill processes to determine which user account to use in order to establish a session for that user (i.e. log them in).

#### Things to check
There are several possible reasons for this error:

- The user that has been successfully authenticated does not have a Hornbill user account.
- The solution here is to create a Hornbill user account for this user. However, it's important to understand why one did not exist as it could indicate a problem with a user import.
- The Hornbill user account is either archived or suspended.
- The solution is to set the status of the account to active. However it's important to understand - why the account was suspended or archived as this may be intentional or could indicate a problem with a user import.
- The Unique Identifier sent from your Identity Provider does not match what is stored in the Logon ID field of the Hornbill User Account.
- The unique user identifier being sent from the Identity Provider must match the Logon ID of a Hornbill user account.
- The Unique Identifier is configurable in the Identity Provider. The unique identifier will be a unique directory attribute such as "userPrincipleName". The attribute used can vary between identity providers so it will be necessary for you to understand what is being sent to Hornbill. This is usually configurable in the section responsible for the "user attributes and claims" (again, exactly where this is configured will depend on your identity provider).
Alternatively, align the Logon ID field of all user accounts to match what your identity provider is sending. For more information on creating and managing users, including Hornbill user account properties, begin at the following page: Users


