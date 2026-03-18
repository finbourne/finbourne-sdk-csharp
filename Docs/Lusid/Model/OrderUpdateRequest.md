# Finbourne.Sdk.Lusid.Model.OrderUpdateRequest

A request to create or update a Order.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Quantity** | **decimal?** | Optional | The quantity of the given instrument ordered. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this order. |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **LimitPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **StopPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Date** | **DateTimeOffset?** | Optional | The date on which the order was made |
| **Side** | **string** | Optional | The client&#39;s representation of the order&#39;s side (buy, sell, short, etc) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderUpdateRequest(
    id: new ResourceId(...),  // required
    quantity: 0.0d,  // optional — The quantity of the given instrument ordered.
    portfolioId: new ResourceId(...),  // optional
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this order.
    price: new CurrencyAndAmount(...),  // optional
    limitPrice: new CurrencyAndAmount(...),  // optional
    stopPrice: new CurrencyAndAmount(...),  // optional
    date: DateTimeOffset.Now,  // optional — The date on which the order was made
    side: "..."  // optional — The client&#39;s representation of the order&#39;s side (buy, sell, short, etc)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderUpdateRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

