# Finbourne.Sdk.Lusid.Model.PriceShiftDefinition

> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Instrument** | **string** | Optional | A single instrument identifier this shift applies to. Exactly one of Instrument and Filter  must be supplied. |
| **Filter** | **string** | Optional | A LUSID filter expression over the instrument entity - fields and properties - selecting which  instruments&#39; quotes the shift applies to, e.g.  \&quot;assetClass eq &#39;Bond&#39; and properties[Instrument/Issuer/Name] eq &#39;X&#39;\&quot;.  Exactly one of Instrument and Filter must be supplied. |
| **Amount** | **decimal** | Required | *No description available.* |
| **ShiftType** | **string** | Required | Available values: Absolute, Relative, Percentage. |
| **QuoteType** | **string** | Optional | Available values: Price, Spread, Rate, LogNormalVol, NormalVol, ParSpread, IsdaSpread, Upfront, Index, Ratio, Delta, PoolFactor, InflationAssumption, DirtyPrice, PrincipalWriteOff, InterestDeferred, InterestShortfall, ConstituentWeightFactor. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition. Default: `ScenarioShiftTypeEnum.PriceShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PriceShiftDefinition(
    instrument: "...",  // optional — A single instrument identifier this shift applies to. Exactly one of Instrument and Filter  must be supplied.
    filter: "...",  // optional — A LUSID filter expression over the instrument entity - fields and properties - selecting which  instruments&#39; quotes the shift applies to, e.g.  \&quot;assetClass eq &#39;Bond&#39; and properties[Instrument/Issuer/Name] eq &#39;X&#39;\&quot;.  Exactly one of Instrument and Filter must be supplied.
    amount: 0.0d,  // required
    shiftType: "...",  // required — Available values: Absolute, Relative, Percentage.
    quoteType: "...",  // optional — Available values: Price, Spread, Rate, LogNormalVol, NormalVol, ParSpread, IsdaSpread, Upfront, Index, Ratio, Delta, PoolFactor, InflationAssumption, DirtyPrice, PrincipalWriteOff, InterestDeferred, InterestShortfall, ConstituentWeightFactor.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PriceShiftDefinition>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

