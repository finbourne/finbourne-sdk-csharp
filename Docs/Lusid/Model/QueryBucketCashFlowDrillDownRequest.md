# Finbourne.Sdk.Lusid.Model.QueryBucketCashFlowDrillDownRequest

Query for the individual cashflows inside a single cashflow bucket, with their source lineage.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The time of the system at which to query for cashflows. |
| **BucketStart** | **DateTimeOffset** | Required | The lower bound effective datetime of the bucket from which to retrieve the cashflows. |
| **BucketEnd** | **DateTimeOffset** | Required | The upper bound effective datetime of the bucket from which to retrieve the cashflows. |
| **StartInclusive** | **bool** | Optional | Whether a cashflow paid exactly on the bucket start is included in the bucket. Defaults to true. |
| **EndInclusive** | **bool** | Optional | Whether a cashflow paid exactly on the bucket end is included in the bucket. Defaults to true. |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The set of portfolios and portfolio groups to which the cashflows must belong. |
| **EffectiveAt** | **DateTimeOffset** | Required | The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up. |
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ReportCurrency** | **string** | Optional | Optional three letter ISO currency string to convert cashflow amounts into. When supplied, each returned cashflow additionally carries ReportCurrencyAmount and TradeToReportCurrencyRate, converted from its own payment (instrument) currency. When omitted, those two fields are not present on any cashflow: Amount (always in the cashflow&#39;s own payment currency) are unaffected either way. |
| **ExcludeUnsettledTrades** | **bool** | Optional | If set to true, unsettled trades are excluded from the result set. Set this to match the value used on the bucketed cash flow query being drilled into, so the individual cash flows reconcile with the bucket. Note that the drill-down returns the complete resolved stream including transaction-sourced cashflows; if the bucketed query used the (default) InstrumentCashFlow representation, also exclude rows with a sourceType of &#39;Transaction&#39; when reconciling. |
| **HaircutRules** | [List&lt;CashFlowHaircutRule&gt;](CashFlowHaircutRule.md) | Optional | Optional ordered haircut rules applied to cashflow inflows; the first matching rule wins and a rule with no criteria acts as a catch-all. When supplied, each returned cashflow carries its gross amount, haircut fraction, net amount and the rule that was applied; with no rules those fields are omitted and the results are unchanged. |
| **CashType** | **string** | Optional | Which date basis buckets cash flows: TradeDate uses each cash flow&#39;s transaction date, SettleDate (default) uses its payment date. The response&#39;s CashFlowDetail.PaymentDate reflects whichever basis was used. Available values: TradeDate, SettleDate. |
| **FxRateType** | **string** | Optional | Which FX rate converts each cashflow into the ReportCurrency. FxSpot (default) uses the spot rate as at the valuation (EffectiveAt) date for every cashflow, as QueryBucketedCashFlows converts them. FxSpotAtCashFlowDate uses the spot rate as at the cashflow&#39;s own date, or as at the valuation date for a cashflow dated after it. FxForward uses the forward rate for the cashflow&#39;s payment date, read from the FX forward curve the recipe resolves for the currency pair as at the valuation (EffectiveAt) date; a cashflow with no such forward rate reports an Error and has no converted amount. ForwardThenSpot uses the forward rate where the recipe resolves one and the spot rate where it does not. All but FxSpot require a ReportCurrency. A cashflow paid after the last point of the recipe&#39;s forward curve takes the last point&#39;s forward rate when the curve&#39;s back extrapolation is Flat (the default), and reports an Error when it is None. Where ForwardThenSpot falls back, the spot rate is the one FxSpot uses: as at the valuation date. The balances in the report currency are those QueryBucketedCashFlows returns for FxSpot. With any other rate type they are a running balance of the cashflows at the rates above, with a starting balance at the spot as at the window start for FxSpotAtCashFlowDate and as at the valuation date for FxForward and ForwardThenSpot; it chains across buckets, and is not QueryBucketedCashFlows&#39; figure. The response&#39;s CashFlowDetail.FxRateTypeApplied says which rate each cashflow received. Available values: FxSpot, FxForward, ForwardThenSpot, FxSpotAtCashFlowDate. |
| **WindowStart** | **DateTimeOffset** | Required | Where the ladder opens: the window start of the bucketed request being drilled into, on or before BucketStart. The opening balance of the first bucket is the ladder&#39;s balance at BucketStart. Required. |
| **StartingBalance** | **string** | Optional | The balance the ladder opens with: &#39;Zero&#39; (default) or &#39;PortfolioCashBalance&#39;. &#39;PortfolioCashBalance&#39; is not supported with a CashType of &#39;TradeDate&#39;. Available values: PortfolioCashBalance, Zero. |
| **BucketingSchedule** | [BucketingSchedule](BucketingSchedule.md) | Required | *No description available.* |
| **RoundingMethod** | **string** | Optional | How a cash flow is allocated to a period. Only RoundUp, the default, is supported; RoundDown is refused. Which period a cash flow on a boundary falls in is decided by StartInclusive and EndInclusive. Available values: RoundUp, RoundDown. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryBucketCashFlowDrillDownRequest(
    asAt: DateTimeOffset.Now,  // optional — The time of the system at which to query for cashflows.
    bucketStart: DateTimeOffset.Now,  // required — The lower bound effective datetime of the bucket from which to retrieve the cashflows.
    bucketEnd: DateTimeOffset.Now,  // required — The upper bound effective datetime of the bucket from which to retrieve the cashflows.
    startInclusive: true,  // optional — Whether a cashflow paid exactly on the bucket start is included in the bucket. Defaults to true.
    endInclusive: true,  // optional — Whether a cashflow paid exactly on the bucket end is included in the bucket. Defaults to true.
    portfolioEntityIds: new List<PortfolioEntityId>(),  // required — The set of portfolios and portfolio groups to which the cashflows must belong.
    effectiveAt: DateTimeOffset.Now,  // required — The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up.
    recipeId: new ResourceId(...),  // required
    reportCurrency: "...",  // optional — Optional three letter ISO currency string to convert cashflow amounts into. When supplied, each returned cashflow additionally carries ReportCurrencyAmount and TradeToReportCurrencyRate, converted from its own payment (instrument) currency. When omitted, those two fields are not present on any cashflow: Amount (always in the cashflow&#39;s own payment currency) are unaffected either way.
    excludeUnsettledTrades: true,  // optional — If set to true, unsettled trades are excluded from the result set. Set this to match the value used on the bucketed cash flow query being drilled into, so the individual cash flows reconcile with the bucket. Note that the drill-down returns the complete resolved stream including transaction-sourced cashflows; if the bucketed query used the (default) InstrumentCashFlow representation, also exclude rows with a sourceType of &#39;Transaction&#39; when reconciling.
    haircutRules: new List<CashFlowHaircutRule>(),  // optional — Optional ordered haircut rules applied to cashflow inflows; the first matching rule wins and a rule with no criteria acts as a catch-all. When supplied, each returned cashflow carries its gross amount, haircut fraction, net amount and the rule that was applied; with no rules those fields are omitted and the results are unchanged.
    cashType: "...",  // optional — Which date basis buckets cash flows: TradeDate uses each cash flow&#39;s transaction date, SettleDate (default) uses its payment date. The response&#39;s CashFlowDetail.PaymentDate reflects whichever basis was used. Available values: TradeDate, SettleDate.
    fxRateType: "...",  // optional — Which FX rate converts each cashflow into the ReportCurrency. FxSpot (default) uses the spot rate as at the valuation (EffectiveAt) date for every cashflow, as QueryBucketedCashFlows converts them. FxSpotAtCashFlowDate uses the spot rate as at the cashflow&#39;s own date, or as at the valuation date for a cashflow dated after it. FxForward uses the forward rate for the cashflow&#39;s payment date, read from the FX forward curve the recipe resolves for the currency pair as at the valuation (EffectiveAt) date; a cashflow with no such forward rate reports an Error and has no converted amount. ForwardThenSpot uses the forward rate where the recipe resolves one and the spot rate where it does not. All but FxSpot require a ReportCurrency. A cashflow paid after the last point of the recipe&#39;s forward curve takes the last point&#39;s forward rate when the curve&#39;s back extrapolation is Flat (the default), and reports an Error when it is None. Where ForwardThenSpot falls back, the spot rate is the one FxSpot uses: as at the valuation date. The balances in the report currency are those QueryBucketedCashFlows returns for FxSpot. With any other rate type they are a running balance of the cashflows at the rates above, with a starting balance at the spot as at the window start for FxSpotAtCashFlowDate and as at the valuation date for FxForward and ForwardThenSpot; it chains across buckets, and is not QueryBucketedCashFlows&#39; figure. The response&#39;s CashFlowDetail.FxRateTypeApplied says which rate each cashflow received. Available values: FxSpot, FxForward, ForwardThenSpot, FxSpotAtCashFlowDate.
    windowStart: DateTimeOffset.Now,  // required — Where the ladder opens: the window start of the bucketed request being drilled into, on or before BucketStart. The opening balance of the first bucket is the ladder&#39;s balance at BucketStart. Required.
    startingBalance: "...",  // optional — The balance the ladder opens with: &#39;Zero&#39; (default) or &#39;PortfolioCashBalance&#39;. &#39;PortfolioCashBalance&#39; is not supported with a CashType of &#39;TradeDate&#39;. Available values: PortfolioCashBalance, Zero.
    bucketingSchedule: new BucketingSchedule(...),  // required
    roundingMethod: "..."  // optional — How a cash flow is allocated to a period. Only RoundUp, the default, is supported; RoundDown is refused. Which period a cash flow on a boundary falls in is decided by StartInclusive and EndInclusive. Available values: RoundUp, RoundDown.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryBucketCashFlowDrillDownRequest>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [ResourceId](ResourceId.md)
- [CashFlowHaircutRule](CashFlowHaircutRule.md) — used in `HaircutRules`
- [BucketingSchedule](BucketingSchedule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

