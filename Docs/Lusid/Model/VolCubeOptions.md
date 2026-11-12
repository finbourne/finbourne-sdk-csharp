# Finbourne.Sdk.Lusid.Model.VolCubeOptions

Options for configuring how an IrVolCubeData is interpreted.
> **Inherits from:** [MarketDataOptions](MarketDataOptions.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DayCountConvention** | **string** | Optional | Day count convention the vols are quoted on. The cube places its expiry pillars on it, and a swaption priced off  the cube measures its time to expiry on it. Supported values: Actual360, Actual365, Act365F, Act365_25 and  ActualActual, or their aliases Act360, MoneyMarket, Act365, ActAct and ActActIsda. Default value: ActualActual. Available values: Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIcma, ActActIsma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM, Invalid. |
| **MarketDataOptionsType** | **string** | Required | Available values: CurveOptions, VolCubeOptions. Available values: CurveOptions, VolCubeOptions. Default: `MarketDataOptionsTypeEnum.VolCubeOptions` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VolCubeOptions(
    dayCountConvention: "...",  // optional — Day count convention the vols are quoted on. The cube places its expiry pillars on it, and a swaption priced off  the cube measures its time to expiry on it. Supported values: Actual360, Actual365, Act365F, Act365_25 and  ActualActual, or their aliases Act360, MoneyMarket, Act365, ActAct and ActActIsda. Default value: ActualActual. Available values: Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIcma, ActActIsma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM, Invalid.
    marketDataOptionsType: "..."  // required — Available values: CurveOptions, VolCubeOptions. Available values: CurveOptions, VolCubeOptions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VolCubeOptions>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

