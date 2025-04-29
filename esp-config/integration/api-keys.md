---
layout: article-toc
---
# API keys
An API key is typically used in conjunction with one of Hornbill's pre-built or customer-built integrations and import tools, to enable machine-to-machine authentication where initial integration during setup is required, as well as to remove the need to specify plain text credentials in configuration files that will be located on computers at the point of integration. 

* Click for more details on [API keys](/esp-fundamentals/security/api-keys/)
* Make sure you follow our [API Key Best Practice Guidance](/esp-fundamentals/best-practice/platform-api-keys)

## Creating an API Key
Click on the + button to start creating a new API key.

* **User Account**<br>The user account under which this API will run under.  The API will inherit the rights of the selected user. The API Key can be restricted further by using rules.
* **Description**<br>This is a simple description of the API key that is being created
* **State**<br>This defines the current state of the API key. The options are Active, Revoked or Suspended. Any API key that is not in an active state cannot be used.
* **Expires**<br>This defines the date and time until the API key is active. Once the expiry date is reached the API key can no longer be used. This is mandatory, following best security practices.  

## API Key Expiry and Auto-Delete
Once an API key has expired, it will automatically be deleted from the system 7 days after the expiry date is reached. 

## API Key Rules
API Key rules are a very flexible scheme that gives you granular control over APIs that can be accessed using any given API key.  

![API Key Rules](/_books/esp-config/images/api-key-rules.png)

Multiple rules can be added, with each rule being placed on a new line.

Learn more about [API Key Rules](/esp-fundamentals/security/api-keys#api-key-security-controls)

::: tip
API Keys can also be viewed or managed from a user account.  Each user account will show any API Key that that have been created under the context of that account.
:::
