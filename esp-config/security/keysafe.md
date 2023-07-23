---
layout: article-toc
---
# KeySafe
Hornbill KeySafe provides secure encrypted storage for various types of authentication credentials, API keys and certificates. KeySafe records store credentials and different record types implement specific authentication schemes used by Hornbill's integration, automation and data import capabilities.

Go here for more detailed explanation of [KeySafe](/esp-fundamentals/security/keysafe)

## Before you begin
* Admin access or a user that has a role that contains the `manageKeysafe` right.
* Knowledge of Hornbill integrations, API usage, workflows and auto tasks.

## How KeySafe is used
KeySafe acts like a system-wide credentials manager for a wide range of integrations, connections and automation functions including: - 

* Cloud integrations within Hornbill Workflow and Auto Tasks.
* ITOM modules that require credentials
* Email Integrations that require OAuth configurations and setup
* External/custom integrations, import tools and anything else connecting to a third-party where machine-to-machine authentication and security is required. 

## Credential Types
Hornbill KeySafe implements a large number of pre-created credential Types. External services and cloud applications that Hornbill integrates with are implemented. When creating a new KeySafe record, you choose the type you want to create and the correct fields and/or user interface will be presented for you to complete.

### Generic KeySafe Types
To support authentication to external systems, generic authentication types are provided to allow KeySafe entries for integration outside of the provided specific KeySafe types.

* **API Key**<br>Authentication that requires an authentication key to make a secure connection.
* **oAuth 2.0**<br>Create an entry that uses standard oAuth 2.0 authentication.
* **HTTP Basic Authentication**<br>Connect using basic HTTP authentication using a user name and password.
* **HTTP Digest Authentication**<br>Connect with a user name and password, but with added security over basic authentication.
* **Database Authentication**<br>Connect to a database system such as Microsoft SQL.
* **User name + Password + Pre-shared key**<br>Basic username and password authentication with an added security of a pre-shared key.
* **SSH Private Key**<br>Uses two related keys, a public key and a private key, that together create a key pair that is used as the secure access credential.

### Service Specific KeySafe Types
The `Type` list includes many predefined services that Hornbill integrates with. Each of these types contains attributes that are required to authenticate to that service. If you are looking to integrate with an external service, check first to see if there is a type available for that service.

## Using KeySafe in a Workflow
Using KeySafe entries as part of a business workflow is a great way to securely connect to external services.

This is achieved using the Cloud Automation node in a workflow

1. Open the properties of the Cloud Automation node.
1. On the `Method` field select the edit icon.
1. Browse the list of services and select an action that you would like to perform.
1. Under `Request Credentials` select an existing KeySafe entry that will be used to authenticate to the service.

<!-- To Do -->
<!-- Images for Cloud Automation Node -->
<!-- Something about Hornbill Automation -->
<!-- Example how a KeySafe entry is used on imports -->

<!-- References -->
<!-- https://wiki.hornbill.com/index.php?title=KeySafe -->