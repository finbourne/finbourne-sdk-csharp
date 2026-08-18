# Finbourne.Sdk.Lusid.Model.InflationCurveData

Market data for an inflation curve, represented by a list of zero-coupon inflation swap  instruments and corresponding market quotes.
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BuildDate** | **DateTimeOffset** | Required | Build date of the curve - this is the reference date for resolution of the swap constituents. |
| **Instruments** | [List&lt;LusidInstrument&gt;](LusidInstrument.md) | Required | The set of instruments that define the curve.  The only supported instrument type is: [InflationSwap]. |
| **Quotes** | [List&lt;MarketQuote&gt;](MarketQuote.md) | Required | The market quotes corresponding to the the instruments used to define the curve |
| **SeasonalFactors** | **List&lt;decimal&gt;** | Optional | Optional multiplicative seasonal adjustment factors, one per calendar month starting from January.  If provided there must be exactly 12 factors. |
| **OutputType** | **string** | Optional | What the values of the built curve represent.  Supported string (enumeration) values are: [Level, Ratio].  Defaults to \&quot;Level\&quot; if not provided. |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | Available values: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface, InflationCurveData. Default: `MarketDataTypeEnum.InflationCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationCurveData(
    buildDate: DateTimeOffset.Now,  // required — Build date of the curve - this is the reference date for resolution of the swap constituents.
    instruments: new List<LusidInstrument>(),  // required — The set of instruments that define the curve.  The only supported instrument type is: [InflationSwap].
    quotes: new List<MarketQuote>(),  // required — The market quotes corresponding to the the instruments used to define the curve
    seasonalFactors: ,  // optional — Optional multiplicative seasonal adjustment factors, one per calendar month starting from January.  If provided there must be exactly 12 factors.
    outputType: "...",  // optional — What the values of the built curve represent.  Supported string (enumeration) values are: [Level, Ratio].  Defaults to \&quot;Level\&quot; if not provided.
    lineage: "...",  // optional — Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    marketDataOptions: new MarketDataOptions(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    marketDataType: "..."  // required — Available values: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface, InflationCurveData.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationCurveData>(json);
```


- [LusidInstrument](LusidInstrument.md) — used in `Instruments`
- [MarketQuote](MarketQuote.md) — used in `Quotes`
- [MarketDataOptions](MarketDataOptions.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

