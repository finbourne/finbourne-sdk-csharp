# Finbourne.Sdk.Insights.Model.IdentityMetricsDataSet

Identity population and activity counts for the domain, pivoted from the latest tranche the identity metrics provider collected.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of this data set. Always &#x60;IdentityMetrics&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property. |
| **CollectedAt** | **DateTimeOffset?** | Optional | The timestamp of the tranche these values were collected in, in UTC, or null if no tranche was returned. |
| **PersonalUsers** | **long?** | Optional | The number of personal (human) users in the domain, or null if not reported. |
| **ServiceUsers** | **long?** | Optional | The number of service users in the domain, or null if not reported. |
| **NeverLoggedIn** | **long?** | Optional | The number of users that have never logged in, or null if not reported. |
| **Ignored** | **long?** | Optional | The number of users excluded from the other counts, or null if not reported. |
| **AccountLocked** | **long?** | Optional | The number of users whose account is locked, or null if not reported. |
| **SuspendedPwReset** | **long?** | Optional | The number of users suspended pending a password reset, or null if not reported. |
| **CreatedLast24Hours** | **long?** | Optional | The number of users created in the last 24 hours, or null if not reported. |
| **CreatedLast7Days** | **long?** | Optional | The number of users created in the last 7 days, or null if not reported. |
| **CreatedLast30Days** | **long?** | Optional | The number of users created in the last 30 days, or null if not reported. |
| **ActiveLast24Hours** | **long?** | Optional | The number of users active in the last 24 hours, or null if not reported. |
| **ActiveLast7Days** | **long?** | Optional | The number of users active in the last 7 days, or null if not reported. |
| **ActiveLast30Days** | **long?** | Optional | The number of users active in the last 30 days, or null if not reported. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new IdentityMetricsDataSet(
    name: "...",  // required — The name of this data set. Always &#x60;IdentityMetrics&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property.
    collectedAt: DateTimeOffset.Now,  // optional — The timestamp of the tranche these values were collected in, in UTC, or null if no tranche was returned.
    personalUsers: 0L,  // optional — The number of personal (human) users in the domain, or null if not reported.
    serviceUsers: 0L,  // optional — The number of service users in the domain, or null if not reported.
    neverLoggedIn: 0L,  // optional — The number of users that have never logged in, or null if not reported.
    ignored: 0L,  // optional — The number of users excluded from the other counts, or null if not reported.
    accountLocked: 0L,  // optional — The number of users whose account is locked, or null if not reported.
    suspendedPwReset: 0L,  // optional — The number of users suspended pending a password reset, or null if not reported.
    createdLast24Hours: 0L,  // optional — The number of users created in the last 24 hours, or null if not reported.
    createdLast7Days: 0L,  // optional — The number of users created in the last 7 days, or null if not reported.
    createdLast30Days: 0L,  // optional — The number of users created in the last 30 days, or null if not reported.
    activeLast24Hours: 0L,  // optional — The number of users active in the last 24 hours, or null if not reported.
    activeLast7Days: 0L,  // optional — The number of users active in the last 7 days, or null if not reported.
    activeLast30Days: 0L  // optional — The number of users active in the last 30 days, or null if not reported.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IdentityMetricsDataSet>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

