# Finbourne.Sdk.Lusid.Model.YieldCurveData

Market data for a yield curve,  represented by a list of instruments and corresponding market quotes
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | Base date |
| **Instruments** | [List&lt;LusidInstrument&gt;](LusidInstrument.md) | Required | The set of instruments that define the curve. |
| **Quotes** | [List&lt;MarketQuote&gt;](MarketQuote.md) | Required | The market quotes corresponding to the the instruments used to define the curve |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.YieldCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new YieldCurveData(
    baseDate: DateTimeOffset.Now,  // required — Base date
    instruments: new List<LusidInstrument>(),  // required — The set of instruments that define the curve.
    quotes: new List<MarketQuote>(),  // required — The market quotes corresponding to the the instruments used to define the curve
    lineage: "...",  // optional — Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    marketDataOptions: new MarketDataOptions(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    marketDataType: "..."  // required — The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<YieldCurveData>(json);
```


- [LusidInstrument](LusidInstrument.md) — used in `Instruments`
- [MarketQuote](MarketQuote.md) — used in `Quotes`
- [MarketDataOptions](MarketDataOptions.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

