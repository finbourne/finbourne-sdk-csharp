# Finbourne.Sdk.Horizon.Model.TpfFailedDeliveryResponse

Response for bulk retry operation of failed deliveries
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Submitted** | **int** | Required | Number of batch elements submitted for retry |
| **Results** | [List&lt;TpfRetryElementResult&gt;](TpfRetryElementResult.md) | Required | Per-element retry results |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new TpfFailedDeliveryResponse(
    submitted: 0,  // required — Number of batch elements submitted for retry
    results: new List<TpfRetryElementResult>()  // required — Per-element retry results
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TpfFailedDeliveryResponse>(json);
```

- [TpfRetryElementResult](TpfRetryElementResult.md) — used in `Results`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

