# Finbourne.Sdk.Lusid.Model.PlacementUpdateRequest

A request to create or update a Placement.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Quantity** | **decimal?** | Optional | The quantity of given instrument ordered. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this placement. |
| **Type** | **string** | Optional | The type of this placement (Market, Limit, etc). |
| **LimitPrice** | **decimal?** | Optional | The optional price, as currency and amount, associated with this placement. |
| **StopPrice** | **decimal?** | Optional | The optional price, as currency and amount, associated with this placement. |
| **Counterparty** | **string** | Optional | Optionally specifies the market entity this placement is placed with. |
| **ExecutionSystem** | **string** | Optional | Optionally specifies the execution system in use. |
| **EntryType** | **string** | Optional | Optionally specifies the entry type of this placement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PlacementUpdateRequest(
    id: new ResourceId(...),  // required
    quantity: 0.0d,  // optional — The quantity of given instrument ordered.
    properties: new PerpetualProperty(...),  // optional — Client-defined properties associated with this placement.
    type: "...",  // optional — The type of this placement (Market, Limit, etc).
    limitPrice: 0.0d,  // optional — The optional price, as currency and amount, associated with this placement.
    stopPrice: 0.0d,  // optional — The optional price, as currency and amount, associated with this placement.
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
var instance = JsonConvert.DeserializeObject<PlacementUpdateRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

