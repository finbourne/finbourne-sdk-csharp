# Finbourne.Sdk.Lusid.Model.OrderGraphPlacementExecutionSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Required | Total number of units executed. |
| **Details** | [List&lt;OrderGraphPlacementExecutionDetail&gt;](OrderGraphPlacementExecutionDetail.md) | Required | Identifiers info for each execution against this placement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphPlacementExecutionSynopsis(
    quantity: 0.0d,  // required — Total number of units executed.
    details: new List<OrderGraphPlacementExecutionDetail>()  // required — Identifiers info for each execution against this placement.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphPlacementExecutionSynopsis>(json);
```

- [OrderGraphPlacementExecutionDetail](OrderGraphPlacementExecutionDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

