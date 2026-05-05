# Finbourne.Sdk.Lusid.Model.CurveOptions

Options for configuring how ComplexMarketData representing a 'curve' is interpreted.
> **Inherits from:** [MarketDataOptions](MarketDataOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DayCountConvention** | **string** | Optional | Day count convention of the curve. Default value: Act360. Available values: Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM, Invalid. |
| **FrontExtrapolationType** | **string** | Optional | What type of extrapolation is used to build the curve  Imagine that the curve is facing the observer(you), then the \&quot;front\&quot; direction is the closest point on the curve onward.    example: 0D tenor to past  Default value: Flat. Available values: None, Flat, Linear. |
| **BackExtrapolationType** | **string** | Optional | What type of extrapolation is used to build the curve.    Imagine that the curve is facing the observer(you), then the \&quot;back\&quot; direction is the furthest point on the curve onward.  example: 30Y tenor to infinity    Default value: Flat. Available values: None, Flat, Linear. |
| **MarketDataOptionsType** | **string** | Required | Available values: CurveOptions. Available values: CurveOptions. Default: `MarketDataOptionsTypeEnum.CurveOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CurveOptions(
    dayCountConvention: "...",  // optional — Day count convention of the curve. Default value: Act360. Available values: Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM, Invalid.
    frontExtrapolationType: "...",  // optional — What type of extrapolation is used to build the curve  Imagine that the curve is facing the observer(you), then the \&quot;front\&quot; direction is the closest point on the curve onward.    example: 0D tenor to past  Default value: Flat. Available values: None, Flat, Linear.
    backExtrapolationType: "...",  // optional — What type of extrapolation is used to build the curve.    Imagine that the curve is facing the observer(you), then the \&quot;back\&quot; direction is the furthest point on the curve onward.  example: 30Y tenor to infinity    Default value: Flat. Available values: None, Flat, Linear.
    marketDataOptionsType: "..."  // required — Available values: CurveOptions. Available values: CurveOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CurveOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

