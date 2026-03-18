# Finbourne.Sdk.Lusid.Model.EquityVolSurfaceData

Market Data for an equity vol surface, represented by a list of instruments and corresponding market quotes
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | Base date of the surface |
| **Instruments** | [List&lt;LusidInstrument&gt;](LusidInstrument.md) | Required | The set of instruments that define the surface. |
| **Quotes** | [List&lt;MarketQuote&gt;](MarketQuote.md) | Required | The set of market quotes that define the surface, in NormalVol or LogNormalVol terms. |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.EquityVolSurfaceData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquityVolSurfaceData(
    baseDate: DateTimeOffset.Now,  // required — Base date of the surface
    instruments: new List<LusidInstrument>(),  // required — The set of instruments that define the surface.
    quotes: new List<MarketQuote>(),  // required — The set of market quotes that define the surface, in NormalVol or LogNormalVol terms.
    lineage: "...",  // optional — Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
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
var instance = JsonConvert.DeserializeObject<EquityVolSurfaceData>(json);
```


- [LusidInstrument](LusidInstrument.md) — used in `Instruments`
- [MarketQuote](MarketQuote.md) — used in `Quotes`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

