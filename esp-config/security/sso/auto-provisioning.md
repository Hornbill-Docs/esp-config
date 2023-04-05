---
layout: article-toc
---
# Auto-Provisioning User Accounts
## Preparing for Auto-Provisioning (Optional)
The necessary configuration to facilitate auto-provisioning can be considered a small extension of the Single Sign On configuration. In the case where only SSO is needed, there is a single one-to-one mapping between the Hornbill User ID and the "nameID" returned in the SAML communication that identifies the user, typically this is tied into the users login ID. For Hornbill to successfully auto-provision a user account, it will be necessary to specify additional information to be transported in the outgoing claim from your Identity Provider. This information is carried in the additional attributes that are transported during the authentication of a user.

Obvious information such as first name, last name and e-mail address would be especially important when creating a Hornbill user account, but you may wish to bring over other information into the Hornbill instance at the point of auto-provisioning.

### Hornbill User Account Properties
The Hornbill instance understands a definitive set of user account target properties. The available properties can be used as a starting point in determining what information you wish to bring into Hornbill via your IDP for auto-provisioning. For each user account property you wish to populate in Hornbill, you will need a directory attribute configured in the outgoing claim coming from your iDP. The mapping is defined in the Hornbill Single Sign On Profile The following table lists the user account properties that can be populated during auto-provisioning.

|Name|Required|Description|
|-|-|-|
|account:name|No|The users display name/handle. If not specified then the name will be derived from account:firstName a space and the account:lastName. If these two attributes are not defined either, the name will be the same as the nameID (the users login id)|
|account:firstName|No|The users given/first name|
|account:lastName|No|The users given/last name|
|account:jobTitle|No|The users job title within the organization|
|account:phone|No|The users phone number|
|account:email|No|The users e-mail address|
|account:mobile|No|The users mobile phone number|
|account:availabilityStatus|No|The users availability status - there is generally not a good mapping for this so you would not normally include it|
|account:availabilityMessage|No|The users availability message - there is generally not a good mapping for this so you would not normally include it|
|account:timeZone|No|The users timezone, see the list of supported times zones in Hornbill Administration|
|account:language|No|The users language, see the list of supported languages in Hornbill Administration|
|account:dateTimeFormat|No|The users dateTime format, see the API documentation for admin::userCreate for the format information|
|account:dateFormat|No|The users date format, see the API documentation for admin::userCreate for the format information|
|account:timeFormat|No|The users time format, see the API documentation for admin::userCreate for the format information|
|account:currencySymbol|No|The users default currency symbol|
|account:countryCode|No|The users country code|

### Auto-provisioning User Templates
If you have chosen to use auto-provisioning, you may want to explore the creation of an auto-provisioning User Template in Hornbill. Details can be found at the following page: Auto Provisioning User Templates.

### Hornbill Contact Record (Guest) Properties
Like Hornbill user accounts, contact records can be created through auto-provisioning. The following table lists the contact record properties that can be populated during auto-provisioning.

|Name|Required|Description|
|-|-|-|
|contact:firstName|No|The users given/first name|
|contact:lastName|No|The users given/last name|
|contact:jobTitle|No|The users job title within the organization|
|contact:phone|No|The users phone number|
|contact:email|No|The users e-mail address|
|contact:company|No|The name of the company the user works at|
|contact:timeZone|No|The users timezone, see the list of supported times zones in Hornbill Administration|
|contact:language|No|The users language, see the list of supported languages in Hornbill Administration|
|contact:countryCode|No|The users country code|

### Auto-provisioning Contact (Guest) Templates
If you have chosen to use auto-provisioning, you may want to explore the creation of an auto-provisioning Contact (Guest) Template in Hornbill. Details can be found at the following page: Auto Provisioning Guest Account Templates.