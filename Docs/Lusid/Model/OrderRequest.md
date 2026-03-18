# Finbourne.Sdk.Lusid.Model.OrderRequest

A request to create or update an Order.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this order. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument ordered. |
| **Quantity** | **decimal?** | Optional | The quantity of the given instrument ordered. |
| **Side** | **string** | Required | The client&#39;s representation of the order&#39;s side (buy, sell, short, etc) |
| **OrderBookId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **State** | **string** | Optional | The order&#39;s state (examples: New, PartiallyFilled, ...) |
| **Type** | **string** | Optional | The order&#39;s type (examples: Limit, Market, ...) |
| **TimeInForce** | **string** | Optional | The order&#39;s time in force (examples: Day, GoodTilCancel, ...) |
| **Date** | **DateTimeOffset** | Optional | The date on which the order was made |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **LimitPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **StopPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **OrderInstruction** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Package** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Weight** | **decimal?** | Optional | The proportion of the total portfolio value ordered for the given instrument ordered. |
| **Amount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OrderRequest(
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this order.
    instrumentIdentifiers: ,  // required — The instrument ordered.
    quantity: 0.0d,  // optional — The quantity of the given instrument ordered.
    side: "...",  // required — The client&#39;s representation of the order&#39;s side (buy, sell, short, etc)
    orderBookId: new ResourceId(...),  // optional
    portfolioId: new ResourceId(...),  // optional
    id: new ResourceId(...),  // required
    state: "...",  // optional — The order&#39;s state (examples: New, PartiallyFilled, ...)
    type: "...",  // optional — The order&#39;s type (examples: Limit, Market, ...)
    timeInForce: "...",  // optional — The order&#39;s time in force (examples: Day, GoodTilCancel, ...)
    date: DateTimeOffset.Now,  // optional — The date on which the order was made
    price: new CurrencyAndAmount(...),  // optional
    limitPrice: new CurrencyAndAmount(...),  // optional
    stopPrice: new CurrencyAndAmount(...),  // optional
    orderInstruction: new ResourceId(...),  // optional
    package: new ResourceId(...),  // optional
    weight: 0.0d,  // optional — The proportion of the total portfolio value ordered for the given instrument ordered.
    amount: new CurrencyAndAmount(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OrderRequest>(json);
```


## Related Models

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

