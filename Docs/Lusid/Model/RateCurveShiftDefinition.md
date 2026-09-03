# Finbourne.Sdk.Lusid.Model.RateCurveShiftDefinition

> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Ccy** | **string** | Required | *No description available.* |
| **Amount** | **decimal?** | Optional | The size of the shift, in the units given by Scale: basis points by default (50 means +50bps),  or a percentage of each rate when Scale is Percentage (1 means rates scaled by 1.01). |
| **StartTenor** | **string** | Optional | *No description available.* |
| **EndTenor** | **string** | Optional | *No description available.* |
| **ShiftType** | **string** | Required | Available values: Parallel, Steepen, Flatten, Twist, Tent. |
| **Scale** | **string** | Optional | Available values: Bps, Percentage. |
| **ApplyTo** | **string** | Optional | A LUSID filter expression over the instrument entity scoping which instruments this shift is  for, e.g. \&quot;properties[Instrument/default/CountryOfIssue] eq &#39;Italy&#39;\&quot;. The shifted market data  is used by the whole valuation run, but when the scenario is requested as a result column the  column is only populated for matching instruments. Only usable when the scenario is applied as  a per-metric column. Note that with a scope set, the base and scenario columns cover different  instrument populations: an aggregate (e.g. Sum) of the scenario column totals only the matching  instruments, so it is not directly comparable to the same aggregate of the base column. |
| **PivotTenor** | **string** | Optional | The tenor the Tent shift peaks at. The shift applies with the full Amount at this tenor,  falling linearly to zero at StartTenor and EndTenor - the key-rate triangle shape, whose  asymmetry matters because key-rate buckets are rarely evenly spaced. Only valid with  ShiftType Tent; omitted, a Tent peaks at the midpoint of the window. Declared last on  purpose: generated SDKs emit their positional constructor in property-declaration order,  and this property must not shift the parameters of the ones before it.  Over a window containing a single curve point, that point takes the full Amount regardless  of where the pivot lands: a one-point window has no slope to express, and every shift  shape degenerates the same way there. |
| **WindowBounds** | **string** | Optional | Available values: Inclusive, StartExclusive, EndExclusive, Exclusive. |
| **CurveName** | **string** | Optional | The funding identifier of the one curve in the currency this shift targets, letting a  scenario shock a named curve (say, an issuer discounting curve) without also moving the  risk-free curve mastered in the same currency. Omitted - as on every scenario stored  before this field existed - the shift matches every rate curve in the currency, exactly  as before. Declared last on purpose: generated SDKs emit their positional constructor in  property-declaration order, and this property must not shift the parameters of the ones  before it. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition, InflationCurveShiftDefinition, CreditSpreadShiftDefinition. Default: `ScenarioShiftTypeEnum.RateCurveShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RateCurveShiftDefinition(
    ccy: "...",  // required
    amount: 0.0d,  // optional — The size of the shift, in the units given by Scale: basis points by default (50 means +50bps),  or a percentage of each rate when Scale is Percentage (1 means rates scaled by 1.01).
    startTenor: "...",  // optional
    endTenor: "...",  // optional
    shiftType: "...",  // required — Available values: Parallel, Steepen, Flatten, Twist, Tent.
    scale: "...",  // optional — Available values: Bps, Percentage.
    applyTo: "...",  // optional — A LUSID filter expression over the instrument entity scoping which instruments this shift is  for, e.g. \&quot;properties[Instrument/default/CountryOfIssue] eq &#39;Italy&#39;\&quot;. The shifted market data  is used by the whole valuation run, but when the scenario is requested as a result column the  column is only populated for matching instruments. Only usable when the scenario is applied as  a per-metric column. Note that with a scope set, the base and scenario columns cover different  instrument populations: an aggregate (e.g. Sum) of the scenario column totals only the matching  instruments, so it is not directly comparable to the same aggregate of the base column.
    pivotTenor: "...",  // optional — The tenor the Tent shift peaks at. The shift applies with the full Amount at this tenor,  falling linearly to zero at StartTenor and EndTenor - the key-rate triangle shape, whose  asymmetry matters because key-rate buckets are rarely evenly spaced. Only valid with  ShiftType Tent; omitted, a Tent peaks at the midpoint of the window. Declared last on  purpose: generated SDKs emit their positional constructor in property-declaration order,  and this property must not shift the parameters of the ones before it.  Over a window containing a single curve point, that point takes the full Amount regardless  of where the pivot lands: a one-point window has no slope to express, and every shift  shape degenerates the same way there.
    windowBounds: "...",  // optional — Available values: Inclusive, StartExclusive, EndExclusive, Exclusive.
    curveName: "...",  // optional — The funding identifier of the one curve in the currency this shift targets, letting a  scenario shock a named curve (say, an issuer discounting curve) without also moving the  risk-free curve mastered in the same currency. Omitted - as on every scenario stored  before this field existed - the shift matches every rate curve in the currency, exactly  as before. Declared last on purpose: generated SDKs emit their positional constructor in  property-declaration order, and this property must not shift the parameters of the ones  before it.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition, InflationCurveShiftDefinition, CreditSpreadShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RateCurveShiftDefinition>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

