# Finbourne.Sdk.Lusid.Model.AppendFxForwardCurveByQuoteReference

Used to append a new point to an FX curve defined using `FxForwardCurveByQuoteReference`.
> **Inherits from:** [AppendMarketData](AppendMarketData.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Tenor** | **string** | Required | Tenor for which the forward rate applies. |
| **QuoteReference** | **Dictionary&lt;string, string&gt;** | Required | A collection of identifiers for the tenor, which will be used to query the LUSID Quote Store to resolve the actual rates.  The keys must be chosen from the following enumeration:  [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].    For example:    \&quot;quoteReference\&quot;: {\&quot;ClientInternal\&quot;: \&quot;SomeIdentifierForTenor\&quot;} |
| **MarketDataType** | **string** | Required | The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData Default: `MarketDataTypeEnum.AppendFxForwardCurveByQuoteReference` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AppendFxForwardCurveByQuoteReference(
    tenor: "...",  // required — Tenor for which the forward rate applies.
    quoteReference: ,  // required — A collection of identifiers for the tenor, which will be used to query the LUSID Quote Store to resolve the actual rates.  The keys must be chosen from the following enumeration:  [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].    For example:    \&quot;quoteReference\&quot;: {\&quot;ClientInternal\&quot;: \&quot;SomeIdentifierForTenor\&quot;}
    marketDataType: "..."  // required — The available values are: AppendFxForwardCurveByQuoteReference, AppendFxForwardCurveData, AppendFxForwardPipsCurveData, AppendFxForwardTenorCurveData, AppendFxForwardTenorPipsCurveData
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AppendFxForwardCurveByQuoteReference>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

