# Finbourne.Sdk.Insights.Model.ServiceRequests24hDataSet

Request volume and server-error rate per service over a rolling twenty four hour window.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of this data set. Always &#x60;ServiceRequests24h&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property. |
| **WindowStart** | **DateTimeOffset** | Required | Inclusive start of the window the data covers, in UTC, floored to a whole minute. |
| **WindowEnd** | **DateTimeOffset** | Required | End of the window the data covers, in UTC, floored to a whole minute. |
| **Truncated** | **bool** | Required | True when the query reached the row cap, so some services are missing. False when the whole result set was returned. |
| **Values** | [List&lt;ServiceRequests&gt;](ServiceRequests.md) | Required | The rows, ordered by service. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ServiceRequests24hDataSet(
    name: "...",  // required — The name of this data set. Always &#x60;ServiceRequests24h&#x60;, matching the corresponding Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet value and Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property.
    windowStart: DateTimeOffset.Now,  // required — Inclusive start of the window the data covers, in UTC, floored to a whole minute.
    windowEnd: DateTimeOffset.Now,  // required — End of the window the data covers, in UTC, floored to a whole minute.
    truncated: true,  // required — True when the query reached the row cap, so some services are missing. False when the whole result set was returned.
    values: new List<ServiceRequests>()  // required — The rows, ordered by service.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ServiceRequests24hDataSet>(json);
```

- [ServiceRequests](ServiceRequests.md) — used in `Values`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

