# Finbourne.Sdk.Identity.Model.McpToolSchedulerNotification

A notification configuration for a scheduler job
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of notification (e.g., \&quot;Email\&quot;, \&quot;Webhook\&quot;) |
| **Target** | **string** | Required | The target of the notification (e.g., email address, webhook URL) |
| **Trigger** | **string** | Required | When to send the notification (e.g., \&quot;OnSuccess\&quot;, \&quot;OnFailure\&quot;, \&quot;Always\&quot;) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new McpToolSchedulerNotification(
    type: "...",  // required — The type of notification (e.g., \&quot;Email\&quot;, \&quot;Webhook\&quot;)
    target: "...",  // required — The target of the notification (e.g., email address, webhook URL)
    trigger: "..."  // required — When to send the notification (e.g., \&quot;OnSuccess\&quot;, \&quot;OnFailure\&quot;, \&quot;Always\&quot;)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<McpToolSchedulerNotification>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

