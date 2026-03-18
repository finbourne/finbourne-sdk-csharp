# Finbourne.Sdk.Lusid.Model.OrderGraphPlacementOrderSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Details** | [List&lt;OrderGraphPlacementOrderDetail&gt;](OrderGraphPlacementOrderDetail.md) | Required | Identifiers for each order in the block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphPlacementOrderSynopsis(
    details: new List<OrderGraphPlacementOrderDetail>()  // required — Identifiers for each order in the block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphPlacementOrderSynopsis>(json);
```


## Related Models

- [OrderGraphPlacementOrderDetail](OrderGraphPlacementOrderDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

