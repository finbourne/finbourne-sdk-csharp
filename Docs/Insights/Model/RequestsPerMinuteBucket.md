# Finbourne.Sdk.Insights.Model.RequestsPerMinuteBucket

One minute of request activity for a single service and endpoint.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MinuteBucket** | **DateTimeOffset** | Required | Start of the whole minute this row covers, in UTC. |
| **Service** | **string** | Optional | The name of the service (application) that handled the requests. |
| **Endpoint** | **string** | Optional | The endpoint (API operation) the requests were made to. |
| **TotalRequests** | **long?** | Optional | The number of requests in this minute, or null if not reported. |
| **Requests5xx** | **long?** | Optional | The number of requests in this minute that returned a 5xx status code, or null if not reported. |
| **DurationSumMs** | **decimal?** | Optional | The sum of the request durations in this minute, in milliseconds, or null if not reported. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new RequestsPerMinuteBucket(
    minuteBucket: DateTimeOffset.Now,  // required — Start of the whole minute this row covers, in UTC.
    service: "...",  // optional — The name of the service (application) that handled the requests.
    endpoint: "...",  // optional — The endpoint (API operation) the requests were made to.
    totalRequests: 0L,  // optional — The number of requests in this minute, or null if not reported.
    requests5xx: 0L,  // optional — The number of requests in this minute that returned a 5xx status code, or null if not reported.
    durationSumMs: 0.0d  // optional — The sum of the request durations in this minute, in milliseconds, or null if not reported.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequestsPerMinuteBucket>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

