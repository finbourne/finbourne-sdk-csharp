# Finbourne.Sdk.Horizon.Model.TpfRetryFailedDeliveryRequest

Request to retry failed deliveries for multiple batch elements. The integration instance identifier is supplied via the route, not the body.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BatchElementReferenceIds** | **List&lt;string&gt;** | Required | Batch element reference identifiers to retry. No regex pattern is required as batch element IDs are vendor-defined strings with varying formats. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfRetryFailedDeliveryRequest(
    batchElementReferenceIds:   // required — Batch element reference identifiers to retry. No regex pattern is required as batch element IDs are vendor-defined strings with varying formats.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfRetryFailedDeliveryRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

