# Finbourne.Sdk.Lusid.Model.BlockAndOrdersRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BlockId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Orders** | [List&lt;BlockedOrderRequest&gt;](BlockedOrderRequest.md) | Required | An order which belongs to a block. Fields common to both entities (such as instrument) should be derived from the block. |
| **BlockProperties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this block. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument ordered. |
| **Side** | **string** | Optional | The client&#39;s representation of the block&#39;s side (buy, sell, short, etc). BlockedOrders in the request which do not specify a side will have their side populated with this value. |
| **Type** | **string** | Optional | The block order&#39;s type (examples: Limit, Market, ...) |
| **TimeInForce** | **string** | Optional | The block orders&#39; time in force (examples: Day, GoodTilCancel, ...) |
| **Date** | **DateTimeOffset** | Optional | The date on which the block was made |
| **LimitPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **StopPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BlockAndOrdersRequest(
    blockId: new ResourceId(...),  // required
    orders: new List<BlockedOrderRequest>(),  // required — An order which belongs to a block. Fields common to both entities (such as instrument) should be derived from the block.
    blockProperties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this block.
    instrumentIdentifiers: ,  // required — The instrument ordered.
    side: "...",  // optional — The client&#39;s representation of the block&#39;s side (buy, sell, short, etc). BlockedOrders in the request which do not specify a side will have their side populated with this value.
    type: "...",  // optional — The block order&#39;s type (examples: Limit, Market, ...)
    timeInForce: "...",  // optional — The block orders&#39; time in force (examples: Day, GoodTilCancel, ...)
    date: DateTimeOffset.Now,  // optional — The date on which the block was made
    limitPrice: new CurrencyAndAmount(...),  // optional
    stopPrice: new CurrencyAndAmount(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BlockAndOrdersRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [BlockedOrderRequest](BlockedOrderRequest.md) — used in `Orders`
- [PerpetualProperty](PerpetualProperty.md) — used in `BlockProperties`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

