# Finbourne.Sdk.Lusid.Model.CurveOptions

Options for configuring how ComplexMarketData representing a 'curve' is interpreted.
> **Inherits from:** [MarketDataOptions](MarketDataOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DayCountConvention** | **string** | Optional | Day count convention of the curve. Defaults to \&quot;Act360\&quot;. |
| **FrontExtrapolationType** | **string** | Optional | What type of extrapolation is used to build the curve  Imagine that the curve is facing the observer(you), then the \&quot;front\&quot; direction is the closest point on the curve onward.    example: 0D tenor to past  Defaults to \&quot;Flat\&quot;. Supported string (enumeration) values are: [None, Flat, Linear]. |
| **BackExtrapolationType** | **string** | Optional | What type of extrapolation is used to build the curve.    Imagine that the curve is facing the observer(you), then the \&quot;back\&quot; direction is the furthest point on the curve onward.  example: 30Y tenor to infinity    Defaults to \&quot;Flat\&quot;. Supported string (enumeration) values are: [None, Flat, Linear]. |
| **MarketDataOptionsType** | **string** | Required | The available values are: CurveOptions Default: `MarketDataOptionsTypeEnum.CurveOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CurveOptions(
    dayCountConvention: "...",  // optional — Day count convention of the curve. Defaults to \&quot;Act360\&quot;.
    frontExtrapolationType: "...",  // optional — What type of extrapolation is used to build the curve  Imagine that the curve is facing the observer(you), then the \&quot;front\&quot; direction is the closest point on the curve onward.    example: 0D tenor to past  Defaults to \&quot;Flat\&quot;. Supported string (enumeration) values are: [None, Flat, Linear].
    backExtrapolationType: "...",  // optional — What type of extrapolation is used to build the curve.    Imagine that the curve is facing the observer(you), then the \&quot;back\&quot; direction is the furthest point on the curve onward.  example: 30Y tenor to infinity    Defaults to \&quot;Flat\&quot;. Supported string (enumeration) values are: [None, Flat, Linear].
    marketDataOptionsType: "..."  // required — The available values are: CurveOptions
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

