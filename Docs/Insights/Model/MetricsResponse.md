# Finbourne.Sdk.Insights.Model.MetricsResponse

The aggregated platform metrics for a domain: one nullable, strongly-typed property per data set.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Required | When this response was assembled, in UTC. Every data set in the response was resolved against this instant. |
| **Domain** | **string** | Required | The domain the metrics are for, resolved from the authenticated request rather than from any parameter. |
| **RequestsPerMinute** | [RequestsPerMinuteDataSet](RequestsPerMinuteDataSet.md) | Optional | *No description available.* |
| **ServiceEndpointDurations24h** | [ServiceEndpointDurations24hDataSet](ServiceEndpointDurations24hDataSet.md) | Optional | *No description available.* |
| **ServiceRequests24h** | [ServiceRequests24hDataSet](ServiceRequests24hDataSet.md) | Optional | *No description available.* |
| **IdentityMetrics** | [IdentityMetricsDataSet](IdentityMetricsDataSet.md) | Optional | *No description available.* |
| **NotIncluded** | **List&lt;string&gt;** | Required | The data sets the caller excluded via the &#x60;include&#x60; parameter, and which were therefore never queried. Each value is one of the Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet values. |
| **Failed** | [List&lt;MetricDataSetFailure&gt;](MetricDataSetFailure.md) | Required | The data sets that were requested but could not be returned, each with a caller-safe reason. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new MetricsResponse(
    asAt: DateTimeOffset.Now,  // required — When this response was assembled, in UTC. Every data set in the response was resolved against this instant.
    domain: "...",  // required — The domain the metrics are for, resolved from the authenticated request rather than from any parameter.
    requestsPerMinute: new RequestsPerMinuteDataSet(...),  // optional
    serviceEndpointDurations24h: new ServiceEndpointDurations24hDataSet(...),  // optional
    serviceRequests24h: new ServiceRequests24hDataSet(...),  // optional
    identityMetrics: new IdentityMetricsDataSet(...),  // optional
    notIncluded: ,  // required — The data sets the caller excluded via the &#x60;include&#x60; parameter, and which were therefore never queried. Each value is one of the Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet values.
    failed: new List<MetricDataSetFailure>(),  // required — The data sets that were requested but could not be returned, each with a caller-safe reason.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetricsResponse>(json);
```

- [RequestsPerMinuteDataSet](RequestsPerMinuteDataSet.md)
- [ServiceEndpointDurations24hDataSet](ServiceEndpointDurations24hDataSet.md)
- [ServiceRequests24hDataSet](ServiceRequests24hDataSet.md)
- [IdentityMetricsDataSet](IdentityMetricsDataSet.md)
- [MetricDataSetFailure](MetricDataSetFailure.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

