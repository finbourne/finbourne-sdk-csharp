# Finbourne.Sdk.Lusid.Model.CreditSpreadCurveData

A credit spread curve matching tenors against par spread quotes
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | EffectiveAt date of the quoted rates |
| **DomCcy** | **string** | Required | Domestic currency of the curve |
| **Tenors** | **List&lt;string&gt;** | Required | The tenors for which the rates apply  For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **Spreads** | **List&lt;decimal&gt;** | Required | Par spread quotes corresponding to the tenors. |
| **RecoveryRate** | **decimal** | Required | The recovery rate in default. |
| **ReferenceDate** | **DateTimeOffset?** | Optional | If tenors are provided, this is the date against which the tenors will be resolved.  This is of importance to CDX spread quotes, which are usually quoted in tenors relative to the CDX start date.  In this case, the ReferenceDate would be equal to the CDX start date, and the BaseDate would be the date for which the spreads are valid.  If not provided, this defaults to the BaseDate of the curve. |
| **Maturities** | **List&lt;DateTimeOffset&gt;** | Optional | The maturity dates for which the rates apply.  Either tenors or maturities should be provided, not both. |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.CreditSpreadCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreditSpreadCurveData(
    baseDate: DateTimeOffset.Now,  // required — EffectiveAt date of the quoted rates
    domCcy: "...",  // required — Domestic currency of the curve
    tenors: ,  // required — The tenors for which the rates apply  For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    spreads: ,  // required — Par spread quotes corresponding to the tenors.
    recoveryRate: 0.0d,  // required — The recovery rate in default.
    referenceDate: DateTimeOffset.Now,  // optional — If tenors are provided, this is the date against which the tenors will be resolved.  This is of importance to CDX spread quotes, which are usually quoted in tenors relative to the CDX start date.  In this case, the ReferenceDate would be equal to the CDX start date, and the BaseDate would be the date for which the spreads are valid.  If not provided, this defaults to the BaseDate of the curve.
    maturities: ,  // optional — The maturity dates for which the rates apply.  Either tenors or maturities should be provided, not both.
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
var instance = JsonConvert.DeserializeObject<CreditSpreadCurveData>(json);
```


- [MarketDataOptions](MarketDataOptions.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

