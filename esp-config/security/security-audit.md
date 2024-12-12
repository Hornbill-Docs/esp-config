# Security Audit

:::info
This feature is only available on the [Enterprise Edition](/esp-fundamentals/about/hornbill-editions#enterprise-edition-architecture).
:::

The Security Audit View, available on the Enterprise Edition, keeps track of events that relate to user access to Hornbill. From here you can quickly identify when the access took place and by who or what.

## Options

### Filter Audit Log
This option lets you quickly filter the list to display entries for a particular account or access from an IP address.

### Success / Failure
This option lets you filter between successful events and failed events.

### Event Types
Use this option to filter between the available event types.

* **Logon**. Shows a successful logon by a user.
* **Logoff**. Shows a successful logoff by a user.
* **User API Session Create**. Identifies when a user session has been created via an API call.
* **Session Timeout**. Show any sessions that have timed out due to inactivity.
* **Session Kill**. Show any sessions that were killed.

### Event Source
Use this option to filter between the available sources of the events.
* **Guest Local**. Guest account Login and Logoff events that use Hornbill authentication.
* **Guest SAML**. Guest account Login and Logoff events that use SAML authentication.
* **User Local**. User account Login and Logoff events that use Hornbill authentication.
* **User SAML**. User account Login and Logoff events that use SAML authentication.
* **System**. System account events that require authentication.