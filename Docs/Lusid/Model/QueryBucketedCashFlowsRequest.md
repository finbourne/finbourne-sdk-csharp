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
| **RoundingMethod** | **string** | Required | When bucketing, there is not a unique way to allocate the bucket points.  RoundingMethod Supported string (enumeration) values are: [RoundDown, RoundUp]. |
| **BucketingDates** | **List&lt;DateTimeOffset&gt;** | Optional | A list of dates to perform cashflow bucketing upon.  If this is provided, the list of tenors for bucketing should be empty. |
| **BucketingTenors** | **List&lt;string&gt;** | Optional | A list of tenors to perform cashflow bucketing upon.  If this is provided, the list of dates for bucketing should be empty. |
| **ReportCurrency** | **string** | Required | Three letter ISO currency string indicating what currency to report in for ReportCurrency denominated queries. |
| **GroupBy** | **List&lt;string&gt;** | Optional | The set of items by which to perform grouping. This primarily matters when one or more of the metric operators is a mapping  that reduces set size, e.g. sum or proportion. The group-by statement determines the set of keys by which to break the results out. |
| **Addresses** | **List&lt;string&gt;** | Optional | The set of items that the user wishes to see in the results. If empty, will be defaulted to standard ones. |
| **EquipWithSubtotals** | **bool** | Optional | Flag directing the Valuation call to populate the results with subtotals of aggregates. |
| **ExcludeUnsettledTrades** | **bool** | Optional | Flag directing the Valuation call to exclude cashflows from unsettled trades.  If absent or set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. If set to true, unsettled trades will be excluded from the result set. |
| **CashFlowType** | **string** | Optional | Indicate the requested cash flow representation InstrumentCashFlows or PortfolioCashFlows (GetCashLadder uses this)  Options: [InstrumentCashFlow, PortfolioCashFlow] |
| **BucketingSchedule** | [BucketingSchedule](BucketingSchedule.md) | Optional | *No description available.* |
| **Filter** | **string** | Optional | *No description available.* |


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
    roundingMethod: "...",  // required — When bucketing, there is not a unique way to allocate the bucket points.  RoundingMethod Supported string (enumeration) values are: [RoundDown, RoundUp].
    bucketingDates: ,  // optional — A list of dates to perform cashflow bucketing upon.  If this is provided, the list of tenors for bucketing should be empty.
    bucketingTenors: ,  // optional — A list of tenors to perform cashflow bucketing upon.  If this is provided, the list of dates for bucketing should be empty.
    reportCurrency: "...",  // required — Three letter ISO currency string indicating what currency to report in for ReportCurrency denominated queries.
    groupBy: ,  // optional — The set of items by which to perform grouping. This primarily matters when one or more of the metric operators is a mapping  that reduces set size, e.g. sum or proportion. The group-by statement determines the set of keys by which to break the results out.
    addresses: ,  // optional — The set of items that the user wishes to see in the results. If empty, will be defaulted to standard ones.
    equipWithSubtotals: true,  // optional — Flag directing the Valuation call to populate the results with subtotals of aggregates.
    excludeUnsettledTrades: true,  // optional — Flag directing the Valuation call to exclude cashflows from unsettled trades.  If absent or set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. If set to true, unsettled trades will be excluded from the result set.
    cashFlowType: "...",  // optional — Indicate the requested cash flow representation InstrumentCashFlows or PortfolioCashFlows (GetCashLadder uses this)  Options: [InstrumentCashFlow, PortfolioCashFlow]
    bucketingSchedule: new BucketingSchedule(...),  // optional
    filter: "..."  // optional
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


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

