---
layout: article-toc
---
# Configuring Single Sign-On
The Hornbill platform supports single sign-on as well as policy-based transparent auto provisioning and data updates of both user and guest accounts thus providing enterprise-class user identity integration with your organizations core IT directory services.

## Topics covered
* Setting up meta data
* Configuring your identity provider
* Managing your SSO Certificate

## Before you begin
* Admin access to Hornbill Configuration
* An Identity Provider that supports SAML 2.0

## Download the Hornbill Meta data

The Service Provider (Hornbill) meta data files needed for configuring your IdP can be downloaded from your Hornbill instance
In order to successfully configure your Identity Provider (IdP) you will need details of your Hornbill instance. The Service Provider meta data files contain such things as the Service Provider Entity Id and Assertion Consumer Service (ACS) binding that your IdP needs to communicate during the authentication process.

To get your meta data files, log into Hornbill Administration and navigate to Home > system > Security > SSO Profiles. Located towards the top right of the list are buttons labeled "Mobile Catalog", "User", "Service", and "Customer". Clicking each of these will download the Hornbill meta data file for the associated Service URL.

* **USER**<br>Contains information for https://live.hornbill.com/[your instance name]
* **MOBILE CATALOG**<br>Contains information for https://mcatalog.hornbill.com/[your instance name]
* **CUSTOMER**<br>Contains information for https://customer.hornbill.com/[your instance name]

### What Meta data files do I need to download?
When configuring your IdP, you will need to create entries to represent each of the Hornbill URL's that will be used to access your Hornbill instance and you will need the corresponding meta data files to support the creation of the trusts.

* **User**<br>This is always necessary. Therefore as a minimum you will have one entry in your IdP.
* **Mobile catalog**<br>This is required to facilitate access via a mobile device.
* **Customer**<br>This represents the self service portal used in the delivery of an external support function. This is only required if you need a portal to provide services to those outside of your organization.

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

Showing the configured state of an SSO profile where certificate time and validity are enabled
Summary
Digital certificates generated and used by your Identity Provider typically have an expiry date. Once a digital certificate has expired, and assuming you have not disabled the Time and Cert valid checks (which you should only ever do for troubleshooting), then you will no longer be able to login using SSO. As it is easily forgotten, your Hornbill instance will run a certificate reminder schedule in advance of your signing certificate expiring, acting as a reminder and prompt for you to update the certificates in your SSO Profile(s).

### How the Schedule Works
The reminder schedule will send email notifications to your registered Primary and Secondary technical contacts, and will follow a schedule defined in “days before expiry” here: -

* **30 Days**<br>A courtesy notification letting you know that your certificate will expire in 30 days, subject of the message will be “Your Single Sign-On Certificate will expire in 30 days”
* **15 Days**<br>First reminder, subject of the message will be “ATTENTION: Your Single Sign-On Certificate will expire in 15 days”
* **7 Days**<br>Second reminder, subject of the message will be “WARNING: Your Single Sign-On Certificate will expire in 7 days”
* **1 Day**<br>Final reminder, subject of the message will be “URGENT: Your Single Sign-On Signing Certificate will expire tomorrow”

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

