---
layout: article-toc
---
# Single Sign-On with SAML 2.0

## Topics covered
* Learn about SAML and how it is used by Hornbill

## What is SAML
Security Assertion Markup Language ('SAML, pronounced "sam-el") is an open standard XML-based framework developed by the Security Services Technical Committee of OASIS and is designed for communicating user authentication, entitlement, and attribute information between parties, in particular between an Identity Provider (IdP) and a Service Provider i.e. Hornbill.
:::note
Useful External References:
[Oasis-Open.org](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=security), [Wikipedia](https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language)
:::

## SAML and Hornbill
Hornbill makes use of the SAML framework to facilitate two things:

* **Single Sign On (SSO)**<br>This is the method of access control that enables a user to log in to their organizations network one time, but then have transparent authorization to access resources of multiple software systems without being prompted to log in to each system separately. In the context of Hornbill, once configured, users may access their Hornbill instance pre-authenticated based on their enterprise desktop or browser login.
* **Auto-provision Hornbill User Accounts**<br>Along with the authorization information needed for SSO, SAML has the ability to transport additional directory attributes of a user. Hornbill is capable of processing this additional information contained in the SAML payload and use it to automatically create a user account on your instance. This mechanism can remove a significant overhead in terms of system administration.

:::note
 While SSO must be set up to utilize auto-provisioning, the auto-provisioning of user accounts in Hornbill is an optional mechanism that can be disabled independently of SSO. Hornbill provides a range of user import utilities that can be used instead of auto-provisioning. More information on the available user imports can be found via the following wiki page: Open Integration Tools
:::

## How it Works
There are three key actors in any SAML implementation, these are the "user" trying to access the Hornbill Cloud Application (via their Web Browser), the "Identity Provider (idP)" which knows and has identified the user, and the Service Provider (Hornbill Cloud Service) which provides the application and/or resources that the user wishes to access. Your Hornbill instance is the service provider, and typically your enterprise directory system, very often [Microsoft Active Directory Federated Services (ADFS)](https://learn.microsoft.com/en-us/windows-server/identity/active-directory-federation-services) acts as your identity provider.

![SAML Flow](/_books/esp-config/security/images/saml-flow.png)

Once SSO is configured, when an unauthenticated user navigates to your Hornbill instance via one of the Hornbill URLs, the browser will be re-directed to the identity provider with the information needed to request access to the service, this is known as a SAML AuthnRequest. The idP will look at the AuthnRequest and if the user is authorized will return an Assertion back to the browser with a redirect to the service provider (in this case the Hornbill Instance). The Hornbill instance will validate the Assertion checking its authenticity against a known Hornbill SSO profile and if valid will create a session and allow the user to access Hornbill as required.