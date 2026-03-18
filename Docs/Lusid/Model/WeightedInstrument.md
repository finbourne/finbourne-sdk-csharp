# Finbourne.Sdk.Lusid.Model.WeightedInstrument

Specification for a holding or quantity of (weight for) an instrument on a given date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Quantity** | **decimal** | Optional | The quantity of the instrument that is owned. |
| **HoldingIdentifier** | **string** | Optional | Identifier for the instrument.  For a single, unique trade or transaction this can be thought of as equivalent to the transaction identifier, or  a composite of the sub-holding keys for a regular sub-holding. When there are multiple transactions sharing the same underlying instrument  such as purchase of shares on multiple dates where tax implications are different this would not be the case.    In an inlined aggregation request if this is wanted to identify a line item, it can be specified in the set of aggregation keys given on the aggregation  request that accompanies the set of weighted instruments. |
| **Instrument** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **InLineLookupIdentifiers** | [WeightedInstrumentInLineLookupIdentifiers](WeightedInstrumentInLineLookupIdentifiers.md) | Optional | *No description available.* |
| **InstrumentScope** | **string** | Optional | The scope in which to resolve the instrument, if no inlined definition is provided.  If left empty, the default scope will be used. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WeightedInstrument(
    quantity: 0.0d,  // optional — The quantity of the instrument that is owned.
    holdingIdentifier: "...",  // optional — Identifier for the instrument.  For a single, unique trade or transaction this can be thought of as equivalent to the transaction identifier, or  a composite of the sub-holding keys for a regular sub-holding. When there are multiple transactions sharing the same underlying instrument  such as purchase of shares on multiple dates where tax implications are different this would not be the case.    In an inlined aggregation request if this is wanted to identify a line item, it can be specified in the set of aggregation keys given on the aggregation  request that accompanies the set of weighted instruments.
    instrument: new LusidInstrument(...),  // optional
    inLineLookupIdentifiers: new WeightedInstrumentInLineLookupIdentifiers(...),  // optional
    instrumentScope: "..."  // optional — The scope in which to resolve the instrument, if no inlined definition is provided.  If left empty, the default scope will be used.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WeightedInstrument>(json);
```

- [LusidInstrument](LusidInstrument.md)
- [WeightedInstrumentInLineLookupIdentifiers](WeightedInstrumentInLineLookupIdentifiers.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

