---
layout: article-toc
---
# KeySafe
Hornbill KeySafe provides secure encrypted storage for various types of authentication. Keysafe entries will store authentication methods and credentials to the vast number of external integrations that Hornbill provides.

## Before you begin
* Admin access or a user that has a role that contains the `manageKeysafe` right.
* Knowledge of designing workflows and using the Cloud Integration node.

## How KeySafe is used
* Use a KeySafe entry from within a BPM Workflow to automate updates to integrated apps.
* Use a KeySafe entry from within an Auto Task to trigger updates to integrated apps via a custom button.
* Use a KeySafe entry with ITOM to authenticate with external integrated apps.
* Centralize authentication to integrated apps to prevent having to share credential with other users
* Update authentication credentials in a single location when password changes occur.

## Credential Types
Hornbill KeySafe supports a number of credentials types. External services and cloud applications that Hornbill integrates with are listed here. Also available are some generic types HTTP Basic or APIKey.

* **Cloud Integrations**<br>The `Type` list includes many predefined services that Hornbill integrates with. Each of these types contain attributes that are required to authenticate to that service. If you are looking to integrate with an external service, check first to see if there is a type available for that service.
* **API Key**
* **HTTP Basic**