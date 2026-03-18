# Finbourne.Sdk.Lusid.Model.BlockedOrderRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this order. |
| **Quantity** | **decimal** | Required | The quantity of the given instrument ordered. |
| **OrderBookId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **State** | **string** | Optional | The order&#39;s state (examples: New, PartiallyFilled, ...) |
| **Date** | **DateTimeOffset** | Optional | The date on which the order was made |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **OrderInstruction** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Package** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Side** | **string** | Optional | The client&#39;s representation of the order&#39;s side (buy, sell, short, etc) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BlockedOrderRequest(
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this order.
    quantity: 0.0d,  // required — The quantity of the given instrument ordered.
    orderBookId: new ResourceId(...),  // optional
    portfolioId: new ResourceId(...),  // optional
    id: new ResourceId(...),  // required
    state: "...",  // optional — The order&#39;s state (examples: New, PartiallyFilled, ...)
    date: DateTimeOffset.Now,  // optional — The date on which the order was made
    price: new CurrencyAndAmount(...),  // optional
    orderInstruction: new ResourceId(...),  // optional
    package: new ResourceId(...),  // optional
    side: "..."  // optional — The client&#39;s representation of the order&#39;s side (buy, sell, short, etc)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BlockedOrderRequest>(json);
```


## Related Models

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

