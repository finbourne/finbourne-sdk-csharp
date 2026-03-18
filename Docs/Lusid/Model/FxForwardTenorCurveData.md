# Finbourne.Sdk.Lusid.Model.FxForwardTenorCurveData

Contains data (i.e. tenors and rates + metadata) for building fx forward curves (when combined with a date to build on)
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BaseDate** | **DateTimeOffset** | Required | EffectiveAt date of the quoted rates |
| **DomCcy** | **string** | Required | Domestic currency of the fx forward |
| **FgnCcy** | **string** | Required | Foreign currency of the fx forward |
| **Tenors** | **List&lt;string&gt;** | Required | Tenors for which the forward rates apply.  For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **Rates** | **List&lt;decimal&gt;** | Required | Rates provided for the fx forward (price in FgnCcy per unit of DomCcy) |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **Calendars** | [List&lt;FxTenorConvention&gt;](FxTenorConvention.md) | Optional | The list of conventions that should be used when interpreting tenors as dates. |
| **SpotDaysCalculationType** | **string** | Optional | Configures how to calculate the spot date from the build date using the Calendars provided.  Supported string (enumeration) values are: [ SingleCalendar, UnionCalendars ] |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.FxForwardTenorCurveData` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForwardTenorCurveData(
    baseDate: DateTimeOffset.Now,  // required — EffectiveAt date of the quoted rates
    domCcy: "...",  // required — Domestic currency of the fx forward
    fgnCcy: "...",  // required — Foreign currency of the fx forward
    tenors: ,  // required — Tenors for which the forward rates apply.  For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    rates: ,  // required — Rates provided for the fx forward (price in FgnCcy per unit of DomCcy)
    lineage: "...",  // optional — Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;.
    marketDataOptions: new MarketDataOptions(...),  // optional
    calendars: new List<FxTenorConvention>(),  // optional — The list of conventions that should be used when interpreting tenors as dates.
    spotDaysCalculationType: "...",  // optional — Configures how to calculate the spot date from the build date using the Calendars provided.  Supported string (enumeration) values are: [ SingleCalendar, UnionCalendars ]
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
var instance = JsonConvert.DeserializeObject<FxForwardTenorCurveData>(json);
```


- [MarketDataOptions](MarketDataOptions.md)
- [FxTenorConvention](FxTenorConvention.md) — used in `Calendars`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

