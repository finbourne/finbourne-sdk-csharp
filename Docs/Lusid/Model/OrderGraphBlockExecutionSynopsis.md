# Finbourne.Sdk.Lusid.Model.OrderGraphBlockExecutionSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Required | Total number of units executed. |
| **Details** | [List&lt;OrderGraphBlockExecutionDetail&gt;](OrderGraphBlockExecutionDetail.md) | Required | Identifiers for each execution in this block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockExecutionSynopsis(
    quantity: 0.0d,  // required — Total number of units executed.
    details: new List<OrderGraphBlockExecutionDetail>()  // required — Identifiers for each execution in this block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockExecutionSynopsis>(json);
```

- [OrderGraphBlockExecutionDetail](OrderGraphBlockExecutionDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

