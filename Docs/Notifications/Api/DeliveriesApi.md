# Finbourne.Sdk.Notifications.Api.DeliveriesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListDeliveries**](#listdeliveries) | **GET** `/notifications/api/deliveries` | ListDeliveries: List Deliveries |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Notifications.Api;
using Finbourne.Sdk.Notifications.Client;
using Finbourne.Sdk.Notifications.Extensions;
using Finbourne.Sdk.Services.Notifications.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<DeliveriesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeliveriesApi>();
```

---

<a id="listdeliveries"></a>
## ListDeliveries

> ResourceListOfDelivery ListDeliveries(string? page = null, int? limit = null, string? filter = null)

ListDeliveries: List Deliveries

Currently only returns deliveries with failed attempts.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeliveriesApi>();
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfDelivery result = apiInstance.ListDeliveries(page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing delivery attempts. This value is returned from the previous call. When this field is supplied the filter field should not be supplied. |
| **limit** | **int?** | query | optional | The maximum number of delivery attempts to retrieve. Defaults to 200 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. For more information about filtering results, see https://support.lusid.com/knowledgebase/article/KA-01914. By default, we set this filter to only query for the last week&#39;s worth of Deliveries, however if a filter is explicitly set, this will be overriden. An example filter to override the attempt time date might be &#39;AttemptTime gt 2023-08-25&#39; for example |

### Return type

[ResourceListOfDelivery](ResourceListOfDelivery.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No deliveries exists with the provided filter(s) |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListDeliveriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfDelivery> response = apiInstance.ListDeliveriesWithHttpInfo(page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

