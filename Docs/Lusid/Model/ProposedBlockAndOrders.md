# Finbourne.Sdk.Lusid.Model.ProposedBlockAndOrders

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Request** | [BlockAndOrdersRequest](BlockAndOrdersRequest.md) | Optional | *No description available.* |
| **NetQuantity** | **decimal?** | Optional | The block&#39;s quantity, netted by direction, where any order is quantity-based. |
| **NetAmount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ProposedBlockAndOrders(
    request: new BlockAndOrdersRequest(...),  // optional
    netQuantity: 0.0d,  // optional — The block&#39;s quantity, netted by direction, where any order is quantity-based.
    netAmount: new CurrencyAndAmount(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProposedBlockAndOrders>(json);
```


## Related Models

- [BlockAndOrdersRequest](BlockAndOrdersRequest.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

