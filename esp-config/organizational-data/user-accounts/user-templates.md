---
layout: article-toc
---
# User templates
User templates are used to create a standard set of settings which can then be used to create user accounts through auto provisioning or when users are manually created. An example of using an identity provider would be to use Active Directory Services to authenticate with Hornbill. When this authentication happens, if a user account does not exist in Hornbill it will be automatically created using this template.

## Basic Information
* **Template Name**<br>More than one template can be created. This will allow you to identify this particular template within the list of templates. When manually adding new users, these template names can be seen under the Create New User button.
* **Type**<br>Select if the the new account will be a Basic or full User account

## Location
* **Site**<br>Select the Site where the user will be located
* **Country**<br>The country where the user is located

## Regional Settings

* **Language**<br>This will set the language for the user. The language set against the user will determine the language that is presented to them.
* **Timezone**<br>This will set the timezone that the user resides in. This will ensure that date/time information presented to them is displayed using their time.
* **Date/Time Format**<br>Set the format for how date/time information will be presented to the user
* **Date Format**<br>Set the format for how date information will be presented to the user
* **Time Format**<br>Set the format for how time information will be presented to the user

## Security Settings
* **Roles**<br>Select the roles to be automatically assigned to the account on creation.