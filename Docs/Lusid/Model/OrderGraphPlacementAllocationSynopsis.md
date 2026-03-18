# Finbourne.Sdk.Lusid.Model.OrderGraphPlacementAllocationSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Required | Total number of units allocated. |
| **Details** | [List&lt;OrderGraphPlacementAllocationDetail&gt;](OrderGraphPlacementAllocationDetail.md) | Required | Identifiers for each allocation in this placement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphPlacementAllocationSynopsis(
    quantity: 0.0d,  // required — Total number of units allocated.
    details: new List<OrderGraphPlacementAllocationDetail>()  // required — Identifiers for each allocation in this placement.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphPlacementAllocationSynopsis>(json);
```

- [OrderGraphPlacementAllocationDetail](OrderGraphPlacementAllocationDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

