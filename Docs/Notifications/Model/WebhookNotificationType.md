# Finbourne.Sdk.Notifications.Model.WebhookNotificationType

The information required to create or update a Webhook notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of delivery mechanism for this notification |
| **HttpMethod** | **string** | Required | The HTTP method such as GET, POST, etc. to use on the request |
| **Url** | **string** | Required | The URL to send the request to |
| **AuthenticationType** | **string** | Required | The type of authentication to use on the request, can be one of the following values: - Lusid -  Internal LUSID call - BasicAuth - User specified Username and password - BearerToken - Authorization header with Bearer scheme and user specified key - None - No Authorization required on the webhook call |
| **AuthenticationConfigurationItemPaths** | **Dictionary&lt;string, string&gt;** | Optional | The paths of the Configuration Store configuration items that contain the authentication configuration. Each authentication type requires different keys: - Lusid - None required - BasicAuth - Requires &#39;Username&#39; and &#39;Password&#39; - BearerToken - Requires &#39;BearerToken&#39; and optionally &#39;BearerScheme&#39; - None - None required              e.g. the following would be valid assuming that the config is present in the configuration store at the specified paths:                  \&quot;authenticationType\&quot;: \&quot;BasicAuth\&quot;,     \&quot;authenticationConfigurationItemPaths\&quot;: {         \&quot;Username\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminUser\&quot;,         \&quot;Password\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminPassword\&quot;     } |
| **ContentType** | **string** | Required | The type of the content e.g. Json |
| **Content** | **Object** | Optional | The content of the request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new WebhookNotificationType(
    type: "...",  // required — The type of delivery mechanism for this notification
    httpMethod: "...",  // required — The HTTP method such as GET, POST, etc. to use on the request
    url: "...",  // required — The URL to send the request to
    authenticationType: "...",  // required — The type of authentication to use on the request, can be one of the following values: - Lusid -  Internal LUSID call - BasicAuth - User specified Username and password - BearerToken - Authorization header with Bearer scheme and user specified key - None - No Authorization required on the webhook call
    authenticationConfigurationItemPaths: ,  // optional — The paths of the Configuration Store configuration items that contain the authentication configuration. Each authentication type requires different keys: - Lusid - None required - BasicAuth - Requires &#39;Username&#39; and &#39;Password&#39; - BearerToken - Requires &#39;BearerToken&#39; and optionally &#39;BearerScheme&#39; - None - None required              e.g. the following would be valid assuming that the config is present in the configuration store at the specified paths:                  \&quot;authenticationType\&quot;: \&quot;BasicAuth\&quot;,     \&quot;authenticationConfigurationItemPaths\&quot;: {         \&quot;Username\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminUser\&quot;,         \&quot;Password\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminPassword\&quot;     }
    contentType: "...",  // required — The type of the content e.g. Json
    content:   // optional — The content of the request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WebhookNotificationType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

