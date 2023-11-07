# API Key Rules

You can specify one or more API rules that will restrict access to specific API's, WebDAV resources and/or IP addresses where the API key use can originate from.

If no rules are specified, then any API that the API key's associated user account has rights to invoked, can be called. If one or more API rules are defined, only API's that match these rules will be allowed, and the same in relation to WebDAV rules.

Each API key rule is a simple string that can include DOS-style wildcards. Rules are evaluated until a match is found, if no match is found the API call is rejected.

You can also add one or more IP rules. If no IP rules are defined, then there are no restrictions on the callers IP address.  However, if one or more IP rules are defined, then one of the rules *must* match the callers IP address, otherwise the API call will be rejected. 

You can also add one or more WebDAV rules. If no WebDAV rules are defined, then there are no restrictions on the WebDAV resources and operations.  However, if one or more WebDAV rules are defined, then one of the rules *must* match the callers WebDAV request, otherwise the WebDAV API call will be rejected. 

See rule examples below which will give you a good idea as to what is possible. 

|Rule|Description|
|:--|:--|
|`ip=142.250.200.46`|Will allow API calls using this API key from the specified address|
|`ip=142.250.200.0/24`|Will allow API calls using this API key from the specified network address 142.250.200.*|
|`dav=GET session/*`|Will allow the caller to do GET operation on any file in the session folder|
|`dav=PUT session/*`|Will allow the caller to do a PUT operation and upload a file into the session folder|
|`dav=* session/*`|Will allow the caller to perform any supported WebDAV operation in the session folder|
|`session:*`|Allows any API call in the session service|
|`session:getSessionInfo`|Will allow the session::getSessionInfo API to be used. You can specify multiple individual API calls when more than one API call should be allowed|
|`session:get*`|Allow any API with a name that starts with 'get' within the session service|
|`apps/com.hornbill.core/*`|Allows all com.hornbill.core global API's to be used|
|`apps/com.hornbill.core:addHistory`| Allow the Core application defined global API addHistory to be called|
|`apps/com.hornbill.core/Achievement:addAchievement`|Allows the application defined for entity Achievement's addAchievement API to be called|
|`apps/com.hornbill.core/Achievement:*`|Allows the application defined for entity Achievement's API's to be called|

### More Information

- [Hornbill Platform API Reference](https://docs.hornbill.com/esp-api/welcome)
- [Read about API Keys](https://docs.hornbill.com/esp-fundamentals/security/api-keys)
- [Best Practice Guide for API Keys](https://docs.hornbill.com/esp-fundamentals/best-practice/platform-api-keys)

