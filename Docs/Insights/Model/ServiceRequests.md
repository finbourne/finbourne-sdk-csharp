# Finbourne.Sdk.Insights.Model.ServiceRequests

The request volume and server-error rate for a single service over the window.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Service** | **string** | Optional | The name of the service (application) that handled the requests. |
| **TotalRequests** | **long?** | Optional | The number of requests over the window, or null if not reported. |
| **Requests5xx** | **long?** | Optional | The number of requests over the window that returned a 5xx status code, or null if not reported. |
| **Pct5xx** | **decimal?** | Optional | The percentage of requests that returned a 5xx status code, or null if not reported. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new ServiceRequests(
    service: "...",  // optional — The name of the service (application) that handled the requests.
    totalRequests: 0L,  // optional — The number of requests over the window, or null if not reported.
    requests5xx: 0L,  // optional — The number of requests over the window that returned a 5xx status code, or null if not reported.
    pct5xx: 0.0d  // optional — The percentage of requests that returned a 5xx status code, or null if not reported.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ServiceRequests>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

