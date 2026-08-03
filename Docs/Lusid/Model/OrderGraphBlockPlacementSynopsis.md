# Finbourne.Sdk.Lusid.Model.OrderGraphBlockPlacementSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal?** | Optional | Total number of units placed. |
| **QuantityByState** | **Dictionary&lt;string, decimal&gt;** | Optional | Total number of units placed. |
| **Amount** | **decimal?** | Optional | Total monetary value placed, in the block currency. |
| **AmountByState** | **Dictionary&lt;string, decimal&gt;** | Optional | Total monetary value placed, broken down by placement state. |
| **Details** | [List&lt;OrderGraphBlockPlacementDetail&gt;](OrderGraphBlockPlacementDetail.md) | Required | Identifiers for each placement in this block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockPlacementSynopsis(
    quantity: 0.0d,  // optional — Total number of units placed.
    quantityByState: ,  // optional — Total number of units placed.
    amount: 0.0d,  // optional — Total monetary value placed, in the block currency.
    amountByState: ,  // optional — Total monetary value placed, broken down by placement state.
    details: new List<OrderGraphBlockPlacementDetail>()  // required — Identifiers for each placement in this block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockPlacementSynopsis>(json);
```

- [OrderGraphBlockPlacementDetail](OrderGraphBlockPlacementDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

