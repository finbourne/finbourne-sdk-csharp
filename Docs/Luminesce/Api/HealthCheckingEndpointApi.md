# Finbourne.Sdk.Luminesce.Api.HealthCheckingEndpointApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**FakeNodeReclaim**](#fakenodereclaim) | **GET** `/honeycomb/fakeNodeReclaim` | [INTERNAL] FakeNodeReclaim: Helps testing of AWS node reclaim behaviour |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Luminesce.Api;
using Finbourne.Sdk.Luminesce.Client;
using Finbourne.Sdk.Luminesce.Extensions;
using Finbourne.Sdk.Services.Luminesce.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<HealthCheckingEndpointApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<HealthCheckingEndpointApi>();
```

---

<a id="fakenodereclaim"></a>
## FakeNodeReclaim

> Object FakeNodeReclaim(int? secondsUntilReclaim = null)

[INTERNAL] FakeNodeReclaim: Helps testing of AWS node reclaim behaviour

 An internal Method used to mark the next SIGTERM as though an Aws Node reclaim were about to take place. Simulates having received an AWS node reclaim warning, or similar.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<HealthCheckingEndpointApi>();
var secondsUntilReclaim = 119;  // int? (optional)
Object result = apiInstance.FakeNodeReclaim(secondsUntilReclaim);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **secondsUntilReclaim** | **int?** | query | optional | the number of seconds from which to assume node termination Default: `119` |

### Return type

**Object**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the FakeNodeReclaimWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Object> response = apiInstance.FakeNodeReclaimWithHttpInfo(secondsUntilReclaim);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

