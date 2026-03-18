# Finbourne.Sdk.Lusid.Model.AggregatedReturnsRequest

The request used in the AggregatedReturns.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Metrics** | [List&lt;PerformanceReturnsMetric&gt;](PerformanceReturnsMetric.md) | Required | A list of metrics to calculate in the AggregatedReturns. |
| **ReturnIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | The Scope and code of the returns. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CompositeMethod** | **string** | Optional | The method used to calculate the Portfolio performance: Equal/Asset. |
| **Period** | **string** | Optional | The type of the returns used to calculate the aggregation result: Daily/Monthly. |
| **OutputFrequency** | **string** | Optional | The type of calculated output: Daily/Weekly/Monthly/Quarterly/Half-Yearly/Yearly. |
| **AlternativeInceptionDate** | **string** | Optional | Optional - either a date, or the key for a portfolio property containing a date. If provided, the given date will override the inception date for this request. |
| **HolidayCalendars** | **List&lt;string&gt;** | Optional | The holiday calendar(s) that should be used in determining the date schedule. Holiday calendar(s) are supplied by their codes, for example, &#39;CoppClark&#39;. Note that when the calendars are not available (e.g. when the user has insufficient permissions), a recipe setting will be used to determine whether the whole batch should then fail or whether the calendar not being available should simply be ignored. |
| **Currency** | **string** | Optional | Optional - either a string or a property. If provided, the results will be converted to the specified currency |
| **RunMode** | **string** | Optional | The dates the AggregatedReturns output will be calculated: ReturnData/WeekDays/AllDays/MonthEnd. Defaults to ReturnData. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregatedReturnsRequest(
    metrics: new List<PerformanceReturnsMetric>(),  // required — A list of metrics to calculate in the AggregatedReturns.
    returnIds: new List<ResourceId>(),  // optional — The Scope and code of the returns.
    recipeId: new ResourceId(...),  // optional
    compositeMethod: "...",  // optional — The method used to calculate the Portfolio performance: Equal/Asset.
    period: "...",  // optional — The type of the returns used to calculate the aggregation result: Daily/Monthly.
    outputFrequency: "...",  // optional — The type of calculated output: Daily/Weekly/Monthly/Quarterly/Half-Yearly/Yearly.
    alternativeInceptionDate: "...",  // optional — Optional - either a date, or the key for a portfolio property containing a date. If provided, the given date will override the inception date for this request.
    holidayCalendars: ,  // optional — The holiday calendar(s) that should be used in determining the date schedule. Holiday calendar(s) are supplied by their codes, for example, &#39;CoppClark&#39;. Note that when the calendars are not available (e.g. when the user has insufficient permissions), a recipe setting will be used to determine whether the whole batch should then fail or whether the calendar not being available should simply be ignored.
    currency: "...",  // optional — Optional - either a string or a property. If provided, the results will be converted to the specified currency
    runMode: "..."  // optional — The dates the AggregatedReturns output will be calculated: ReturnData/WeekDays/AllDays/MonthEnd. Defaults to ReturnData.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregatedReturnsRequest>(json);
```


## Related Models

- [PerformanceReturnsMetric](PerformanceReturnsMetric.md) — used in `Metrics`
- [ResourceId](ResourceId.md) — used in `ReturnIds`
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

