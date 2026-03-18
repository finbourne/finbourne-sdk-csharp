# Finbourne.Sdk.Lusid.Model.IrVolCubeData

Market Data required to build a volatility cube for swaption pricing,  represented by a list of instruments and corresponding market quotes
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | Base date of the cube - this is the start date of the swaptions on the cube. |
| **Instruments** | [List&lt;LusidInstrument&gt;](LusidInstrument.md) | Required | Retrieve the set of instruments that define the cube. |
| **Quotes** | [List&lt;MarketQuote&gt;](MarketQuote.md) | Required | Access the set of quotes that define the cube. |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.IrVolCubeData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IrVolCubeData(
    baseDate: DateTimeOffset.Now,  // required — Base date of the cube - this is the start date of the swaptions on the cube.
    instruments: new List<LusidInstrument>(),  // required — Retrieve the set of instruments that define the cube.
    quotes: new List<MarketQuote>(),  // required — Access the set of quotes that define the cube.
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
var instance = JsonConvert.DeserializeObject<IrVolCubeData>(json);
```


- [LusidInstrument](LusidInstrument.md) — used in `Instruments`
- [MarketQuote](MarketQuote.md) — used in `Quotes`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

