# Finbourne.Sdk.Lusid.Model.FxForwardPipsCurveData

Contains data (i.e. dates and pips + metadata) for building fx forward curves (when combined with a spot rate to build on)
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | EffectiveAt date of the quoted pip rates |
| **DomCcy** | **string** | Required | Domestic currency of the fx forward |
| **FgnCcy** | **string** | Required | Foreign currency of the fx forward |
| **Dates** | **List&lt;DateTimeOffset&gt;** | Required | Dates for which the forward rates apply |
| **PipRates** | **List&lt;decimal&gt;** | Required | Rates provided for the fx forward (price in FgnCcy per unit of DomCcy), expressed in pips |
| **PipMultiplier** | **decimal?** | Optional | Optional. The scaling factor applied to the pip rates to convert them into a forward rate adjustment,  so that forwardRate &#x3D; spotRate + pipRate * pipMultiplier. Must be strictly positive when supplied.  When omitted, the market convention for the currency pair is used:  0.01 when the foreign (quote) currency is JPY, and 0.0001 (the four-decimal-place convention of the major pairs) otherwise. |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | Available values: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface, InflationCurveData. Default: `MarketDataTypeEnum.FxForwardPipsCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForwardPipsCurveData(
    baseDate: DateTimeOffset.Now,  // required — EffectiveAt date of the quoted pip rates
    domCcy: "...",  // required — Domestic currency of the fx forward
    fgnCcy: "...",  // required — Foreign currency of the fx forward
    dates: ,  // required — Dates for which the forward rates apply
    pipRates: ,  // required — Rates provided for the fx forward (price in FgnCcy per unit of DomCcy), expressed in pips
    pipMultiplier: 0.0d,  // optional — Optional. The scaling factor applied to the pip rates to convert them into a forward rate adjustment,  so that forwardRate &#x3D; spotRate + pipRate * pipMultiplier. Must be strictly positive when supplied.  When omitted, the market convention for the currency pair is used:  0.01 when the foreign (quote) currency is JPY, and 0.0001 (the four-decimal-place convention of the major pairs) otherwise.
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
var instance = JsonConvert.DeserializeObject<FxForwardPipsCurveData>(json);
```


- [MarketDataOptions](MarketDataOptions.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

