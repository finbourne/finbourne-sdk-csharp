# Finbourne.Sdk.Insights.Api.VendorLogsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetVendorLog**](#getvendorlog) | **GET** `/insights/api/vendor/{id}` | [EXPERIMENTAL] GetVendorLog: Get the log for a specific vendor request. |
| [**GetVendorRequest**](#getvendorrequest) | **GET** `/insights/api/vendor/{id}/request` | [EXPERIMENTAL] GetVendorRequest: Get the request body for a vendor request. |
| [**GetVendorResponse**](#getvendorresponse) | **GET** `/insights/api/vendor/{id}/response` | [EXPERIMENTAL] GetVendorResponse: Get the response from a vendor request. |
| [**ListVendorLogs**](#listvendorlogs) | **GET** `/insights/api/vendor` | [EXPERIMENTAL] ListVendorLogs: List the logs for vendor requests. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<VendorLogsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorLogsApi>();
```

---

<a id="getvendorlog"></a>
## GetVendorLog

> VendorLog GetVendorLog(string id)

[EXPERIMENTAL] GetVendorLog: Get the log for a specific vendor request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorLogsApi>();
var id = "id_example";  // string
VendorLog result = apiInstance.GetVendorLog(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier of the request to obtain the log for. |

### Return type

[VendorLog](VendorLog.md)

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
<summary>Using the GetVendorLogWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VendorLog> response = apiInstance.GetVendorLogWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvendorrequest"></a>
## GetVendorRequest

> VendorRequest GetVendorRequest(string id)

[EXPERIMENTAL] GetVendorRequest: Get the request body for a vendor request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorLogsApi>();
var id = "id_example";  // string
VendorRequest result = apiInstance.GetVendorRequest(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier of the request to obtain the content for. |

### Return type

[VendorRequest](VendorRequest.md)

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
<summary>Using the GetVendorRequestWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VendorRequest> response = apiInstance.GetVendorRequestWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvendorresponse"></a>
## GetVendorResponse

> VendorResponse GetVendorResponse(string id)

[EXPERIMENTAL] GetVendorResponse: Get the response from a vendor request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorLogsApi>();
var id = "id_example";  // string
VendorResponse result = apiInstance.GetVendorResponse(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The identifier of the request to obtain the response for. |

### Return type

[VendorResponse](VendorResponse.md)

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
<summary>Using the GetVendorResponseWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VendorResponse> response = apiInstance.GetVendorResponseWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listvendorlogs"></a>
## ListVendorLogs

> ResourceListWithHistogramOfVendorLog ListVendorLogs(string? filter = null, string? sortBy = null, int? limit = null, string? page = null, string? histogramInterval = null)

[EXPERIMENTAL] ListVendorLogs: List the logs for vendor requests.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorLogsApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var histogramInterval = "histogramInterval_example";  // string? (optional)
ResourceListWithHistogramOfVendorLog result = apiInstance.ListVendorLogs(filter, sortBy, limit, page, histogramInterval);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about [filtering results from LUSID](https://support.lusid.com/filtering-results-from-lusid). |
| **sortBy** | **string?** | query | optional | Order the results by these fields. Use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. Multiple fields can be denoted by a comma e.g. -MyFieldName,AnotherFieldName,-AFurtherFieldName |
| **limit** | **int?** | query | optional | When paginating, only return this number of records. The minimum value is 0 and the maximum is 10000. |
| **page** | **string?** | query | optional | Encoded page string returned from a previous search result that will retrieve the next page of data. When this field is supplied, filter and sortby fields should not be supplied. |
| **histogramInterval** | **string?** | query | optional | Optional interval to use in a histogram of the returned values. If not provided, no histogram will be generated. |

### Return type

[ResourceListWithHistogramOfVendorLog](ResourceListWithHistogramOfVendorLog.md)

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
<summary>Using the ListVendorLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListWithHistogramOfVendorLog> response = apiInstance.ListVendorLogsWithHttpInfo(filter, sortBy, limit, page, histogramInterval);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

