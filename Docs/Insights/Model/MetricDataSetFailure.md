# Finbourne.Sdk.Insights.Model.MetricDataSetFailure

Names a metric data set that was requested but could not be returned, with a caller-safe explanation.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The data set that could not be returned. One of the Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet values, and identical to the name of the Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property that would have carried it. |
| **Reason** | **string** | Required | A generic, caller-safe explanation of why the data set is missing. Never contains provider names, query text, internal service names or exception detail. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new MetricDataSetFailure(
    name: "...",  // required — The data set that could not be returned. One of the Finbourne.Insights.WebApi.Dtos.Metrics.MetricDataSet values, and identical to the name of the Finbourne.Insights.WebApi.Dtos.Metrics.MetricsResponse property that would have carried it.
    reason: "..."  // required — A generic, caller-safe explanation of why the data set is missing. Never contains provider names, query text, internal service names or exception detail.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetricDataSetFailure>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

