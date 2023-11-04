# API Key Rules

You can restrict the use of an API Key by specifying one or more rules that restrict the use of the API for specific API's, WebDAV resources and/or IP addresses where the API key use can originate from.

If no rules are specified, then any API that the API key's associated user account has rights to invoked, can be called. If one or more API rules are defined, only API's that match these rules will be allowed, and the same in relation to WebDAV rules.

Each APIKEY rule is a simple string that can include DOS-style wildcards. Rules are evaluated until a match is found, if no match is found the API call is rejected.

You can also add one or more IP rules (from build 3755). If no IP rules are defined, then there are no restrcitions on the callers IP address.  However, if one or more IP rules are defined, then one of the rules *must* match the callers IP address, otherwise the API call will be rejected. 

You can also add one or more WebDAV rules (from build 3790). If no WebDAV rules are defined, then there are no restrcitions on the WebDAV resources and operations.  However, if one or more WebDAV rules are defined, then one of the rules *must* match the callers WebDAV request, otherwise the WebDAV API call will be rejected. 

IP rules are specified either as an absolute IP address, or as a network address using the [Classless Inter-Domain Routing (CIDR)](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) network address formatting convention. 

See the table of rule examples below. 

|Rule|Description|
|:--|:--|
|`ip=142.250.200.46`|Will allow API calls using this API key from the specified address|
|`ip=142.250.200.0/24`|Will allow API calls using this API key from the specified network address 142.250.200.x|
|`dav=GET session/*`|Will allow the caller to do GET operation on any file in the session folder|
|`dav=PUT session/*`|Will allow the caller to do a PUT operation and upload a file into the session folder|
|`dav=* session/*`|Will allow the caller to perform any supported WebDAV operation|
|`session:*`|Allows any API in the session service|
|`session:getSessionInfo`|Will allow this API. You can specify multiple individual API calls when more than one API call should be allowed|
|`session:get*`|Allow any API with a name that starts with 'get' within the session service|
|`apps/com.hornbill.core/*`|Allows all com.hornbill.core API's|
|`apps/com.hornbill.core:addHistory`| Allow the Core application defined global API addHistory
|`apps/com.hornbill.core/Achievement:addAchievement`|Allows the application defined for entity Achievement|
|`apps/com.hornbill.core/Achievement:*`|Allows the application defined for entity Achievement's API's|

### More Information

- [Hornbill Platform API Refernce](https://docs.hornbill.com/esp-api/welcome)
- [Read about API Keys](https://docs.hornbill.com/esp-fundamentals/security/api-keys)
- [Best Practice Guide for API Keys](https://docs.hornbill.com/esp-fundamentals/best-practice/platform-api-keys)


