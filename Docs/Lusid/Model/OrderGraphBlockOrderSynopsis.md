# Finbourne.Sdk.Lusid.Model.OrderGraphBlockOrderSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Required | Total number of units ordered. |
| **QuantityByState** | **Dictionary&lt;string, decimal&gt;** | Optional | Total number of units placed. |
| **Details** | [List&lt;OrderGraphBlockOrderDetail&gt;](OrderGraphBlockOrderDetail.md) | Required | Identifiers and other info for each order in this block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockOrderSynopsis(
    quantity: 0.0d,  // required — Total number of units ordered.
    quantityByState: ,  // optional — Total number of units placed.
    details: new List<OrderGraphBlockOrderDetail>()  // required — Identifiers and other info for each order in this block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockOrderSynopsis>(json);
```

- [OrderGraphBlockOrderDetail](OrderGraphBlockOrderDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

