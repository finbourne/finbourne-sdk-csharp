# Finbourne.Sdk.Horizon.Model.IntegrationDescription

Response containing the description of an integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | Unique identifier of the integration e.g. \&quot;copp-clark\&quot;. |
| **Name** | **string** | Required | Readable name of the integration e.g. \&quot;Copp Clark\&quot;. |
| **Description** | **string** | Required | Describes the purpose of the integration. |
| **SupportedTriggerTypes** | **List&lt;string&gt;** | Required | Trigger types (Time, File) the integration supports. |
| **Licensed** | **bool** | Required | True if your domain is licensed to use this integration, otherwise false. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationDescription(
    type: "...",  // required — Unique identifier of the integration e.g. \&quot;copp-clark\&quot;.
    name: "...",  // required — Readable name of the integration e.g. \&quot;Copp Clark\&quot;.
    description: "...",  // required — Describes the purpose of the integration.
    supportedTriggerTypes: ,  // required — Trigger types (Time, File) the integration supports.
    licensed: true  // required — True if your domain is licensed to use this integration, otherwise false.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationDescription>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

