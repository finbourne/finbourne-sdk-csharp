# Finbourne.Sdk.Lusid.Model.BucketCashFlowDrillDownResponse

The cash flows of a range of effective dates, split into periods by a BucketingSchedule: for each period, member portfolio,  payment currency and sub-holding key combination, its opening balance, the cash flows that make up its activity, and its  closing balance. Each balance and each cash flow appears once, in its bucket.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ReportCurrency** | **string** | Optional | The report currency the cash flows&#39; converted fields are in; absent when none was requested. |
| **WindowStart** | **DateTimeOffset** | Required | The window start the buckets&#39; balances run from: where the first bucket&#39;s opening balance is taken. |
| **Buckets** | [List&lt;BucketCashFlowBucket&gt;](BucketCashFlowBucket.md) | Required | One bucket per period of the schedule, per member portfolio, payment currency and sub-holding key combination, each with its  opening balance, activity and closing balance. |
| **CurrencySubtotals** | [List&lt;BucketCurrencySubtotal&gt;](BucketCurrencySubtotal.md) | Required | The buckets summed across portfolios and sub-holding keys, one per period and payment currency. |
| **Issues** | **List&lt;string&gt;** | Optional | What the balances do not cover, for example that they are in the payment currency only and gross of haircut; absent when there is nothing to report. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketCashFlowDrillDownResponse(
    reportCurrency: "...",  // optional — The report currency the cash flows&#39; converted fields are in; absent when none was requested.
    windowStart: DateTimeOffset.Now,  // required — The window start the buckets&#39; balances run from: where the first bucket&#39;s opening balance is taken.
    buckets: new List<BucketCashFlowBucket>(),  // required — One bucket per period of the schedule, per member portfolio, payment currency and sub-holding key combination, each with its  opening balance, activity and closing balance.
    currencySubtotals: new List<BucketCurrencySubtotal>(),  // required — The buckets summed across portfolios and sub-holding keys, one per period and payment currency.
    issues: ,  // optional — What the balances do not cover, for example that they are in the payment currency only and gross of haircut; absent when there is nothing to report.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketCashFlowDrillDownResponse>(json);
```

- [BucketCashFlowBucket](BucketCashFlowBucket.md) — used in `Buckets`
- [BucketCurrencySubtotal](BucketCurrencySubtotal.md) — used in `CurrencySubtotals`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

