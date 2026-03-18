# Finbourne.Sdk.Lusid.Model.OrderGraphBlockAllocationSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Required | Total number of units allocated. |
| **Details** | [List&lt;OrderGraphBlockAllocationDetail&gt;](OrderGraphBlockAllocationDetail.md) | Required | Identifiers for each allocation in this block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockAllocationSynopsis(
    quantity: 0.0d,  // required — Total number of units allocated.
    details: new List<OrderGraphBlockAllocationDetail>()  // required — Identifiers for each allocation in this block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockAllocationSynopsis>(json);
```

- [OrderGraphBlockAllocationDetail](OrderGraphBlockAllocationDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

