# Finbourne.Sdk.Luminesce.Api.ViewManagementApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteView**](#deleteview) | **DELETE** `/honeycomb/api/View/update` | [EXPERIMENTAL] DeleteView: Deletes a view by name |
| [**GetViewCreationSql**](#getviewcreationsql) | **PUT** `/honeycomb/api/View/sql` | [EXPERIMENTAL] GetViewCreationSql: Gets the original source Sql for a view (if available) |
| [**ListViews**](#listviews) | **GET** `/honeycomb/api/View/list` | [EXPERIMENTAL] ListViews: List views which are visible to the current user |
| [**UpsertView**](#upsertview) | **PUT** `/honeycomb/api/View/update` | [EXPERIMENTAL] UpsertView: Creates or updates a view from a full ViewDefinition. |

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

<a id="deleteview"></a>
## DeleteView

> string DeleteView(string? viewName = null)

[EXPERIMENTAL] DeleteView: Deletes a view by name

 Deletes a view.  This is primarily intended for use by an automated tool to synchronise views between domains.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ViewManagementApi>();
var viewName = "viewName_example";  // string? (optional)
string result = apiInstance.DeleteView(viewName);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **viewName** | **string?** | query | optional | View to delete |

### Return type

**string**

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
<summary>Using the DeleteViewWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.DeleteViewWithHttpInfo(viewName);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

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

> List&lt;ViewItem&gt; ListViews(bool? showAll = null, string? regExFilter = null, string? nameLikeFilter = null)

[EXPERIMENTAL] ListViews: List views which are visible to the current user

 Lists all the views which you have access to see. These come from directly from persisted files in the file system. Some limited filtering is available.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ViewManagementApi>();
var showAll = false;  // bool? (optional)
var regExFilter = "regExFilter_example";  // string? (optional)
var nameLikeFilter = "nameLikeFilter_example";  // string? (optional)
List<ViewItem> result = apiInstance.ListViews(showAll, regExFilter, nameLikeFilter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **showAll** | **bool?** | query | optional | Show additional views if permissions allow Default: `false` |
| **regExFilter** | **string?** | query | optional | Regular Expression filter to reduce the number of views returned, it is applied to the view *content* (this filter is applied withing the Filesystem itself.) |
| **nameLikeFilter** | **string?** | query | optional | SQL Like-style filter on the view name, to reduce the number of views returned (this filter is applied to the Filesystem-returned view list.) |

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
ApiResponse<List<ViewItem>> response = apiInstance.ListViewsWithHttpInfo(showAll, regExFilter, nameLikeFilter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertview"></a>
## UpsertView

> string UpsertView(bool? allowWarnings = null, bool? mayUpdateExisting = null, ViewItem? viewItem = null)

[EXPERIMENTAL] UpsertView: Creates or updates a view from a full ViewDefinition.

 Creates or updates a view from a full ViewDefinition.  Adds or creates a view from a view definition - without running the SQL of the view.  This is primarily intended for use by an automated tool to copy views between domains.  What this is *absolutely not* intended to do is to update views to tampered with definitions that were not originally created by `Sys.Admin.SetupView`, not even the smallest of changes are permitted as they may not work and will lead to additional support loads.  The flow for using fbn-config and these endpoints should generally be: - version control the `Sys.Admin.SetupView` query or the fbn-config resource that runs that query. - that can be automatically deployed to a development environment / domain. - an automated process then uses the `list` endpoint to get the full view definition (see above) from the dev-domain - then that definition can be given to a sit/uat/prod domain via this endpoint   - fbn-config could be responsible for this via a new resource type or simply a new, or any other script with PATs for both domains could be responsible for that)  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ViewManagementApi>();
var allowWarnings = false;  // bool? (optional)
var mayUpdateExisting = false;  // bool? (optional)
var viewItem = new ViewItem?(); // ViewItem? (optional)
string result = apiInstance.UpsertView(allowWarnings, mayUpdateExisting, viewItem);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **allowWarnings** | **bool?** | query | optional | May views with *warnings* be upserted?  Regardless of this views with *errors* may not be. Warnings includes things like: - not using macros properly so that filters or aggregations cannot be passed down - using things like &#x60;select *&#x60; that can lead to results changing over time Errors includes things like: - uses a provider or view that simply doesn&#39;t exists (so perhaps a view this depends on needs creating first?) - The SQL or Metadata of the view was manually edited, not setup correctly by &#x60;Sys.Admin.SetupView&#x60; Default: `false` |
| **mayUpdateExisting** | **bool?** | query | optional | May an existing view be overwritten?  Defaults to false to prevent accidental overwrites. Set to true when intentionally deploying an updated view definition to a domain. Default: `false` |
| **viewItem** | [ViewItem?](ViewItem?.md) | body | optional | View to create / change the definition of. |

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
<summary>Using the UpsertViewWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.UpsertViewWithHttpInfo(allowWarnings, mayUpdateExisting, viewItem);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

