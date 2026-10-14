# Finbourne.Sdk.Luminesce.Api.MultiQueryExecutionApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelMultiQuery**](#cancelmultiquery) | **DELETE** `/honeycomb/api/MultiQueryBackground/{executionId}` | CancelMultiQuery: Cancel / Clear a previously started query-set |
| [**DownloadMultiQueryResults**](#downloadmultiqueryresults) | **GET** `/honeycomb/api/MultiQueryBackground/{executionId}/download` | [EXPERIMENTAL] DownloadMultiQueryResults: Downloads the results of a custom query-set as one file |
| [**GetProgressOfMultiQuery**](#getprogressofmultiquery) | **GET** `/honeycomb/api/MultiQueryBackground/{executionId}` | GetProgressOfMultiQuery: View progress of the entire query-set load |
| [**ListCustomQueries**](#listcustomqueries) | **GET** `/honeycomb/api/MultiQueryBackground` | [EXPERIMENTAL] ListCustomQueries: List the custom query-sets available to the calling user |
| [**SaveMultiQueryResultsToDrive**](#savemultiqueryresultstodrive) | **GET** `/honeycomb/api/MultiQueryBackground/{executionId}/drive` | [EXPERIMENTAL] SaveMultiQueryResultsToDrive: Saves the results of a custom query-set directly to Drive, as one file |
| [**StartCustomQueries**](#startcustomqueries) | **PUT** `/honeycomb/api/MultiQueryBackground/custom` | [EXPERIMENTAL] StartCustomQueries: Run a caller-supplied set of Sql queries in the background |
| [**StartQueries**](#startqueries) | **PUT** `/honeycomb/api/MultiQueryBackground` | StartQueries: Run a given set of Sql queries in the background |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<MultiQueryExecutionApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
```

---

<a id="cancelmultiquery"></a>
## CancelMultiQuery

> BackgroundQueryCancelResponse CancelMultiQuery(string executionId)

CancelMultiQuery: Cancel / Clear a previously started query-set

Cancel the query-set (if still running) / clear the data (if already returned) The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var executionId = "executionId_example";  // string
BackgroundQueryCancelResponse result = apiInstance.CancelMultiQuery(executionId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |

### Return type

[BackgroundQueryCancelResponse](../Model/BackgroundQueryCancelResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the CancelMultiQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundQueryCancelResponse> response = apiInstance.CancelMultiQueryWithHttpInfo(executionId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="downloadmultiqueryresults"></a>
## DownloadMultiQueryResults

> System.IO.Stream DownloadMultiQueryResults(string executionId, ExportType? format = null, string? fileName = null, string? dateTimeFormat = null, int? loadWaitMilliseconds = null)

[EXPERIMENTAL] DownloadMultiQueryResults: Downloads the results of a custom query-set as one file

Exports the results of all the queries of a custom query-set (other than those which are not external results) as one file. Queries that failed, or were skipped as a query they depend on failed, are left out - though if none succeeded there is nothing to export.  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : no query succeeded, or a placeholder or Drive parameter was incorrect in some way - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query-set doesn't exist, isn't a custom one, or the calling user did not run it. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var executionId = "executionId_example";  // string
var format = new ExportType?(); // ExportType? (optional)
var fileName = "fileName_example";  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
System.IO.Stream result = apiInstance.DownloadMultiQueryResults(executionId, format, fileName, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query-set |
| **format** | [ExportType?](../Model/ExportType?.md) | query | optional | Format to download in.  Several results are one worksheet each for Excel, one table each for Sqlite, and otherwise one file each within a zip. |
| **fileName** | **string?** | query | optional | Name of the file (without extension).  Defaults to &#x60;{executionId}&#x60;. May contain the placeholders &#x60;{executionId}&#x60;, &#x60;{date:format}&#x60; (when the queries started, UTC, e.g. &#x60;{date:yyyyMMdd}&#x60;) and &#x60;{param:name}&#x60; (the value of a scalar parameter). |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |
| **loadWaitMilliseconds** | **int?** | query | optional | Optional maximum additional wait period for post execution platform processing. Default: `0` |

### Return type

**System.IO.Stream**

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
<summary>Using the DownloadMultiQueryResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.DownloadMultiQueryResultsWithHttpInfo(executionId, format, fileName, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprogressofmultiquery"></a>
## GetProgressOfMultiQuery

> BackgroundMultiQueryProgressResponse GetProgressOfMultiQuery(string executionId)

GetProgressOfMultiQuery: View progress of the entire query-set load

View progress information (up until this point) for the entire query-set The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var executionId = "executionId_example";  // string
BackgroundMultiQueryProgressResponse result = apiInstance.GetProgressOfMultiQuery(executionId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |

### Return type

[BackgroundMultiQueryProgressResponse](../Model/BackgroundMultiQueryProgressResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetProgressOfMultiQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundMultiQueryProgressResponse> response = apiInstance.GetProgressOfMultiQueryWithHttpInfo(executionId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcustomqueries"></a>
## ListCustomQueries

> List&lt;CustomMultiQueryListItem&gt; ListCustomQueries(string? sqlLike = null)

[EXPERIMENTAL] ListCustomQueries: List the custom query-sets available to the calling user

Lists the custom query-sets (started by the calling user via `custom`) that have finished with at least one result which may be fetched,  and which have not yet passed their `keepForSeconds` time, most recent first.  Each lists its queries that are external results, and which of those have results. Those that errored are included, as some of their queries may still have succeeded.  The following error codes are to be anticipated most with standard Problem Detail reports: - 401 Unauthorized

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var sqlLike = "sqlLike_example";  // string? (optional)
List<CustomMultiQueryListItem> result = apiInstance.ListCustomQueries(sqlLike);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sqlLike** | **string?** | query | optional | An optional SQL-LIKE style filter on the LuminesceSql of the queries (manually include wildcards if desired), a query-set matching should any of its queries. |

### Return type

[List&lt;CustomMultiQueryListItem&gt;](../Model/CustomMultiQueryListItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the ListCustomQueriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<CustomMultiQueryListItem>> response = apiInstance.ListCustomQueriesWithHttpInfo(sqlLike);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="savemultiqueryresultstodrive"></a>
## SaveMultiQueryResultsToDrive

> string SaveMultiQueryResultsToDrive(string executionId, string driveLocationAndFileName, bool? mayOverwrite = null, ExportType? format = null, string? driveTemplateLocation = null, string? dateTimeFormat = null, int? loadWaitMilliseconds = null)

[EXPERIMENTAL] SaveMultiQueryResultsToDrive: Saves the results of a custom query-set directly to Drive, as one file

Exports the results of all the queries of a custom query-set (other than those which are not external results) as one file. Queries that failed, or were skipped as a query they depend on failed, are left out - though if none succeeded there is nothing to export.  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : no query succeeded, or a placeholder or Drive parameter was incorrect in some way - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query-set doesn't exist, isn't a custom one, or the calling user did not run it. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var executionId = "executionId_example";  // string
var driveLocationAndFileName = "driveLocationAndFileName_example";  // string
var mayOverwrite = false;  // bool? (optional)
var format = new ExportType?(); // ExportType? (optional)
var driveTemplateLocation = "driveTemplateLocation_example";  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.SaveMultiQueryResultsToDrive(executionId, driveLocationAndFileName, mayOverwrite, format, driveTemplateLocation, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query-set |
| **driveLocationAndFileName** | **string** | query | **required** | Location and file name within drive where this should be saved to. Missing paths will be created, and extension (if given) will be ignored and inferred from the chosen format (zip where several results are zipped). May contain the placeholders &#x60;{executionId}&#x60;, &#x60;{date:format}&#x60; (when the queries started, UTC, e.g. &#x60;{date:yyyyMMdd}&#x60;) and &#x60;{param:name}&#x60; (the value of a scalar parameter). |
| **mayOverwrite** | **bool?** | query | optional | If there is an existing file at the requested location with the same name should this be overridden, or an error returned? Default: `false` |
| **format** | [ExportType?](../Model/ExportType?.md) | query | optional | Format to save in.  Several results are one worksheet each for Excel, one table each for Sqlite, and otherwise one file each within a zip. |
| **driveTemplateLocation** | **string?** | query | optional | Drive path and full file name including extension to be used for the export. Only some export types support templates, such as Excel and Pdf, and this will need to match the format type, if given. |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |
| **loadWaitMilliseconds** | **int?** | query | optional | Optional maximum additional wait period for post execution platform processing. Default: `0` |

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
<summary>Using the SaveMultiQueryResultsToDriveWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.SaveMultiQueryResultsToDriveWithHttpInfo(executionId, driveLocationAndFileName, mayOverwrite, format, driveTemplateLocation, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="startcustomqueries"></a>
## StartCustomQueries

> BackgroundMultiQueryResponse StartCustomQueries(CustomMultiQueryRequest customMultiQueryRequest)

[EXPERIMENTAL] StartCustomQueries: Run a caller-supplied set of Sql queries in the background

 Starts a caller-supplied set of named queries in the background, getting back an immediate response with how to - fetch the data of each (external) query in various formats, view progress information and cancel / clear them, as for any multi-query - download, or save to Drive, the results of all the (external) queries that succeeded as one file  The queries are started in the order given, at most `maxInParallel` at a time (1 by default, null for as many as possible). A query may use the results of an earlier one as a table variable of its name, e.g. `select * from @Holdings`, and is then only started once that has succeeded (and is skipped if it does not).  The scalar parameters are given to every query.  The multi-query as a whole is reported as failed if any of its queries fails or is skipped.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - the request was invalid, a Saved Query could not be loaded, or there was something wrong with the syntax of a query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var customMultiQueryRequest = new CustomMultiQueryRequest(); // CustomMultiQueryRequest
BackgroundMultiQueryResponse result = apiInstance.StartCustomQueries(customMultiQueryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **customMultiQueryRequest** | [CustomMultiQueryRequest](../Model/CustomMultiQueryRequest.md) | body | **required** | The queries to run (as LuminesceSql or Saved Query references), the scalar parameters for them all, etc. |

### Return type

[BackgroundMultiQueryResponse](../Model/BackgroundMultiQueryResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Accepted |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the StartCustomQueriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundMultiQueryResponse> response = apiInstance.StartCustomQueriesWithHttpInfo(customMultiQueryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="startqueries"></a>
## StartQueries

> BackgroundMultiQueryResponse StartQueries(MultiQueryDefinitionType type, string body, DateTimeOffset? asAt = null, DateTimeOffset? effectiveAt = null, int? limit1 = null, int? limit2 = null, string? input1 = null, string? input2 = null, string? input3 = null, int? timeoutSeconds = null, int? keepForSeconds = null)

StartQueries: Run a given set of Sql queries in the background

 Allow for starting a potentially long running query and getting back an immediate response with how to  - fetch the data in various formats (if available, or if not simply being informed it is not yet ready), on a per result basis - view progress information (up until this point), for all results in one go - cancel the queries (if still running) / clear the data (if already returned)  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - there was something wrong with your query syntax (the issue was detected at parse-time) - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MultiQueryExecutionApi>();
var type = Instrument;  // MultiQueryDefinitionType
var body = Apple;  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit1 = 56;  // int? (optional)
var limit2 = 56;  // int? (optional)
var input1 = "input1_example";  // string? (optional)
var input2 = "input2_example";  // string? (optional)
var input3 = "input3_example";  // string? (optional)
var timeoutSeconds = 1200;  // int? (optional)
var keepForSeconds = 7200;  // int? (optional)
BackgroundMultiQueryResponse result = apiInstance.StartQueries(type, body, asAt, effectiveAt, limit1, limit2, input1, input2, input3, timeoutSeconds, keepForSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **MultiQueryDefinitionType** | query | **required** | An enum value defining the set of statements being executed |
| **body** | **string** | body | **required** | A \&quot;search\&quot; value (e.g. &#39;Apple&#39; on an instrument search, a &#x60;Finbourne.Filtering&#x60; expression of Insights, etc.) In the cases where \&quot;Nothing\&quot; is valid for a &#x60;Finbourne.Filtering&#x60; expression, pass &#x60;True&#x60;. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt time used by any bitemporal provider in the queries. |
| **effectiveAt** | **DateTimeOffset?** | query | optional | The EffectiveAt time used by any bitemporal provider in the queries. |
| **limit1** | **int?** | query | optional | A limit that is applied to first-level queries (e.g. Instruments themselves) |
| **limit2** | **int?** | query | optional | A limit that is applied to second-level queries (e.g. Holdings based on the set of Instruments found) |
| **input1** | **string?** | query | optional | A value available to queries, these vary by &#39;type&#39; and are only used by some types at all. e.g. a start-date of some sort |
| **input2** | **string?** | query | optional | A second value available to queries, these vary by &#39;type&#39; and are only used by some types at all. |
| **input3** | **string?** | query | optional | A third value available to queries, these vary by &#39;type&#39; and are only used by some types at all. |
| **timeoutSeconds** | **int?** | query | optional | Maximum time the query may run for, in seconds: &lt;0 → ∞, 0 → 1200s (20m) Default: `0` |
| **keepForSeconds** | **int?** | query | optional | Maximum time the result may be kept for, in seconds: &lt;0 → 1200 (20m), 0 → 28800 (8h), max &#x3D; 2,678,400 (31d) Default: `0` |

### Return type

[BackgroundMultiQueryResponse](../Model/BackgroundMultiQueryResponse.md)

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Accepted |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the StartQueriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundMultiQueryResponse> response = apiInstance.StartQueriesWithHttpInfo(type, body, asAt, effectiveAt, limit1, limit2, input1, input2, input3, timeoutSeconds, keepForSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

