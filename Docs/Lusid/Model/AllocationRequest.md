# Finbourne.Sdk.Lusid.Model.AllocationRequest

A request to create or update an Allocation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this allocation. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument allocated. |
| **Quantity** | **decimal** | Required | The quantity of given instrument allocated. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AllocatedOrderId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
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


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationRequest(
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this allocation.
    instrumentIdentifiers: ,  // required — The instrument allocated.
    quantity: 0.0d,  // required — The quantity of given instrument allocated.
    portfolioId: new ResourceId(...),  // required
    allocatedOrderId: new ResourceId(...),  // required
    id: new ResourceId(...),  // required
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
    executionIds: new List<ResourceId>()  // optional — The executions associated with this allocation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationRequest>(json);
```


## Related Models

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `PlacementIds`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ResourceId](ResourceId.md) — used in `ExecutionIds`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

