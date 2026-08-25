# Finbourne.Sdk.Insights.Api.MetricsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetMetrics**](#getmetrics) | **GET** `/insights/api/metrics` | [EARLY ACCESS] GetMetrics: Get the aggregated platform metrics for the caller&#39;s domain. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Insights.Api;
using Finbourne.Sdk.Insights.Client;
using Finbourne.Sdk.Insights.Extensions;
using Finbourne.Sdk.Services.Insights.Model;
using Newtonsoft.Json;

// Use the ApiFactoryBuilder to build an instance of the API class.
// Credentials are loaded from the secrets.json file by default.
// See https://support.lusid.com/knowledgebase/article/KA-01667 for details.

var secretsFilename = "secrets.json";
var path = Path.Combine(Directory.GetCurrentDirectory(), secretsFilename);
// Replace with the relevant values
File.WriteAllText(
    path,
    @"{
        ""api"": {
            ""tokenUrl"": ""<your-token-url>"",
            ""baseUrl"": ""https://<your-domain>.lusid.com"",
            ""username"": ""<your-username>"",
            ""password"": ""<your-password>"",
            ""clientId"": ""<your-client-id>"",
            ""clientSecret"": ""<your-client-secret>""
        }
    }");

// uncomment the below to use configuration overrides
// var opts = new ConfigurationOptions();
// opts.TimeoutMs = 30_000;

// uncomment the below to use an api factory with overrides
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<MetricsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MetricsApi>();
```

---

<a id="getmetrics"></a>
## GetMetrics

> MetricsResponse GetMetrics(List<string>? include = null)

[EARLY ACCESS] GetMetrics: Get the aggregated platform metrics for the caller's domain.

 Returns request volumes, error rates and duration distributions for the domain's services, plus its identity             population and activity counts. The domain is taken from the authenticated request, never from a parameter.  <b>This endpoint is slow by design.</b> It runs several analytical queries in parallel and commonly takes             upwards of thirty seconds when the underlying data is cold. The server abandons a data set that has not             completed within its configured budget and reports it in `failed`, so a call returns rather than hanging             indefinitely; allow comfortably more than that budget on the client, and do not call this on a             user-interactive code path without showing progress.  Partial success is normal and is still reported as a `200`. A data set that could not be retrieved is             null in the response and named in `failed` with a reason; a data set excluded via             include is null and named in `notIncluded`. Render a null data set as unavailable             rather than as an absence of activity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MetricsApi>();
var include = new List<string>?(); // List<string>? (optional)
MetricsResponse result = apiInstance.GetMetrics(include);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **include** | [List&lt;string&gt;?](../Model/string.md) | query | optional | The data sets to return, by name. Omit to return all of them. Repeat the parameter to request several, for example &#x60;?include&#x3D;RequestsPerMinute&amp;include&#x3D;IdentityMetrics&#x60;. Matched case-insensitively against the data set names, which are the &#x60;name&#x60; values on the response&#39;s data sets; duplicates are ignored. |

### Return type

[MetricsResponse](../Model/MetricsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMetricsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MetricsResponse> response = apiInstance.GetMetricsWithHttpInfo(include);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

