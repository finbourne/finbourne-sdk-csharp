# Finbourne.Sdk.Insights.Model.ServiceEndpointDurations24hDataSet

Request duration distribution per service and endpoint over a rolling twenty four hour window.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of this data set. Always &#x60;ServiceEndpointDurations24h&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property. |
| **WindowStart** | **DateTimeOffset** | Required | Inclusive start of the window the data covers, in UTC, floored to a whole minute. |
| **WindowEnd** | **DateTimeOffset** | Required | End of the window the data covers, in UTC, floored to a whole minute. |
| **Truncated** | **bool** | Required | True when the query reached the row cap, so some services or endpoints are missing. False when the whole result set was returned. |
| **Values** | [List&lt;ServiceEndpointDuration&gt;](ServiceEndpointDuration.md) | Required | The rows, ordered by service then endpoint. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ServiceEndpointDurations24hDataSet(
    name: "...",  // required — The name of this data set. Always &#x60;ServiceEndpointDurations24h&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property.
    windowStart: DateTimeOffset.Now,  // required — Inclusive start of the window the data covers, in UTC, floored to a whole minute.
    windowEnd: DateTimeOffset.Now,  // required — End of the window the data covers, in UTC, floored to a whole minute.
    truncated: true,  // required — True when the query reached the row cap, so some services or endpoints are missing. False when the whole result set was returned.
    values: new List<ServiceEndpointDuration>()  // required — The rows, ordered by service then endpoint.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ServiceEndpointDurations24hDataSet>(json);
```

- [ServiceEndpointDuration](ServiceEndpointDuration.md) — used in `Values`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

