---
layout: article-toc
---
# Single sign-on with SAML 2.0
The Hornbill platform supports single sign-on as well as policy-based transparent auto provisioning and data updates of both user and guest accounts thus providing enterprise-class user identity integration with your organizations core IT directory services.

## Topics covered
* Learn about SAML and how it is used by Hornbill
* Setting up meta data
* Configuring your identity provider
* Managing your SSO Certificate

## Before you begin
* Admin access to Hornbill Configuration
* An Identity Provider that supports SAML 2.0

## What is SAML
Security Assertion Markup Language ('SAML, pronounced "sam-el") is an open standard XML-based framework developed by the Security Services Technical Committee of OASIS and is designed for communicating user authentication, entitlement, and attribute information between parties, in particular between an Identity Provider (IdP) and a Service Provider i.e. Hornbill.
:::note
Useful External References:
[Oasis-Open.org](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=security), [Wikipedia](https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language)
:::

## SAML and Hornbill
Hornbill makes use of the SAML framework to facilitate two things:

Single Sign On (SSO) - this is the method of access control that enables a user to log in to their organizations network one time, but then have transparent authorization to access resources of multiple software systems without being prompted to log in to each system separately. In the context of Hornbill, once configured, users may access their Hornbill instance pre-authenticated based on their enterprise desktop or browser login.
Auto-provision Hornbill User Accounts - along with the authorization information needed for SSO, SAML has the ability to transport additional directory attributes of a user. Hornbill is capable of processing this additional information contained in the SAML payload and use it to automatically create a user accounts on your instance. This mechanism can remove a significant overhead in terms of system administration.

:::note
 While SSO must be set up to utilize auto-provisioning, the auto-provisioning of user accounts in Hornbill is an optional mechanism that can be disabled independently of SSO. Hornbill provides a range of user import utilities that can be used instead of auto-provisioning. More information on the available user imports can be found via the following wiki page: Open Integration Tools
:::

## How it Works
There are three key actors in any SAML implementation, these are the "user" trying to access the Hornbill Cloud Application (via their Web Browser), the "Identity Provider (idP)" which knows and has identified the user, and the Service Provider (Hornbill Cloud Service) which provides the application and/or resources that the user wishes to access. Your Hornbill instance is the service provider, and typically your enterprise directory system, very often [Microsoft Active Directory Federated Services (ADFS)](https://learn.microsoft.com/en-us/windows-server/identity/active-directory-federation-services) acts as your identity provider.

![SAML Flow](/_books/esp-config/security/images/saml-flow.png)

Once SSO is configured, when an unauthenticated user navigates to your Hornbill instance via one of the Hornbill URLs, the browser will be re-directed to the identity provider with the information needed to request access to the service, this is known as a SAML AuthnRequest. The idP will look at the AuthnRequest and if the user is authorized will return an Assertion back to the browser with a redirect to the service provider (in this case the Hornbill Instance). The Hornbill instance will validate the Assertion checking its authenticity against a known Hornbill SSO profile and if valid will create a session and allow the user to access Hornbill as required.

## Download the Hornbill Meta data

The Service Provider (Hornbill) meta data files needed for configuring your IdP can be downloaded from your Hornbill instance
In order to successfully configure your Identity Provider (IdP) you will need details of your Hornbill instance. The Service Provider meta data files contain such things as the Service Provider Entity Id and Assertion Consumer Service (ACS) binding that your IdP needs to communicate during the authentication process.

To get your meta data files, log into Hornbill Administration and navigate to Home > system > Security > SSO Profiles. Located towards the top right of the list are buttons labeled "Mobile Catalog", "User", "Admin", "Service", and "Customer". Clicking each of these will download the Hornbill meta data file for the associated Service URL.

USER - contains information for https://live.hornbill.com/[your instance name]
ADMIN - contains information for https://admin.hornbill.com/[your instance name]
MOBILE CATALOG - contains information for https://mcatalog.hornbill.com/[your instance name]
CUSTOMER - contains information for https://customer.hornbill.com/[your instance name]
SERVICE - contains information for https://service.hornbill.com/[your instance name]
This is the URL relating to the Hornbill Service Portal and is due to be retired during 2020. All new implementations of Hornbill do not require this.

What Meta data files do I need to download?
When configuring your IdP, you will need to create entries to represent each of the Hornbill URL's that will be used to access your Hornbill instance and you will need the corresponding meta data files to support the creation of the trusts.

"User" is always necessary. Therefore as a minimum you will have one entry in your IdP.
"Admin" is optional as access can be gained via a link from the user app once successful login has been achieved. However, many choose to configure this in their IdP for added convenience.
"Mobile catalog" is required to facilitate access via a mobile device.
"Customer" represents the self service portal used in the delivery of an external support function. This is only required if you need a portal to provide services to those outside of your organization.

## Configure your Identity Provider
The Hornbill SSO implementation follows the SAML 2.0:2005 specification so will work with any commercial or home-grown identity provider that correctly supports this standard. We have tried to make our system as flexible as possible in terms of configuration and compatibility with the standard. Here is a link to the official standards documentation: - SAML 2.0 2005
The following identity providers are known to have been configured and work with the Hornbill platform (we will expand this list as we integrate successfully with other systems).

* Microsoft Active Directory Federation Services (ADFS 2.0)
* Azure Single Sign On
* Ping Identity
* SSO Circle
* Shibboleth Identity Provider
* OpenAthens (EduServ)

As you might expect, different vendors may use different terminology to describe the configuration required in the IdP but typical examples are "Service Provider Profile" or "Relying Party Trust" (see below for Example IDP configurations and references). It is likely that you will need an entry in your IdP to represent each of the Hornbill Service URL's (i.e. admin, live, and service).
Example IdP Configurations
Microsoft ADFS 2.0
Microsoft Azure - There's a Hornbill app in the Azure Gallery to help with the setup of Hornbill single sign-on using Azure AD as its identity provider.
Information
When creating an Azure Enterprise Application entry for Hornbill, the tutorial provided by Microsoft has the following step:
a. In the Identifier (Entity ID) text box, type a URL using the following pattern:
https://<SUBDOMAIN>.hornbill.com/<INSTANCE_NAME>/lib/saml/auth/simplesaml/module.php/saml/sp/metadata.php/saml
This URL is no longer valid and should be replaced with the following: xxx . Confirmation of the correct URL is available via the metadata accessible within the SSO profile configuration section in the Hornbill admin portal.
We are currently liaising with Microsoft to have this information updated.

IMPORTANT: Although we have expertise around our own platform and its SAML implementation, configuration, and behavior, we use the language associated with the SAML 2.0 standard and not the language/terminology of any specific vendors identity provider platforms. Hornbill's technical staff are not experts with the various identity provider technologies and platforms in use. It is important to understand that Hornbill supports the SAML 2.0 standard to the letter. Each organization's identity provider implementation can be unique to their organization and it will be necessary for you to have someone internally with expertise and a working knowledge of your identity provider and directory services within your own organization. You should refer your technical network expert to this document which should provide them with sufficient information to allow the planning and configuration of Single Sign-On for your organization.

## SSO Certificate Expiry Reminders

Showing the configured state of an SSO profile where certificate time and validity are enabled
Summary
Digital certificates generated and used by your Identity Provider typically have an expiry date. Once a digital certificate has expired, and assuming you have not disabled the Time and Cert valid checks (which you should only ever do for troubleshooting), then you will no longer be able to login using SSO. As it is easily forgotten, your Hornbill instance will run a certificate reminder schedule in advance of your signing certificate expiring, acting as a reminder and prompt for you to update the certificates in your SSO Profile(s).

### How the Schedule Works
The reminder schedule will send email notifications to your registered Primary and Secondary technical contacts, and will follow a schedule defined in “days before expiry” here: -

30 Days – a courtesy notification letting you know that your certificate will expire in 30 days, subject of the message will be “Your Single Sign-On Certificate will expire in 30 days”
15 Days – first reminder, subject of the message will be “ATTENTION: Your Single Sign-On Certificate will expire in 15 days”
7 Days – second reminder, subject of the message will be “WARNING: Your Single Sign-On Certificate will expire in 7 days”
1 Day – final reminder, subject of the message will be “URGENT: Your Single Sign-On Signing Certificate will expire tomorrow”
At any point during this 30-day schedule, your SSO Profile(s) certificates are updated with new ones, this schedule will be reset and you will not receive any further notifications.

The schedule message, subject, and content of the email messages are fixed and not customizable. The email addresses used are those defined as your primary and secondary technical contacts registered against your instance.

### SSO Auto Certificate Renewal

Showing the configured state of an SSO profile with both expired and valid certificates and SSO Auto Certificate Renewal enabled
Summary
In order to eliminate manual administrative overhead, it is possible to configure your Hornbill instance to automatically update the public certificates from your SAML identity provider instead of having to do this manually each time the certificate is renewed on your identity provider.

### Benefit
By configuring this capability, this certificate renewal automation removes the need for any further maintenance of certificates between your Hornbill instance and your Identity Provider, eliminating situations where someone forgets to update a certificate manually causing a loss of access to your instance while a new certificate is applied manually.

### Overview
Many SAML 2.0 Identity providers have a feature whereby the signing certificate used for signing SAML assertions is renewed periodically. When a new certificate is generated, it is typically generated in advance of the expiry date of the currently active certificate creating an overlap period where both the new and the old certificate are active. This gives system administrators time to update any service providers using SSO with the new certificate information.

The policies that control the certificate renewal and overlap periods are defined by the identity provider and beyond the scope of this document, you should see the documentation for the Identity Provider you are using.

### How It works
When configuring Hornbill to use SSO, one of the things you are required to do as part of the SSO configuration is provide your Hornbill instance with the metadata from your Identity Provider, this is typically a URL that when viewed in a browser will return the XML data describing the Identity Provider, its public certificates and so on.

If this is URL is accessible to the Hornbill instance, our servers will periodically look for new certificates from this trusted URL, and a match is found to any registered SSO profile on your instance, and if there are new public key(s), these will be automatically imported into the Hornbill SSO profile, allowing a seamless switch-over from an existing to a new certificate without any service disruption. Conversely, expired certificates are automatically removed from your SSO profile(s).

### Configuring Auto Certificate Renewal
Configuration is as simple as providing the metadata URL and enabling the feature (see image to the right). So long as our servers can reach the metadata page over HTTPS this will just work. There are no special configurations required on your Identity Provider, apart from the assumption that your Identity Provider is auto-renewing its certificates periodically.

### SSO Auto Certificate Renewal and SSO Certificate Expiry Reminders
When you configure automatic certificate renewal, you may or may not get one or more certificate expiry reminder emails, this depends on how your Identity Provider auto certificate renewal policy is set up in relation to the SSO Certificate Expiry Reminder schedule. In practice a certificate renewal occurs somewhere around 20-days prior to the expiry date, as shown in the below example (look at the old cert expiry date and the new cert start date), so in this case, you would receive the first courtesy notification in the SSO Certificate Expiry Reminder schedule, and then 10 days later your certs would be renewed, and you would not receive any further notifications. However, each setup is different so if you start to receive the warning or urgent notifications while you have auto certificate renewal enabled, you should investigate further.

### Expired Certificate Auto Deletion
Certificates that have expired are marked as "expired" and will be displayed in red to indicate this, and are no longer used for verification. Expired certificates are left on the SSO profile for 180 days, after which time, the expired certificates are automatically, and permanently deleted from the SSO profile.

## Configure a Single Sign On Profile in Hornbill
The final step in setting up SSO for Hornbill is to create a Single Sign On Profile in your Hornbill instance. The following page will provide detail on how to complete this step: Configuring a Single Sign On Profile in Hornbill.

## Enabling Single Sign On in your Web Browser
Depending on your policy, it may be necessary to make changes to your browser settings to ensure a seamless SSO experience. The following page outlines the steps for some common browsers: Enabling Single Sign On in Your Web Browser.

## Troubleshooting Single Sign On
Hornbill's Single Sign On implementation is designed to present you with helpful error messages in situations where something may not be quite right. For information in relation common scenarios and what to do to overcome them please see the following page: Troubleshooting Single Sign On.

## Preparing for Auto-Provisioning (Optional)
The necessary configuration to facilitate auto-provisioning can be considered a small extension of the Single Sign On configuration. In the case where only SSO is needed, there is a single one-to-one mapping between the Hornbill User ID and the "nameID" returned in the SAML communication that identifies the user, typically this is tied into the users login ID. For Hornbill to successfully auto-provision a user account, it will be necessary to specify additional information to be transported in the outgoing claim from your Identity Provider. This information is carried in the additional attributes that are transported during the authentication of a user.

Obvious information such as first name, last name and e-mail address would be especially important when creating a Hornbill user account, but you may wish to bring over other information into the Hornbill instance at the point of auto-provisioning.

### Hornbill User Account Properties
The Hornbill instance understands a definitive set of user account target properties. The available properties can be used as a starting point in determining what information you wish to bring into Hornbill via your IDP for auto-provisioning. For each user account property you wish to populate in Hornbill, you will need a directory attribute configured in the outgoing claim coming from your iDP. The mapping is defined in the Hornbill Single Sign On Profile The following table lists the user account properties that can be populated during auto-provisioning.

Name	Required	Description
account:name	No	The users display name/handle. If not specified then the name will be derived from account:firstName a space and the account:lastName. If these two attributes are not defined either, the name will be the same as the nameID (the users login id)
account:firstName	No	The users given/first name
account:lastName	No	The users given/last name
account:jobTitle	No	The users job title within the organization
account:phone	No	The users phone number
account:email	No	The users e-mail address
account:mobile	No	The users mobile phone number
account:availabilityStatus	No	The users availability status - there is generally not a good mapping for this so you would not normally include it
account:availabilityMessage	No	The users availability message - there is generally not a good mapping for this so you would not normally include it
account:timeZone	No	The users timezone, see the list of supported times zones in Hornbill Administration
account:language	No	The users language, see the list of supported languages in Hornbill Administration
account:dateTimeFormat	No	The users dateTime format, see the API documentation for admin::userCreate for the format information
account:dateFormat	No	The users date format, see the API documentation for admin::userCreate for the format information
account:timeFormat	No	The users time format, see the API documentation for admin::userCreate for the format information
account:currencySymbol	No	The users default currency symbol
account:countryCode	No	The users country code
Auto-provisioning User Templates
If you have chosen to use auto-provisioning, you may want to explore the creation of an auto-provisioning User Template in Hornbill. Details can be found at the following page: Auto Provisioning User Templates.
Hornbill Contact Record (Guest) Properties
Like Hornbill user accounts, contact records can be created through auto-provisioning. The following table lists the contact record properties that can be populated during auto-provisioning.

Name	Required	Description
contact:firstName	No	The users given/first name
contact:lastName	No	The users given/last name
contact:jobTitle	No	The users job title within the organization
contact:phone	No	The users phone number
contact:email	No	The users e-mail address
contact:company	No	The name of the company the user works at
contact:timeZone	No	The users timezone, see the list of supported times zones in Hornbill Administration
contact:language	No	The users language, see the list of supported languages in Hornbill Administration
contact:countryCode	No	The users country code
Auto-provisioning Contact (Guest) Templates
If you have chosen to use auto-provisioning, you may want to explore the creation of an auto-provisioning Contact (Guest) Template in Hornbill. Details can be found at the following page: Auto Provisioning Guest Account Templates.