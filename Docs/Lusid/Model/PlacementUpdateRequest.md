# Finbourne.Sdk.Lusid.Model.PlacementUpdateRequest

A request to update a Placement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Quantity** | **decimal?** | Optional | The quantity of given instrument ordered. |
| **Amount** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this placement. |
| **Type** | **string** | Optional | Optionally changes the type of this placement (Market, Limit, Stop, StopLimit, etc). A type change is permitted only when the associated block is of type &#39;Market&#39;. Setting the type to &#39;Market&#39; clears the placement&#39;s stop and limit prices; any other type change leaves them as they are. |
| **LimitPrice** | **decimal?** | Optional | Optionally updates the limit price of this placement, in the placement&#39;s limit price currency unless a currency is also specified. A price on a placement with no limit price currency is stored but not returned until a currency is supplied. |
| **StopPrice** | **decimal?** | Optional | Optionally updates the stop price of this placement, in the placement&#39;s stop price currency unless a currency is also specified. A price on a placement with no stop price currency is stored but not returned until a currency is supplied. |
| **Counterparty** | **string** | Optional | Optionally specifies the market entity this placement is placed with. |
| **ExecutionSystem** | **string** | Optional | Optionally specifies the execution system in use. |
| **EntryType** | **string** | Optional | Optionally specifies the entry type of this placement. Available values: Undecided, Manual, Direct, Ems, External. |
| **Currency** | **string** | Optional | Optionally sets the ISO currency code of the placement&#39;s stop and/or limit price. Not permitted for a Market placement. For a value placement it must match the currency of the amount exactly, whether that amount is on the placement or in the update. When omitted, no currency checks are applied. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PlacementUpdateRequest(
    id: new ResourceId(...),  // required
    quantity: 0.0d,  // optional — The quantity of given instrument ordered.
    amount: new CurrencyAndAmount(...),  // optional
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this placement.
    type: "...",  // optional — Optionally changes the type of this placement (Market, Limit, Stop, StopLimit, etc). A type change is permitted only when the associated block is of type &#39;Market&#39;. Setting the type to &#39;Market&#39; clears the placement&#39;s stop and limit prices; any other type change leaves them as they are.
    limitPrice: 0.0d,  // optional — Optionally updates the limit price of this placement, in the placement&#39;s limit price currency unless a currency is also specified. A price on a placement with no limit price currency is stored but not returned until a currency is supplied.
    stopPrice: 0.0d,  // optional — Optionally updates the stop price of this placement, in the placement&#39;s stop price currency unless a currency is also specified. A price on a placement with no stop price currency is stored but not returned until a currency is supplied.
    counterparty: "...",  // optional — Optionally specifies the market entity this placement is placed with.
    executionSystem: "...",  // optional — Optionally specifies the execution system in use.
    entryType: "...",  // optional — Optionally specifies the entry type of this placement. Available values: Undecided, Manual, Direct, Ems, External.
    currency: "..."  // optional — Optionally sets the ISO currency code of the placement&#39;s stop and/or limit price. Not permitted for a Market placement. For a value placement it must match the currency of the amount exactly, whether that amount is on the placement or in the update. When omitted, no currency checks are applied.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PlacementUpdateRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

