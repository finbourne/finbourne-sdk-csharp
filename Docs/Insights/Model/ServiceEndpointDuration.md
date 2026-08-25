# Finbourne.Sdk.Insights.Model.ServiceEndpointDuration

The request duration distribution for a single service and endpoint over the window.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Service** | **string** | Optional | The name of the service (application) that handled the requests. |
| **Endpoint** | **string** | Optional | The endpoint (API operation) the requests were made to. |
| **TotalRequests** | **long?** | Optional | The number of requests over the window, or null if not reported. |
| **MeanDurationMs** | **decimal?** | Optional | The mean request duration in milliseconds, or null if not reported. |
| **MedianDurationMs** | **decimal?** | Optional | The median (50th percentile) request duration in milliseconds, or null if not reported. |
| **P95DurationMs** | **decimal?** | Optional | The 95th percentile request duration in milliseconds, or null if not reported. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ServiceEndpointDuration(
    service: "...",  // optional — The name of the service (application) that handled the requests.
    endpoint: "...",  // optional — The endpoint (API operation) the requests were made to.
    totalRequests: 0L,  // optional — The number of requests over the window, or null if not reported.
    meanDurationMs: 0.0d,  // optional — The mean request duration in milliseconds, or null if not reported.
    medianDurationMs: 0.0d,  // optional — The median (50th percentile) request duration in milliseconds, or null if not reported.
    p95DurationMs: 0.0d  // optional — The 95th percentile request duration in milliseconds, or null if not reported.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ServiceEndpointDuration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

