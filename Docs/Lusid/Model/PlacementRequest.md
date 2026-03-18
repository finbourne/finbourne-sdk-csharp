# Finbourne.Sdk.Lusid.Model.PlacementRequest

A request to create or update a Placement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ParentPlacementId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **BlockIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | The IDs of the Blocks associated with this placement. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this order. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | The instrument ordered. |
| **Quantity** | **decimal** | Required | The quantity of given instrument ordered. |
| **State** | **string** | Optional | The state of this placement (typically a FIX state; Open, Filled, etc). |
| **Side** | **string** | Required | The side (Buy, Sell, ...) of this placement. |
| **TimeInForce** | **string** | Required | The time in force applicable to this placement (GTC, FOK, Day, etc) |
| **Type** | **string** | Required | The type of this placement (Market, Limit, etc). |
| **CreatedDate** | **DateTimeOffset** | Required | The active date of this placement. |
| **LimitPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **StopPrice** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Counterparty** | **string** | Optional | Optionally specifies the market entity this placement is placed with. |
| **ExecutionSystem** | **string** | Optional | Optionally specifies the execution system in use. |
| **EntryType** | **string** | Optional | Optionally specifies the entry type of this placement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PlacementRequest(
    id: new ResourceId(...),  // required
    parentPlacementId: new ResourceId(...),  // optional
    blockIds: new List<ResourceId>(),  // required — The IDs of the Blocks associated with this placement.
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this order.
    instrumentIdentifiers: ,  // required — The instrument ordered.
    quantity: 0.0d,  // required — The quantity of given instrument ordered.
    state: "...",  // optional — The state of this placement (typically a FIX state; Open, Filled, etc).
    side: "...",  // required — The side (Buy, Sell, ...) of this placement.
    timeInForce: "...",  // required — The time in force applicable to this placement (GTC, FOK, Day, etc)
    type: "...",  // required — The type of this placement (Market, Limit, etc).
    createdDate: DateTimeOffset.Now,  // required — The active date of this placement.
    limitPrice: new CurrencyAndAmount(...),  // optional
    stopPrice: new CurrencyAndAmount(...),  // optional
    counterparty: "...",  // optional — Optionally specifies the market entity this placement is placed with.
    executionSystem: "...",  // optional — Optionally specifies the execution system in use.
    entryType: "..."  // optional — Optionally specifies the entry type of this placement.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PlacementRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `BlockIds`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

