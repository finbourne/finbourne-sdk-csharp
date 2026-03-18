# Finbourne.Sdk.Lusid.Model.Execution

The record of a number of executions against a single Placement (directly analogous to  a partial or full fill against a street order).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PlacementId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this execution. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument ordered. |
| **LusidInstrumentId** | **string** | Required | The LUSID instrument id for the instrument execution. |
| **Quantity** | **decimal** | Required | The quantity of given instrument ordered. |
| **State** | **string** | Required | The state of this execution (typically a FIX state; Open, Filled, etc). |
| **Side** | **string** | Required | The side (Buy, Sell, ...) of this execution. |
| **Type** | **string** | Required | The type of this execution (Market, Limit, etc). |
| **CreatedDate** | **DateTimeOffset** | Required | The active date of this execution. |
| **SettlementDate** | **DateTimeOffset?** | Optional | The (optional) settlement date for this execution |
| **Price** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **SettlementCurrency** | **string** | Required | The execution&#39;s settlement currency. |
| **SettlementCurrencyFxRate** | **decimal** | Required | The exectuion&#39;s settlement currency rate. |
| **Counterparty** | **string** | Required | The market entity this placement is placed with. |
| **AveragePrice** | **decimal?** | Optional | The average price of all executions for a given placement at the time of upsert |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Execution(
    id: new ResourceId(...),  // required
    placementId: new ResourceId(...),  // required
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this execution.
    instrumentIdentifiers: ,  // required — The instrument ordered.
    lusidInstrumentId: "...",  // required — The LUSID instrument id for the instrument execution.
    quantity: 0.0d,  // required — The quantity of given instrument ordered.
    state: "...",  // required — The state of this execution (typically a FIX state; Open, Filled, etc).
    side: "...",  // required — The side (Buy, Sell, ...) of this execution.
    type: "...",  // required — The type of this execution (Market, Limit, etc).
    createdDate: DateTimeOffset.Now,  // required — The active date of this execution.
    settlementDate: DateTimeOffset.Now,  // optional — The (optional) settlement date for this execution
    price: new CurrencyAndAmount(...),  // required
    settlementCurrency: "...",  // required — The execution&#39;s settlement currency.
    settlementCurrencyFxRate: 0.0d,  // required — The exectuion&#39;s settlement currency rate.
    counterparty: "...",  // required — The market entity this placement is placed with.
    averagePrice: 0.0d,  // optional — The average price of all executions for a given placement at the time of upsert
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
var instance = JsonConvert.DeserializeObject<Execution>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [ModelVersion](ModelVersion.md)
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

