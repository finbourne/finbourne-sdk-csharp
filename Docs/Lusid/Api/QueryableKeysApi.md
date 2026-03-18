# Finbourne.Sdk.Lusid.Api.QueryableKeysApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAllQueryableKeys**](#getallqueryablekeys) | **GET** `/api/api/queryablekeys` | [EARLY ACCESS] GetAllQueryableKeys: Query the set of supported \&quot;addresses\&quot; that can be queried from all endpoints. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Lusid.Api;
using Finbourne.Sdk.Lusid.Client;
using Finbourne.Sdk.Lusid.Extensions;
using Finbourne.Sdk.Services.Lusid.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<QueryableKeysApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QueryableKeysApi>();
```

---

<a id="getallqueryablekeys"></a>
## GetAllQueryableKeys

> ResourceListOfQueryableKey GetAllQueryableKeys(DateTimeOffset? asAt = null, string? filter = null)

[EARLY ACCESS] GetAllQueryableKeys: Query the set of supported \"addresses\" that can be queried from all endpoints.

When a request is made, the user needs to know what keys can be passed to it for queryable data. This endpoint provides all supported keys,

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QueryableKeysApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfQueryableKey result = apiInstance.GetAllQueryableKeys(asAt, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | For user defined DerivedValuation keys. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfQueryableKey](ResourceListOfQueryableKey.md)

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
<summary>Using the GetAllQueryableKeysWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfQueryableKey> response = apiInstance.GetAllQueryableKeysWithHttpInfo(asAt, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

