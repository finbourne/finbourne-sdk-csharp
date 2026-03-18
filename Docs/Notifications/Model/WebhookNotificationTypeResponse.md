# Finbourne.Sdk.Notifications.Model.WebhookNotificationTypeResponse

Holds readonly information about a Webhook notification
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | The type of delivery mechanism for this notification |
| **HttpMethod** | **string** | Optional | The HTTP method such as GET, POST, etc. to use on the request |
| **Url** | **string** | Optional | The URL to send the request to |
| **AuthenticationType** | **string** | Optional | The type of authentication to use on the request |
| **AuthenticationConfigurationItemPaths** | **Dictionary&lt;string, string&gt;** | Optional | The paths of the Configuration Store configuration items that contain the authentication configuration. Each authentication type requires different keys: - Lusid - None required - BasicAuth - Requires &#39;Username&#39; and &#39;Password&#39; - BearerToken - Requires &#39;BearerToken&#39; and optionally &#39;BearerScheme&#39;              e.g. the following would be valid assuming that the config is present in the configuration store at the specified paths:                  \&quot;authenticationType\&quot;: \&quot;BasicAuth\&quot;,     \&quot;authenticationConfigurationItemPaths\&quot;: {         \&quot;Username\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminUser\&quot;,         \&quot;Password\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminPassword\&quot;     } |
| **ContentType** | **string** | Optional | The type of the content e.g. Json |
| **Content** | **Object** | Optional | The content of the request |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new WebhookNotificationTypeResponse(
    type: "...",  // optional — The type of delivery mechanism for this notification
    httpMethod: "...",  // optional — The HTTP method such as GET, POST, etc. to use on the request
    url: "...",  // optional — The URL to send the request to
    authenticationType: "...",  // optional — The type of authentication to use on the request
    authenticationConfigurationItemPaths: ,  // optional — The paths of the Configuration Store configuration items that contain the authentication configuration. Each authentication type requires different keys: - Lusid - None required - BasicAuth - Requires &#39;Username&#39; and &#39;Password&#39; - BearerToken - Requires &#39;BearerToken&#39; and optionally &#39;BearerScheme&#39;              e.g. the following would be valid assuming that the config is present in the configuration store at the specified paths:                  \&quot;authenticationType\&quot;: \&quot;BasicAuth\&quot;,     \&quot;authenticationConfigurationItemPaths\&quot;: {         \&quot;Username\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminUser\&quot;,         \&quot;Password\&quot;: \&quot;config://personal/myUserId/WebhookConfigurations/ExampleService/AdminPassword\&quot;     }
    contentType: "...",  // optional — The type of the content e.g. Json
    content:   // optional — The content of the request
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WebhookNotificationTypeResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

