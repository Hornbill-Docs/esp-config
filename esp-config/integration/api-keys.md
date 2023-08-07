---
layout: article-toc
---
# API keys
An API key is typically used in conjunction with one of Hornbill's pre-built or customer-built integrations and import tools, to enable machine-to-machine authentication where initial integration during setup is required, as well as to remove the need to specify plain text credentials in configuration files that will be located on computers at the point of integration. 

* Click for more details on [API keys](/esp-fundamentals/integration/api-keys)
* Make sure you follow our [API Key Best Practice Guidance](/esp-fundamentals/best-practice/platform-api-keys)

## Creating an API Key
Click on the + button to start creating a new API key.

* **Description**<br>This is a simple description of the API key that is being created
* **State**<br>This defines the current state of the API key. The options are Active, Revoked or Suspended. Any API key that is not in Active state cannot be used.
* **Expires**<br>This defines the date and time until the API key is active. Once the expiry date is reached the API key can no longer be used. This is mandatory, following best security practices.

## Rules
This is a list of Hornbill APIs (https://api.hornbill.com/) that can be used by the API key. You can restrict the use of an API key here by specifying only certain APIs that can be used by the API key.

If no rules are specified, then any API that the API key's associated user account has rights to call, can be called. If one or more rules are defined, only API's that match these rules will be allowed.

Each rule is a simple string that can include DOS-style wildcards. Rules are evaluated until a match is found, if no match is found the API call is rejected.
Here are some examples: -

session:* - will allow any API in the session service
session:getSessionInfo - will allow this API
session:get* - will allow any API whos name starts with 'get' in the session service

apps/com.hornbill.core/* will allow all com.hornbill.core defined API's
apps/com.hornbill.core:addHistory will allow the application defined global API addHistory
apps/com.hornbill.core/Achievement:addAchievement will allow the application defined for entity Achievement

Each rule needs to be in the following format: <service>:<api_name>. Replace <service> and <api_name> with relevant values.
Click on the "Create" button to finish creating the new API key.