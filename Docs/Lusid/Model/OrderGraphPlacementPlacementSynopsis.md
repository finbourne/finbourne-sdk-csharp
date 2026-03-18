# Finbourne.Sdk.Lusid.Model.OrderGraphPlacementPlacementSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Details** | [List&lt;OrderGraphPlacementChildPlacementDetail&gt;](OrderGraphPlacementChildPlacementDetail.md) | Required | Identifiers for each child placement for this placement. |
| **Quantity** | **decimal** | Required | Total number of units placed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphPlacementPlacementSynopsis(
    details: new List<OrderGraphPlacementChildPlacementDetail>(),  // required — Identifiers for each child placement for this placement.
    quantity: 0.0d  // required — Total number of units placed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphPlacementPlacementSynopsis>(json);
```


## Related Models

- [OrderGraphPlacementChildPlacementDetail](OrderGraphPlacementChildPlacementDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

