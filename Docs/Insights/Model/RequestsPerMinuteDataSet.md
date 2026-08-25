# Finbourne.Sdk.Insights.Model.RequestsPerMinuteDataSet

Request volume, error count and total duration per minute, broken down by service and endpoint, over a rolling three hour window.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of this data set. Always &#x60;RequestsPerMinute&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property. |
| **WindowStart** | **DateTimeOffset** | Required | Inclusive start of the window the data covers, in UTC, floored to a whole minute. |
| **WindowEnd** | **DateTimeOffset** | Required | End of the window the data covers, in UTC, floored to a whole minute. |
| **Truncated** | **bool** | Required | True when the query reached the row cap, so the data covers only part of the window and totals are understated. False when the whole window was returned. |
| **Values** | [List&lt;RequestsPerMinuteBucket&gt;](RequestsPerMinuteBucket.md) | Required | The per-minute rows, ordered by minute, then service, then endpoint. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new RequestsPerMinuteDataSet(
    name: "...",  // required — The name of this data set. Always &#x60;RequestsPerMinute&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property.
    windowStart: DateTimeOffset.Now,  // required — Inclusive start of the window the data covers, in UTC, floored to a whole minute.
    windowEnd: DateTimeOffset.Now,  // required — End of the window the data covers, in UTC, floored to a whole minute.
    truncated: true,  // required — True when the query reached the row cap, so the data covers only part of the window and totals are understated. False when the whole window was returned.
    values: new List<RequestsPerMinuteBucket>()  // required — The per-minute rows, ordered by minute, then service, then endpoint.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequestsPerMinuteDataSet>(json);
```

- [RequestsPerMinuteBucket](RequestsPerMinuteBucket.md) — used in `Values`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

