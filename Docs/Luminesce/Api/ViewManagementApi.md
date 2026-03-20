# Finbourne.Sdk.Luminesce.Api.ViewManagementApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetViewCreationSql**](#getviewcreationsql) | **PUT** `/honeycomb/api/View/sql` | [EXPERIMENTAL] GetViewCreationSql: Gets the original source Sql for a view (if available) |
| [**ListViews**](#listviews) | **GET** `/honeycomb/api/View/list` | [EXPERIMENTAL] ListViews: List views which are visible to the current users |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ViewManagementApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ViewManagementApi>();
```

---

<a id="getviewcreationsql"></a>
## GetViewCreationSql

> string GetViewCreationSql(ViewItem? viewItem = null)

[EXPERIMENTAL] GetViewCreationSql: Gets the original source Sql for a view (if available)

 Gets the original source Sql for a view (if available, 404 if not found in the logs)  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ViewManagementApi>();
var viewItem = new ViewItem?(); // ViewItem? (optional)
string result = apiInstance.GetViewCreationSql(viewItem);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **viewItem** | [ViewItem?](ViewItem?.md) | body | optional | View to fetch the create SQL for. Only the LastUpdatedAt and LastUpdatedExecutionId properties are required. |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the GetViewCreationSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetViewCreationSqlWithHttpInfo(viewItem);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listviews"></a>
## ListViews

> List&lt;ViewItem&gt; ListViews(bool? showAll = null, string? regExFilter = null)

[EXPERIMENTAL] ListViews: List views which are visible to the current users

 Lists all the views which you have access, some limited filtering is available. These come from directly from persisted files in the file system.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ViewManagementApi>();
var showAll = false;  // bool? (optional)
var regExFilter = "regExFilter_example";  // string? (optional)
List<ViewItem> result = apiInstance.ListViews(showAll, regExFilter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **showAll** | **bool?** | query | optional | Show additional views if permissions allow Default: `false` |
| **regExFilter** | **string?** | query | optional | Regular Expression filter to apply to the view content |

### Return type

[List&lt;ViewItem&gt;](ViewItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the ListViewsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<ViewItem>> response = apiInstance.ListViewsWithHttpInfo(showAll, regExFilter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

