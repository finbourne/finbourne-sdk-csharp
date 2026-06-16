# Finbourne.Sdk.Horizon.Model.ResolveFailedDeliveryRequest

Request to resolve a failed delivery without retry.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Reason** | **string** | Required | The reason for resolving the failed delivery without retrying. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ResolveFailedDeliveryRequest(
    reason: "..."  // required — The reason for resolving the failed delivery without retrying.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResolveFailedDeliveryRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

