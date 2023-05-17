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
* Centralize authentication to integrated apps to prevent having to share credential with other users.
* Use KeySafe to store credentials to connect to LDAP Servers and Azure AD for user imports into Hornbill.
* Update authentication credentials in a single location when password changes occur.

## Credential Types
Hornbill KeySafe supports a number of credentials types. External services and cloud applications that Hornbill integrates with are listed here. Also available are some generic types HTTP Basic or APIKey.

### Generic KeySafe Types
To support authentication to external systems, generic authentication types are provided to allow KeySafe entries for integration outside of the provided specific Keysafe types.

* **API Key**<br>Authentication that requires an authentication key to make a secure connection.
* **oAuth 2.0**<br>Create an entry that uses standard oAuth 2.0 authentication.
* **HTTP Basic Authentication**<br>Connect using basic HTTP authentication using a user name and password.
* **HTTP Digest Authentication**<br>Connect with a user name and password, but with added security over basic authentication.
* **Database Authentication**<br>Connect to a database system such as Microsoft SQL.
* **User name + Password + Pre-shared key**<br>Basic username and password authentication with an added security of a pre-shared key.
* **SSH Private Key**<br>Uses two related keys, a public key and a private key, that together create a key pair that is used as the secure access credential.


### Service Specific KeySafe Types
The `Type` list includes many predefined services that Hornbill integrates with. Each of these types contain attributes that are required to authenticate to that service. If you are looking to integrate with an external service, check first to see if there is a type available for that service.

## Using KeySafe in a Workflow
Using KeySafe entires as part of a business workflow is a great way to securely connect to external services.

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