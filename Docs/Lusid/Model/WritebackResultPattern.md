# Finbourne.Sdk.Lusid.Model.WritebackResultPattern

One combination of units difference and result cardinality for which writeback is suggested. A combination  that is not configured never produces a suggestion, even where the reconciliation has crossed the items  successfully. The collection is a set, and is returned in a canonical order regardless of the order supplied.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UnitsDifference** | **string** | Required | How the origin units compare to the target units, on a literal comparison rather than on the result type. LongBeyondTolerance is reported on results but cannot be configured. Available values: Exact, ShortWithinTolerance, ShortBeyondTolerance, LongWithinTolerance, LongBeyondTolerance. |
| **ResultCardinality** | **string** | Required | The item cardinality of the result, read left to right. ManyToMany is not supported. Available values: OneToOne, OneToMany, ManyToOne, ManyToMany, OneToNone, ManyToNone, NoneToOne, NoneToMany, NoneToNone. |
| **UseTargetUnits** | **bool** | Optional | Which side supplies the units where the two sides do not agree exactly. When false, the units come from the origin and any difference is left outstanding on the target; when true, they come from the target, which is written back in full. Defaults to false. Must be true for LongWithinTolerance, and cannot be true for ShortBeyondTolerance. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WritebackResultPattern(
    unitsDifference: "...",  // required — How the origin units compare to the target units, on a literal comparison rather than on the result type. LongBeyondTolerance is reported on results but cannot be configured. Available values: Exact, ShortWithinTolerance, ShortBeyondTolerance, LongWithinTolerance, LongBeyondTolerance.
    resultCardinality: "...",  // required — The item cardinality of the result, read left to right. ManyToMany is not supported. Available values: OneToOne, OneToMany, ManyToOne, ManyToMany, OneToNone, ManyToNone, NoneToOne, NoneToMany, NoneToNone.
    useTargetUnits: true  // optional — Which side supplies the units where the two sides do not agree exactly. When false, the units come from the origin and any difference is left outstanding on the target; when true, they come from the target, which is written back in full. Defaults to false. Must be true for LongWithinTolerance, and cannot be true for ShortBeyondTolerance.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WritebackResultPattern>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

