# Finbourne.Sdk.Lusid.Model.FxForwardCurveByQuoteReference

Contains data (i.e. tenors and rates + metadata) for building fx forward curves (when combined with a date to build on)
> **Inherits from:** [ComplexMarketData](ComplexMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DomCcy** | **string** | Required | Domestic currency of the fx forward |
| **FgnCcy** | **string** | Required | Foreign currency of the fx forward |
| **Tenors** | **List&lt;string&gt;** | Required | Tenors for which the forward rates apply.  For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **QuoteReferences** | **List&lt;Dictionary&lt;string, string&gt;&gt;** | Required | For each tenor, a collection of identifiers. These will be looked up in the LUSID Quote Store to resolve the actual rates.  Accepts an array of Dictionary&lt;string, string&gt;. The keys of each dictionary must be chosen from the following enumeration:  [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].  For example:    \&quot;quoteReferences\&quot;: [{\&quot;ClientInternal\&quot;: \&quot;SomeIdentifierForFirstTenor\&quot;},{\&quot;ClientInternal\&quot;: \&quot;SomeIdentifierForSecondTenor\&quot;} |
| **Lineage** | **string** | Optional | Description of the complex market data&#39;s lineage e.g. &#39;FundAccountant_GreenQuality&#39;. |
| **MarketDataOptions** | [MarketDataOptions](MarketDataOptions.md) | Optional | *No description available.* |
| **Calendars** | [List&lt;FxTenorConvention&gt;](FxTenorConvention.md) | Optional | The list of conventions that should be used when interpreting tenors as dates. |
| **SpotDaysCalculationType** | **string** | Optional | Configures how to calculate the spot date from the build date using the Calendars provided.  Supported string (enumeration) values are: [ SingleCalendar, UnionCalendars ] |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **MarketDataType** | **string** | Required | The available values are: DiscountFactorCurveData, EquityVolSurfaceData, FxVolSurfaceData, IrVolCubeData, OpaqueMarketData, YieldCurveData, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData, FxForwardCurveByQuoteReference, CreditSpreadCurveData, EquityCurveByPricesData, ConstantVolatilitySurface Default: `MarketDataTypeEnum.FxForwardCurveByQuoteReference` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForwardCurveByQuoteReference(
    domCcy: "...",  // required — Domestic currency of the fx forward
    fgnCcy: "...",  // required — Foreign currency of the fx forward
    tenors: ,  // required — Tenors for which the forward rates apply.  For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    quoteReferences: ,  // required — For each tenor, a collection of identifiers. These will be looked up in the LUSID Quote Store to resolve the actual rates.  Accepts an array of Dictionary&lt;string, string&gt;. The keys of each dictionary must be chosen from the following enumeration:  [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].  For example:    \&quot;quoteReferences\&quot;: [{\&quot;ClientInternal\&quot;: \&quot;SomeIdentifierForFirstTenor\&quot;},{\&quot;ClientInternal\&quot;: \&quot;SomeIdentifierForSecondTenor\&quot;}
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
var instance = JsonConvert.DeserializeObject<FxForwardCurveByQuoteReference>(json);
```


- [MarketDataOptions](MarketDataOptions.md)
- [FxTenorConvention](FxTenorConvention.md) — used in `Calendars`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

