# Finbourne.Sdk.Horizon.Model.ResolveFailedDeliveryResponse

Response from resolving the failed deliveries for a batch without retry. Resolution is batch-level, so Finbourne.Horizon.Integrations.Web.Dto.Integrations.TradePublicationFramework.Response.ResolveFailedDeliveryResponse.ResolvedCount is the number of failed deliveries marked resolved.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BatchReferenceId** | **string** | Required | *No description available.* |
| **ResolvedCount** | **int** | Required | *No description available.* |
| **Resolved** | **bool** | Required | *No description available.* |
| **ResolvedAt** | **DateTimeOffset** | Required | *No description available.* |
| **ResolutionReason** | **string** | Required | *No description available.* |
| **Message** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ResolveFailedDeliveryResponse(
    batchReferenceId: "...",  // required
    resolvedCount: 0,  // required
    resolved: true,  // required
    resolvedAt: DateTimeOffset.Now,  // required
    resolutionReason: "...",  // required
    message: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResolveFailedDeliveryResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

