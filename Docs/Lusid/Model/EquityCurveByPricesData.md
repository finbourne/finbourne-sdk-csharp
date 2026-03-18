# Finbourne.Sdk.Lusid.Model.EquityCurveByPricesData

Contains data (i.e. dates and prices + metadata) for building Equity curves
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | EffectiveAt date of the provided prices |
| **Dates** | **List&lt;DateTimeOffset&gt;** | Required | Dates provided for the forward price of the Equity at the corresponding price in Prices.  These dates should be in the future with respect to the BaseDate. |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **Prices** | **List&lt;decimal&gt;** | Required | Prices provided for the forward price of the Equity at the corresponding date in Dates. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.EquityCurveByPricesData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquityCurveByPricesData(
    baseDate: DateTimeOffset.Now,  // required — EffectiveAt date of the provided prices
    dates: ,  // required — Dates provided for the forward price of the Equity at the corresponding price in Prices.  These dates should be in the future with respect to the BaseDate.
    lineage: "...",  // optional — Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    prices: ,  // required — Prices provided for the forward price of the Equity at the corresponding date in Dates.
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
var instance = JsonConvert.DeserializeObject<EquityCurveByPricesData>(json);
```


- [MarketDataOptions](MarketDataOptions.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

