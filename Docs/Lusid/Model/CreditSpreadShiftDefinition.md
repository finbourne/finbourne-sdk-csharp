# Finbourne.Sdk.Lusid.Model.CreditSpreadShiftDefinition

A shift of a credit spread curve, targeted by the ticker of the reference entity and,  optionally, the currency the curve is quoted in. The shift applies to the par spread quotes  the curve carries, so a basis-point amount means basis points of spread - the units a spread  shock is quoted in. Shift shapes, tenor windows, scales and the Tent pivot behave exactly as  they do on a rate curve shift.
> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Ticker** | **string** | Required | The ticker of the reference entity whose spread curve is shifted. |
| **Ccy** | **string** | Optional | The currency the curve is quoted in; disambiguates a ticker quoted in more than one  currency. Omitted, the shift matches the ticker in every currency. |
| **Amount** | **decimal?** | Optional | The size of the shift, in the units given by Scale: basis points of spread by default  (50 means +50bps), or a percentage of each spread when Scale is Percentage (1 means  spreads scaled by 1.01). |
| **StartTenor** | **string** | Optional | *No description available.* |
| **EndTenor** | **string** | Optional | *No description available.* |
| **ShiftType** | **string** | Required | Available values: Parallel, Steepen, Flatten, Twist, Tent. |
| **Scale** | **string** | Optional | Available values: Bps, Percentage. |
| **PivotTenor** | **string** | Optional | The tenor the Tent shift peaks at. The shift applies with the full Amount at this tenor,  falling linearly to zero at StartTenor and EndTenor - the key-rate triangle shape. Only  valid with ShiftType Tent; omitted, a Tent peaks at the midpoint of the window. Declared  last on purpose: generated SDKs emit their positional constructor in property-declaration  order, and this property must not shift the parameters of the ones before it. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition, InflationCurveShiftDefinition, CreditSpreadShiftDefinition. Default: `ScenarioShiftTypeEnum.CreditSpreadShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreditSpreadShiftDefinition(
    ticker: "...",  // required — The ticker of the reference entity whose spread curve is shifted.
    ccy: "...",  // optional — The currency the curve is quoted in; disambiguates a ticker quoted in more than one  currency. Omitted, the shift matches the ticker in every currency.
    amount: 0.0d,  // optional — The size of the shift, in the units given by Scale: basis points of spread by default  (50 means +50bps), or a percentage of each spread when Scale is Percentage (1 means  spreads scaled by 1.01).
    startTenor: "...",  // optional
    endTenor: "...",  // optional
    shiftType: "...",  // required — Available values: Parallel, Steepen, Flatten, Twist, Tent.
    scale: "...",  // optional — Available values: Bps, Percentage.
    pivotTenor: "...",  // optional — The tenor the Tent shift peaks at. The shift applies with the full Amount at this tenor,  falling linearly to zero at StartTenor and EndTenor - the key-rate triangle shape. Only  valid with ShiftType Tent; omitted, a Tent peaks at the midpoint of the window. Declared  last on purpose: generated SDKs emit their positional constructor in property-declaration  order, and this property must not shift the parameters of the ones before it.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition, InflationCurveShiftDefinition, CreditSpreadShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreditSpreadShiftDefinition>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

