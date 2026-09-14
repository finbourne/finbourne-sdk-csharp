# Finbourne.Sdk.Lusid.Model.InflationCurveShiftDefinition

A shift of an inflation curve, targeted by inflation index name. The shift applies to the  zero-coupon inflation swap quotes the curve was solved from and the curve re-solves with  the same seasonal factors and resolved fixings, so seasonality and the historic index path  survive the shift. Shift shapes, tenor windows, scales and the Tent pivot behave exactly  as they do on a rate curve shift.
> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **string** | Required | The inflation index name the curve is keyed by, e.g. UKRPI or EUHICPXT. |
| **Amount** | **decimal?** | Optional | The size of the shift, in the units given by Scale: basis points on the zero-coupon  rates by default (50 means +50bps), or a percentage of each rate when Scale is  Percentage (1 means rates scaled by 1.01). |
| **StartTenor** | **string** | Optional | The near end of the tenor window the shift applies over, resolved against the valuation  date. A whole number of units, in any case: BD (business day), D, W, M, Q or Qtr, SA  (semi-annual), Y or A - for example \&quot;1BD\&quot;, \&quot;3m\&quot;, \&quot;6M\&quot;, \&quot;1Qtr\&quot;, \&quot;5y\&quot;. Omitted, the window  is open at this end and every point up to EndTenor is in it. |
| **EndTenor** | **string** | Optional | The far end of the tenor window, in the same units as StartTenor. Omitted, the window is  open at this end. |
| **ShiftType** | **string** | Required | Available values: Parallel, Steepen, Flatten, Twist, Tent. |
| **Scale** | **string** | Optional | Available values: Bps, Percentage. |
| **PivotTenor** | **string** | Optional | The tenor the Tent shift peaks at. The shift applies with the full Amount at this tenor,  falling linearly to zero at StartTenor and EndTenor - the key-rate triangle shape. Only  valid with ShiftType Tent; omitted, a Tent peaks at the midpoint of the window. In the  same units as StartTenor. Declared last on purpose: generated SDKs emit their positional  constructor in property-declaration order, and this property must not shift the parameters  of the ones before it. |
| **WindowBounds** | **string** | Optional | Available values: Inclusive, StartExclusive, EndExclusive, Exclusive. |
| **MinimumAmountBps** | **decimal?** | Optional | The smallest magnitude, in basis points, of the shift finally applied at each curve point,  evaluated per point AFTER the shape weight, in the direction the shift acts there. Exactly  the rate curve shift&#39;s MinimumAmountBps - see that field for the full semantics; the two  curve shifts keep one vocabulary. Omitted, no floor applies - today&#39;s behaviour.  Declared after PivotTenor on purpose, for the constructor-ordering reason given there. |
| **ApplyWhenValue** | **string** | Optional | Available values: Any, Positive, Negative. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition, InflationCurveShiftDefinition, CreditSpreadShiftDefinition, ModelOptionShiftDefinition. Default: `ScenarioShiftTypeEnum.InflationCurveShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationCurveShiftDefinition(
    index: "...",  // required — The inflation index name the curve is keyed by, e.g. UKRPI or EUHICPXT.
    amount: 0.0d,  // optional — The size of the shift, in the units given by Scale: basis points on the zero-coupon  rates by default (50 means +50bps), or a percentage of each rate when Scale is  Percentage (1 means rates scaled by 1.01).
    startTenor: "...",  // optional — The near end of the tenor window the shift applies over, resolved against the valuation  date. A whole number of units, in any case: BD (business day), D, W, M, Q or Qtr, SA  (semi-annual), Y or A - for example \&quot;1BD\&quot;, \&quot;3m\&quot;, \&quot;6M\&quot;, \&quot;1Qtr\&quot;, \&quot;5y\&quot;. Omitted, the window  is open at this end and every point up to EndTenor is in it.
    endTenor: "...",  // optional — The far end of the tenor window, in the same units as StartTenor. Omitted, the window is  open at this end.
    shiftType: "...",  // required — Available values: Parallel, Steepen, Flatten, Twist, Tent.
    scale: "...",  // optional — Available values: Bps, Percentage.
    pivotTenor: "...",  // optional — The tenor the Tent shift peaks at. The shift applies with the full Amount at this tenor,  falling linearly to zero at StartTenor and EndTenor - the key-rate triangle shape. Only  valid with ShiftType Tent; omitted, a Tent peaks at the midpoint of the window. In the  same units as StartTenor. Declared last on purpose: generated SDKs emit their positional  constructor in property-declaration order, and this property must not shift the parameters  of the ones before it.
    windowBounds: "...",  // optional — Available values: Inclusive, StartExclusive, EndExclusive, Exclusive.
    minimumAmountBps: 0.0d,  // optional — The smallest magnitude, in basis points, of the shift finally applied at each curve point,  evaluated per point AFTER the shape weight, in the direction the shift acts there. Exactly  the rate curve shift&#39;s MinimumAmountBps - see that field for the full semantics; the two  curve shifts keep one vocabulary. Omitted, no floor applies - today&#39;s behaviour.  Declared after PivotTenor on purpose, for the constructor-ordering reason given there.
    applyWhenValue: "...",  // optional — Available values: Any, Positive, Negative.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition, InflationCurveShiftDefinition, CreditSpreadShiftDefinition, ModelOptionShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationCurveShiftDefinition>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

