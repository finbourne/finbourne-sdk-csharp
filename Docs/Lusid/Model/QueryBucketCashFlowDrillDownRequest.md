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
| **ReportCurrency** | **string** | Required | Three letter ISO currency string indicating what currency to report in for ReportCurrency denominated queries. |
| **ExcludeUnsettledTrades** | **bool** | Optional | If set to true, unsettled trades are excluded from the result set. Set this to match the value used on the bucketed cash flow query being drilled into, so the individual cash flows reconcile with the bucket. |
| **HaircutRules** | [List&lt;CashFlowHaircutRule&gt;](CashFlowHaircutRule.md) | Optional | Optional ordered haircut rules applied to cashflow inflows; the first matching rule wins and a rule with no criteria acts as a catch-all. When supplied, each returned cashflow carries its gross amount, haircut fraction, net amount and the rule that was applied; with no rules those fields are omitted and the results are unchanged. |


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
    reportCurrency: "...",  // required — Three letter ISO currency string indicating what currency to report in for ReportCurrency denominated queries.
    excludeUnsettledTrades: true,  // optional — If set to true, unsettled trades are excluded from the result set. Set this to match the value used on the bucketed cash flow query being drilled into, so the individual cash flows reconcile with the bucket.
    haircutRules: new List<CashFlowHaircutRule>()  // optional — Optional ordered haircut rules applied to cashflow inflows; the first matching rule wins and a rule with no criteria acts as a catch-all. When supplied, each returned cashflow carries its gross amount, haircut fraction, net amount and the rule that was applied; with no rules those fields are omitted and the results are unchanged.
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


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

