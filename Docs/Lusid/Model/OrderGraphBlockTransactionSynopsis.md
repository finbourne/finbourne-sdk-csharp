# Finbourne.Sdk.Lusid.Model.OrderGraphBlockTransactionSynopsis

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Required | Total number of units booked. |
| **Details** | [List&lt;OrderGraphBlockTransactionDetail&gt;](OrderGraphBlockTransactionDetail.md) | Required | Identifiers for each transaction in this block. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderGraphBlockTransactionSynopsis(
    quantity: 0.0d,  // required — Total number of units booked.
    details: new List<OrderGraphBlockTransactionDetail>()  // required — Identifiers for each transaction in this block.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderGraphBlockTransactionSynopsis>(json);
```

- [OrderGraphBlockTransactionDetail](OrderGraphBlockTransactionDetail.md) — used in `Details`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

