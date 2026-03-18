# Finbourne.Sdk.Lusid.Model.Allocation

An Allocation of a certain quantity of a specific instrument against an originating  Order.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AllocatedOrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Quantity** | **decimal** | Required | The quantity of given instrument allocated. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument allocated. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this allocation. |
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies |
| **LusidInstrumentId** | **string** | Required | The LUSID instrument id for the instrument allocated. |
| **PlacementIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | A placement - also known as an order placed in the market - associated with this allocation. |
| **State** | **string** | Optional | The state of this allocation. |
| **Side** | **string** | Optional | The side of this allocation (examples: Buy, Sell, ...). |
| **Type** | **string** | Optional | The type of order associated with this allocation (examples: Limit, Market, ...). |
| **SettlementDate** | **DateTimeOffset?** | Optional | The settlement date for this allocation. |
| **Date** | **DateTimeOffset** | Optional | The date of this allocation. |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **SettlementCurrency** | **string** | Optional | The settlement currency of this allocation. |
| **SettlementCurrencyFxRate** | **decimal?** | Optional | The settlement currency to allocation currency FX rate. |
| **Counterparty** | **string** | Optional | The counterparty for this allocation. |
| **ExecutionIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The executions associated with this allocation |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Allocation(
    id: new ResourceId(...),  // required
    allocatedOrderId: new ResourceId(...),  // required
    portfolioId: new ResourceId(...),  // required
    quantity: 0.0d,  // required — The quantity of given instrument allocated.
    instrumentIdentifiers: ,  // required — The instrument allocated.
    varVersion: new ModelVersion(...),  // optional
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this allocation.
    instrumentScope: "...",  // optional — The scope in which the instrument lies
    lusidInstrumentId: "...",  // required — The LUSID instrument id for the instrument allocated.
    placementIds: new List<ResourceId>(),  // optional — A placement - also known as an order placed in the market - associated with this allocation.
    state: "...",  // optional — The state of this allocation.
    side: "...",  // optional — The side of this allocation (examples: Buy, Sell, ...).
    type: "...",  // optional — The type of order associated with this allocation (examples: Limit, Market, ...).
    settlementDate: DateTimeOffset.Now,  // optional — The settlement date for this allocation.
    date: DateTimeOffset.Now,  // optional — The date of this allocation.
    price: new CurrencyAndAmount(...),  // optional
    settlementCurrency: "...",  // optional — The settlement currency of this allocation.
    settlementCurrencyFxRate: 0.0d,  // optional — The settlement currency to allocation currency FX rate.
    counterparty: "...",  // optional — The counterparty for this allocation.
    executionIds: new List<ResourceId>(),  // optional — The executions associated with this allocation
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
var instance = JsonConvert.DeserializeObject<Allocation>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ResourceId](ResourceId.md) — used in `PlacementIds`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ResourceId](ResourceId.md) — used in `ExecutionIds`
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

