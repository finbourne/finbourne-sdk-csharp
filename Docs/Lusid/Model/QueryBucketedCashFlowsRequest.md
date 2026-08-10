# Finbourne.Sdk.Lusid.Model.QueryBucketedCashFlowsRequest

Query for bucketed cashflows from one or more portfolios.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The time of the system at which to query for bucketed cashflows. |
| **WindowStart** | **DateTimeOffset** | Required | The lower bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.  There is no lower bound if this is not specified. |
| **WindowEnd** | **DateTimeOffset** | Required | The upper bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.  The upper bound defaults to &#39;today&#39; if it is not specified |
| **PortfolioEntityIds** | [List&lt;PortfolioEntityId&gt;](PortfolioEntityId.md) | Required | The set of portfolios and portfolio groups to which the instrument events must belong. |
| **EffectiveAt** | **DateTimeOffset** | Required | The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up.  For example, on a swap if the effectiveAt is in the middle of the window, cashflows before it will be historic and resets assumed to exist where if the effectiveAt  is before the start of the range they are forward looking and will be expectations assuming the model supports that.  There is evidently a presumption here about availability of data and that the effectiveAt is realistically on or before the real-world today. |
| **RecipeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RoundingMethod** | **string** | Required | When bucketing, there is not a unique way to allocate the bucket points. Available values: RoundUp, RoundDown. |
| **BucketingDates** | **List&lt;DateTimeOffset&gt;** | Optional | A list of dates to perform cashflow bucketing upon.  If this is provided, the list of tenors for bucketing should be empty. |
| **BucketingTenors** | **List&lt;string&gt;** | Optional | A list of tenors to perform cashflow bucketing upon.  If this is provided, the list of dates for bucketing should be empty. |
| **ReportCurrency** | **string** | Required | Three letter ISO currency string indicating what currency to report in for ReportCurrency denominated queries. |
| **GroupBy** | **List&lt;string&gt;** | Optional | The set of items by which to perform grouping. This primarily matters when one or more of the metric operators is a mapping  that reduces set size, e.g. sum or proportion. The group-by statement determines the set of keys by which to break the results out. |
| **Addresses** | **List&lt;string&gt;** | Optional | The set of items that the user wishes to see in the results. If empty, will be defaulted to standard ones. |
| **EquipWithSubtotals** | **bool** | Optional | Flag directing the Valuation call to populate the results with subtotals of aggregates. |
| **ExcludeUnsettledTrades** | **bool** | Optional | Flag directing the Valuation call to exclude cashflows from unsettled trades.  If absent or set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. If set to true, unsettled trades will be excluded from the result set. |
| **CashFlowType** | **string** | Optional | Indicate the requested cash flow representation. Supported string (enumeration) values are: [InstrumentCashFlow, PortfolioCashFlow, TransactionCashFlow]. Defaults to &#39;InstrumentCashFlow&#39; (GetCashLadder uses PortfolioCashFlow). Available values: InstrumentCashFlow, PortfolioCashFlow, TransactionCashFlow. |
| **BucketingSchedule** | [BucketingSchedule](BucketingSchedule.md) | Optional | *No description available.* |
| **Filter** | **string** | Optional | *No description available.* |
| **CashFlowCalculationVersion** | **string** | Optional | The version of the cash flow calculation logic to use. Defaults to &#39;1&#39; if not specified. Valid values are &#39;1&#39; and &#39;2&#39;.  &#39;1&#39; is the current production behaviour: cash flows booked as transactions are de-duplicated against the  instrument cash flows by identifier, and movements are treated as factual when they settle on or before the effective date.  &#39;2&#39; resolves cash flows via a deterministic source waterfall (structured result store &gt; transaction &gt; instrument),  classifies cash flows as factual by the transaction trade date (so trades dealt on or before the effective date  that settle afterwards are factual), and applies corporate action date filtering.  Bucketed responses calculated under version &#39;2&#39; always include the bucket interval metadata columns  (&#39;Valuation/Bucket/Start&#39;, &#39;Valuation/Bucket/End&#39;, &#39;Valuation/Bucket/StartInclusive&#39;, &#39;Valuation/Bucket/EndInclusive&#39;),  which are the required input of the bucket cash flow drill-down endpoint. Without a border configuration the  metadata describes the window-clamped interval of cash flow dates that the rounding method allocates to each bucket point. |
| **HaircutRules** | [List&lt;CashFlowHaircutRule&gt;](CashFlowHaircutRule.md) | Optional | Optional ordered haircut rules applied to cashflow inflows; the first matching rule wins and a rule with no criteria acts as a catch-all. When supplied, the additional per-bucket columns &#39;Valuation/Bucket/HaircutAmount&#39; and &#39;Valuation/Bucket/NetOfHaircutAmount&#39; are produced; with no rules the results are unchanged. Only supported for the InstrumentCashFlow CashFlowType. |
| **BorderConfiguration** | [BucketBorderConfiguration](BucketBorderConfiguration.md) | Optional | *No description available.* |
| **StartingBalance** | **string** | Optional | The balance to use at the start of the bucketing window when computing open/close balances.  Supported string (enumeration) values are: [PortfolioCashBalance, Zero].  When supplied, the additional per-bucket running balance columns &#39;Valuation/Bucket/OpenBalance&#39; and &#39;Valuation/Bucket/CloseBalance&#39; are produced  per group, in the currency of the group&#39;s cash flows: the first bucket opens at zero (&#39;Zero&#39;) or at the portfolio cash balance at the window  start (&#39;PortfolioCashBalance&#39;), and each subsequent bucket opens at the previous bucket&#39;s close balance. When absent, no balance columns are  produced and the results are unchanged. &#39;PortfolioCashBalance&#39; is only supported for the PortfolioCashFlow and TransactionCashFlow CashFlowTypes. Available values: PortfolioCashBalance, Zero. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QueryBucketedCashFlowsRequest(
    asAt: DateTimeOffset.Now,  // optional — The time of the system at which to query for bucketed cashflows.
    windowStart: DateTimeOffset.Now,  // required — The lower bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.  There is no lower bound if this is not specified.
    windowEnd: DateTimeOffset.Now,  // required — The upper bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.  The upper bound defaults to &#39;today&#39; if it is not specified
    portfolioEntityIds: new List<PortfolioEntityId>(),  // required — The set of portfolios and portfolio groups to which the instrument events must belong.
    effectiveAt: DateTimeOffset.Now,  // required — The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up.  For example, on a swap if the effectiveAt is in the middle of the window, cashflows before it will be historic and resets assumed to exist where if the effectiveAt  is before the start of the range they are forward looking and will be expectations assuming the model supports that.  There is evidently a presumption here about availability of data and that the effectiveAt is realistically on or before the real-world today.
    recipeId: new ResourceId(...),  // required
    roundingMethod: "...",  // required — When bucketing, there is not a unique way to allocate the bucket points. Available values: RoundUp, RoundDown.
    bucketingDates: ,  // optional — A list of dates to perform cashflow bucketing upon.  If this is provided, the list of tenors for bucketing should be empty.
    bucketingTenors: ,  // optional — A list of tenors to perform cashflow bucketing upon.  If this is provided, the list of dates for bucketing should be empty.
    reportCurrency: "...",  // required — Three letter ISO currency string indicating what currency to report in for ReportCurrency denominated queries.
    groupBy: ,  // optional — The set of items by which to perform grouping. This primarily matters when one or more of the metric operators is a mapping  that reduces set size, e.g. sum or proportion. The group-by statement determines the set of keys by which to break the results out.
    addresses: ,  // optional — The set of items that the user wishes to see in the results. If empty, will be defaulted to standard ones.
    equipWithSubtotals: true,  // optional — Flag directing the Valuation call to populate the results with subtotals of aggregates.
    excludeUnsettledTrades: true,  // optional — Flag directing the Valuation call to exclude cashflows from unsettled trades.  If absent or set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. If set to true, unsettled trades will be excluded from the result set.
    cashFlowType: "...",  // optional — Indicate the requested cash flow representation. Supported string (enumeration) values are: [InstrumentCashFlow, PortfolioCashFlow, TransactionCashFlow]. Defaults to &#39;InstrumentCashFlow&#39; (GetCashLadder uses PortfolioCashFlow). Available values: InstrumentCashFlow, PortfolioCashFlow, TransactionCashFlow.
    bucketingSchedule: new BucketingSchedule(...),  // optional
    filter: "...",  // optional
    cashFlowCalculationVersion: "...",  // optional — The version of the cash flow calculation logic to use. Defaults to &#39;1&#39; if not specified. Valid values are &#39;1&#39; and &#39;2&#39;.  &#39;1&#39; is the current production behaviour: cash flows booked as transactions are de-duplicated against the  instrument cash flows by identifier, and movements are treated as factual when they settle on or before the effective date.  &#39;2&#39; resolves cash flows via a deterministic source waterfall (structured result store &gt; transaction &gt; instrument),  classifies cash flows as factual by the transaction trade date (so trades dealt on or before the effective date  that settle afterwards are factual), and applies corporate action date filtering.  Bucketed responses calculated under version &#39;2&#39; always include the bucket interval metadata columns  (&#39;Valuation/Bucket/Start&#39;, &#39;Valuation/Bucket/End&#39;, &#39;Valuation/Bucket/StartInclusive&#39;, &#39;Valuation/Bucket/EndInclusive&#39;),  which are the required input of the bucket cash flow drill-down endpoint. Without a border configuration the  metadata describes the window-clamped interval of cash flow dates that the rounding method allocates to each bucket point.
    haircutRules: new List<CashFlowHaircutRule>(),  // optional — Optional ordered haircut rules applied to cashflow inflows; the first matching rule wins and a rule with no criteria acts as a catch-all. When supplied, the additional per-bucket columns &#39;Valuation/Bucket/HaircutAmount&#39; and &#39;Valuation/Bucket/NetOfHaircutAmount&#39; are produced; with no rules the results are unchanged. Only supported for the InstrumentCashFlow CashFlowType.
    borderConfiguration: new BucketBorderConfiguration(...),  // optional
    startingBalance: "..."  // optional — The balance to use at the start of the bucketing window when computing open/close balances.  Supported string (enumeration) values are: [PortfolioCashBalance, Zero].  When supplied, the additional per-bucket running balance columns &#39;Valuation/Bucket/OpenBalance&#39; and &#39;Valuation/Bucket/CloseBalance&#39; are produced  per group, in the currency of the group&#39;s cash flows: the first bucket opens at zero (&#39;Zero&#39;) or at the portfolio cash balance at the window  start (&#39;PortfolioCashBalance&#39;), and each subsequent bucket opens at the previous bucket&#39;s close balance. When absent, no balance columns are  produced and the results are unchanged. &#39;PortfolioCashBalance&#39; is only supported for the PortfolioCashFlow and TransactionCashFlow CashFlowTypes. Available values: PortfolioCashBalance, Zero.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QueryBucketedCashFlowsRequest>(json);
```

- [PortfolioEntityId](PortfolioEntityId.md) — used in `PortfolioEntityIds`
- [ResourceId](ResourceId.md)
- [BucketingSchedule](BucketingSchedule.md)
- [CashFlowHaircutRule](CashFlowHaircutRule.md) — used in `HaircutRules`
- [BucketBorderConfiguration](BucketBorderConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

