# Finbourne.Sdk.Lusid.Model.Block

A block of orders for the same instrument, intended to record for example a trader's aggregation  of outstanding orders at a given time.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The related order ids. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this block. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument ordered. |
| **LusidInstrumentId** | **string** | Required | The LUSID instrument id for the instrument ordered. |
| **Quantity** | **decimal** | Required | The total quantity of given instrument ordered. |
| **Side** | **string** | Required | The client&#39;s representation of the block&#39;s side (buy, sell, short, etc) |
| **Type** | **string** | Required | The block order&#39;s type (examples: Limit, Market, ...) |
| **TimeInForce** | **string** | Required | The block orders&#39; time in force (examples: Day, GoodTilCancel, ...) |
| **CreatedDate** | **DateTimeOffset** | Required | The date on which the block was made |
| **LimitPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **StopPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **IsSwept** | **bool** | Required | Swept blocks are considered no longer of active interest, and no longer take part in various order management processes |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Block(
    id: new ResourceId(...),  // required
    orderIds: new List<ResourceId>(),  // required — The related order ids.
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this block.
    instrumentIdentifiers: ,  // required — The instrument ordered.
    lusidInstrumentId: "...",  // required — The LUSID instrument id for the instrument ordered.
    quantity: 0.0d,  // required — The total quantity of given instrument ordered.
    side: "...",  // required — The client&#39;s representation of the block&#39;s side (buy, sell, short, etc)
    type: "...",  // required — The block order&#39;s type (examples: Limit, Market, ...)
    timeInForce: "...",  // required — The block orders&#39; time in force (examples: Day, GoodTilCancel, ...)
    createdDate: DateTimeOffset.Now,  // required — The date on which the block was made
    limitPrice: new CurrencyAndAmount(...),  // optional
    stopPrice: new CurrencyAndAmount(...),  // optional
    isSwept: true,  // required — Swept blocks are considered no longer of active interest, and no longer take part in various order management processes
    varVersion: new ModelVersion(...),  // optional
    dataModelMembership: new DataModelMembership(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Block>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `OrderIds`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ModelVersion](ModelVersion.md)
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

