# Finbourne.Sdk.Luminesce.Api.SqlBackgroundExecutionApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CancelQuery**](#cancelquery) | **DELETE** `/honeycomb/api/SqlBackground/{executionId}` | CancelQuery: Cancel / Clear data from a previously run query |
| [**FetchQueryResultCsv**](#fetchqueryresultcsv) | **GET** `/honeycomb/api/SqlBackground/{executionId}/csv` | FetchQueryResultCsv: Fetch the result of a query as CSV |
| [**FetchQueryResultExcel**](#fetchqueryresultexcel) | **GET** `/honeycomb/api/SqlBackground/{executionId}/excel` | FetchQueryResultExcel: Fetch the result of a query as an Excel file |
| [**FetchQueryResultHistogram**](#fetchqueryresulthistogram) | **GET** `/honeycomb/api/SqlBackground/{executionId}/histogram` | FetchQueryResultHistogram: Construct a histogram of the result of a query |
| [**FetchQueryResultJson**](#fetchqueryresultjson) | **GET** `/honeycomb/api/SqlBackground/{executionId}/json` | FetchQueryResultJson: Fetch the result of a query as a JSON string |
| [**FetchQueryResultJsonProper**](#fetchqueryresultjsonproper) | **GET** `/honeycomb/api/SqlBackground/{executionId}/jsonProper` | FetchQueryResultJsonProper: Fetch the result of a query as JSON |
| [**FetchQueryResultJsonProperWithLineage**](#fetchqueryresultjsonproperwithlineage) | **GET** `/honeycomb/api/SqlBackground/{executionId}/jsonProperWithLineage` | FetchQueryResultJsonProperWithLineage: Fetch the result of a query as JSON, but including a Lineage Node (if available) |
| [**FetchQueryResultParquet**](#fetchqueryresultparquet) | **GET** `/honeycomb/api/SqlBackground/{executionId}/parquet` | FetchQueryResultParquet: Fetch the result of a query as Parquet |
| [**FetchQueryResultPipe**](#fetchqueryresultpipe) | **GET** `/honeycomb/api/SqlBackground/{executionId}/pipe` | FetchQueryResultPipe: Fetch the result of a query as pipe-delimited |
| [**FetchQueryResultSqlite**](#fetchqueryresultsqlite) | **GET** `/honeycomb/api/SqlBackground/{executionId}/sqlite` | FetchQueryResultSqlite: Fetch the result of a query as SqLite |
| [**FetchQueryResultXml**](#fetchqueryresultxml) | **GET** `/honeycomb/api/SqlBackground/{executionId}/xml` | FetchQueryResultXml: Fetch the result of a query as XML |
| [**GetHistoricalFeedback**](#gethistoricalfeedback) | **GET** `/honeycomb/api/SqlBackground/{executionId}/historicalFeedback` | GetHistoricalFeedback: View historical query progress (for older queries) |
| [**GetProgressOf**](#getprogressof) | **GET** `/honeycomb/api/SqlBackground/{executionId}` | GetProgressOf: View query progress up to this point. |
| [**StartQuery**](#startquery) | **PUT** `/honeycomb/api/SqlBackground` | StartQuery: Start to Execute Sql in the background |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SqlBackgroundExecutionApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
```

---

<a id="cancelquery"></a>
## CancelQuery

> BackgroundQueryCancelResponse CancelQuery(string executionId)

CancelQuery: Cancel / Clear data from a previously run query

Cancel the query (if still running) / clear the data (if already returned) The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running or the calling user did not run the query. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
BackgroundQueryCancelResponse result = apiInstance.CancelQuery(executionId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |

### Return type

[BackgroundQueryCancelResponse](BackgroundQueryCancelResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the CancelQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundQueryCancelResponse> response = apiInstance.CancelQueryWithHttpInfo(executionId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultcsv"></a>
## FetchQueryResultCsv

> string FetchQueryResultCsv(string executionId, bool? download = null, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? limit = null, int? page = null, string? delimiter = null, string? escape = null, string? dateTimeFormat = null, int? loadWaitMilliseconds = null)

FetchQueryResultCsv: Fetch the result of a query as CSV

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var download = false;  // bool? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var limit = 0;  // int? (optional)
var page = 0;  // int? (optional)
var delimiter = "delimiter_example";  // string? (optional)
var escape = "escape_example";  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.FetchQueryResultCsv(executionId, download, sortBy, filter, select, groupBy, limit, page, delimiter, escape, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
| **limit** | **int?** | query | optional | When paginating, only return this number of records, page should also be specified. Default: `0` |
| **page** | **int?** | query | optional | 0-N based on chunk sized determined by the limit, ignored if limit &lt; 1. Default: `0` |
| **delimiter** | **string?** | query | optional | Delimiter string to override the default |
| **escape** | **string?** | query | optional | Escape character to override the default |
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
<summary>Using the FetchQueryResultCsvWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultCsvWithHttpInfo(executionId, download, sortBy, filter, select, groupBy, limit, page, delimiter, escape, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultexcel"></a>
## FetchQueryResultExcel

> System.IO.Stream FetchQueryResultExcel(string executionId, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, string? dateTimeFormat = null, int? loadWaitMilliseconds = null)

FetchQueryResultExcel: Fetch the result of a query as an Excel file

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
System.IO.Stream result = apiInstance.FetchQueryResultExcel(executionId, sortBy, filter, select, groupBy, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
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
<summary>Using the FetchQueryResultExcelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.FetchQueryResultExcelWithHttpInfo(executionId, sortBy, filter, select, groupBy, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresulthistogram"></a>
## FetchQueryResultHistogram

> string FetchQueryResultHistogram(string executionId, string timestampFieldName, DateTimeOffset? startAt = null, DateTimeOffset? endAt = null, string? bucketSize = null, string? filter = null, bool? jsonProper = null)

FetchQueryResultHistogram: Construct a histogram of the result of a query

Fetch the histogram in Json format (if available, or if not simply being informed it is not yet ready) The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var timestampFieldName = "timestampFieldName_example";  // string
var startAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var endAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var bucketSize = "bucketSize_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var jsonProper = false;  // bool? (optional)
string result = apiInstance.FetchQueryResultHistogram(executionId, timestampFieldName, startAt, endAt, bucketSize, filter, jsonProper);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **timestampFieldName** | **string** | query | **required** | Name of the timestamp field used in building the histogram |
| **startAt** | **DateTimeOffset?** | query | optional | Start point (of the timestampFieldName field) for the histogram |
| **endAt** | **DateTimeOffset?** | query | optional | End point (of the timestampFieldName field) for the histogram |
| **bucketSize** | **string?** | query | optional | Optional histogram bucket width.  If not provided a set number of buckets between start/end range will be generated. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **jsonProper** | **bool?** | query | optional | Should this be text/json (not json-encoded-as-a-string) Default: `false` |

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
<summary>Using the FetchQueryResultHistogramWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultHistogramWithHttpInfo(executionId, timestampFieldName, startAt, endAt, bucketSize, filter, jsonProper);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultjson"></a>
## FetchQueryResultJson

> string FetchQueryResultJson(string executionId, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? limit = null, int? page = null, int? loadWaitMilliseconds = null)

FetchQueryResultJson: Fetch the result of a query as a JSON string

 *Please move to '/jsonProper' instead.  This may be marked as Deprecated in the future.*  Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var limit = 0;  // int? (optional)
var page = 0;  // int? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.FetchQueryResultJson(executionId, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
| **limit** | **int?** | query | optional | When paginating, only return this number of records, page should also be specified. Default: `0` |
| **page** | **int?** | query | optional | 0-N based on chunk sized determined by the limit, ignored if limit &lt; 1. Default: `0` |
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
<summary>Using the FetchQueryResultJsonWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultJsonWithHttpInfo(executionId, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultjsonproper"></a>
## FetchQueryResultJsonProper

> string FetchQueryResultJsonProper(string executionId, bool? download = null, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? limit = null, int? page = null, int? loadWaitMilliseconds = null)

FetchQueryResultJsonProper: Fetch the result of a query as JSON

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var download = false;  // bool? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var limit = 0;  // int? (optional)
var page = 0;  // int? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.FetchQueryResultJsonProper(executionId, download, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
| **limit** | **int?** | query | optional | When paginating, only return this number of records, page should also be specified. Default: `0` |
| **page** | **int?** | query | optional | 0-N based on chunk sized determined by the limit, ignored if limit &lt; 1. Default: `0` |
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
<summary>Using the FetchQueryResultJsonProperWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultJsonProperWithHttpInfo(executionId, download, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultjsonproperwithlineage"></a>
## FetchQueryResultJsonProperWithLineage

> string FetchQueryResultJsonProperWithLineage(string executionId, bool? download = null, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? limit = null, int? page = null, int? loadWaitMilliseconds = null)

FetchQueryResultJsonProperWithLineage: Fetch the result of a query as JSON, but including a Lineage Node (if available)

Fetch the data in proper Json format (if available, or if not simply being informed it is not yet ready) But embeds the data under a `Data` node and Lineage (if requested when starting the execution) under a `Lineage` node. Lineage is just for the 'raw query' it ignores all of these parameters: sortBy, filter, select, groupBy and limit.  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var download = false;  // bool? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var limit = 0;  // int? (optional)
var page = 0;  // int? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.FetchQueryResultJsonProperWithLineage(executionId, download, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
| **limit** | **int?** | query | optional | When paginating, only return this number of records, page should also be specified. Default: `0` |
| **page** | **int?** | query | optional | 0-N based on chunk sized determined by the limit, ignored if limit &lt; 1. Default: `0` |
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
<summary>Using the FetchQueryResultJsonProperWithLineageWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultJsonProperWithLineageWithHttpInfo(executionId, download, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultparquet"></a>
## FetchQueryResultParquet

> System.IO.Stream FetchQueryResultParquet(string executionId, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? loadWaitMilliseconds = null)

FetchQueryResultParquet: Fetch the result of a query as Parquet

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
System.IO.Stream result = apiInstance.FetchQueryResultParquet(executionId, sortBy, filter, select, groupBy, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
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
<summary>Using the FetchQueryResultParquetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.FetchQueryResultParquetWithHttpInfo(executionId, sortBy, filter, select, groupBy, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultpipe"></a>
## FetchQueryResultPipe

> string FetchQueryResultPipe(string executionId, bool? download = null, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? limit = null, int? page = null, string? dateTimeFormat = null, int? loadWaitMilliseconds = null)

FetchQueryResultPipe: Fetch the result of a query as pipe-delimited

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var download = false;  // bool? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var limit = 0;  // int? (optional)
var page = 0;  // int? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.FetchQueryResultPipe(executionId, download, sortBy, filter, select, groupBy, limit, page, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
| **limit** | **int?** | query | optional | When paginating, only return this number of records, page should also be specified. Default: `0` |
| **page** | **int?** | query | optional | 0-N based on chunk sized determined by the limit, ignored if limit &lt; 1. Default: `0` |
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
<summary>Using the FetchQueryResultPipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultPipeWithHttpInfo(executionId, download, sortBy, filter, select, groupBy, limit, page, dateTimeFormat, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultsqlite"></a>
## FetchQueryResultSqlite

> System.IO.Stream FetchQueryResultSqlite(string executionId, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? loadWaitMilliseconds = null)

FetchQueryResultSqlite: Fetch the result of a query as SqLite

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
System.IO.Stream result = apiInstance.FetchQueryResultSqlite(executionId, sortBy, filter, select, groupBy, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
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
<summary>Using the FetchQueryResultSqliteWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.FetchQueryResultSqliteWithHttpInfo(executionId, sortBy, filter, select, groupBy, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="fetchqueryresultxml"></a>
## FetchQueryResultXml

> string FetchQueryResultXml(string executionId, bool? download = null, string? sortBy = null, string? filter = null, string? select = null, string? groupBy = null, int? limit = null, int? page = null, int? loadWaitMilliseconds = null)

FetchQueryResultXml: Fetch the result of a query as XML

Fetch the data in the format of the method's name (if available, or if not simply being informed it is not yet ready).  The following error codes are to be anticipated most with standard Problem Detail reports: - 400 BadRequest : Something failed with the execution of your query - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't (yet) exist or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var download = false;  // bool? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var select = "select_example";  // string? (optional)
var groupBy = "groupBy_example";  // string? (optional)
var limit = 0;  // int? (optional)
var page = 0;  // int? (optional)
var loadWaitMilliseconds = 0;  // int? (optional)
string result = apiInstance.FetchQueryResultXml(executionId, download, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **sortBy** | **string?** | query | optional | Order the results by these fields.             Use the &#x60;-&#x60; sign to denote descending order, e.g. &#x60;-MyFieldName&#x60;.  Numeric indexes may be used also, e.g. &#x60;2,-3&#x60;.             Multiple fields can be denoted by a comma e.g. &#x60;-MyFieldName,AnotherFieldName,-AFurtherFieldName&#x60;.             Default is null, the sort order specified in the query itself. |
| **filter** | **string?** | query | optional | An ODATA filter per Finbourne.Filtering syntax. |
| **select** | **string?** | query | optional | Default is null (meaning return all columns in the original query itself). The values are in terms of the result column name from the original data set and are comma delimited. The power of this comes in that you may aggregate the data if you wish (that is the main reason for allowing this, in fact). e.g.: - &#x60;MyField&#x60; - &#x60;Max(x) FILTER (WHERE y &gt; 12) as ABC&#x60; (max of a field, if another field lets it qualify, with a nice column name) - &#x60;count(*)&#x60; (count the rows for the given group, that would produce a rather ugly column name, but  it works) - &#x60;count(distinct x) as numOfXs&#x60; If there was an illegal character in a field you are selecting from, you are responsible for bracketing it with [ ].  e.g. - &#x60;some_field, count(*) as a, max(x) as b, min([column with space in name]) as nice_name&#x60;   where you would likely want to pass &#x60;1&#x60; as the &#x60;groupBy&#x60; also. |
| **groupBy** | **string?** | query | optional | Groups by the specified fields.             A comma delimited list of: 1 based numeric indexes (cleaner), or repeats of the select expressions (a bit verbose and must match exactly).             e.g. &#x60;2,3&#x60;, &#x60;myColumn&#x60;.             Default is null (meaning no grouping will be performed on the selected columns).             This applies only over the result set being requested here, meaning indexes into the \&quot;select\&quot; parameter fields.             Only specify this if you are selecting aggregations in the \&quot;select\&quot; parameter. |
| **limit** | **int?** | query | optional | When paginating, only return this number of records, page should also be specified. Default: `0` |
| **page** | **int?** | query | optional | 0-N based on chunk sized determined by the limit, ignored if limit &lt; 1. Default: `0` |
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
<summary>Using the FetchQueryResultXmlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.FetchQueryResultXmlWithHttpInfo(executionId, download, sortBy, filter, select, groupBy, limit, page, loadWaitMilliseconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gethistoricalfeedback"></a>
## GetHistoricalFeedback

> BackgroundQueryProgressResponse GetHistoricalFeedback(string executionId, int? nextMessageWaitSeconds = null, DateTimeOffset? startedAt = null)

GetHistoricalFeedback: View historical query progress (for older queries)

View full progress information, including historical feedback for queries which have passed their `keepForSeconds` time, so long as they were executed in the last 31 days.  This method is slow by its nature of looking at the stream of historical feedback data.   On the other hand under some circumstances this can fail to wait long enough and return 404s where really there is data. To help with this `nextMessageWaitSeconds` may be specified to non-default values larger then the 2-7s used internally.  Unlike most methods here this may be called by a user that did not run the original query, if your entitlements allow this, as this is pure telemetry information.  The following error codes are to be anticipated most with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var nextMessageWaitSeconds = 56;  // int? (optional)
var startedAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
BackgroundQueryProgressResponse result = apiInstance.GetHistoricalFeedback(executionId, nextMessageWaitSeconds, startedAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **nextMessageWaitSeconds** | **int?** | query | optional | An override to the internal default for the number of seconds to wait for stream-messages. Meant to help understand 404s that would seem on the surface to be incorrect. |
| **startedAt** | **DateTimeOffset?** | query | optional | Performance will be hugely improved if thet time (in UTC) when the query was started is provided. It will also significantly decrease the chances of a 404 where there really is data, as it can help to disambiguate between &#39;there is no query with this executionId&#39; and &#39;there is such a query but we couldn&#39;t wait long enough for it to come back from the Feedback Stream&#39;. |

### Return type

[BackgroundQueryProgressResponse](BackgroundQueryProgressResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetHistoricalFeedbackWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundQueryProgressResponse> response = apiInstance.GetHistoricalFeedbackWithHttpInfo(executionId, nextMessageWaitSeconds, startedAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprogressof"></a>
## GetProgressOf

> BackgroundQueryProgressResponse GetProgressOf(string executionId, bool? buildFromLogs = null, bool? includeAllFeedback = null)

GetProgressOf: View query progress up to this point.

View progress information (up until this point and starting from the last point requested) The following error codes are to be anticipated most with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden - 404 Not Found : The requested query result doesn't exist and is not running or the calling user did not run the query. - 429 Too Many Requests : Please try your request again soon   1. The query has been executed successfully in the past yet the server-instance receiving this request (e.g. from a load balancer) doesn't yet have this data available.   1. By virtue of the request you have just placed this will have started to load from the persisted cache and will soon be available.   1. It is also the case that the original server-instance to process the original query is likely to already be able to service this request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var executionId = "executionId_example";  // string
var buildFromLogs = false;  // bool? (optional)
var includeAllFeedback = false;  // bool? (optional)
BackgroundQueryProgressResponse result = apiInstance.GetProgressOf(executionId, buildFromLogs, includeAllFeedback);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **executionId** | **string** | path | **required** | ExecutionId returned when starting the query |
| **buildFromLogs** | **bool?** | query | optional | Should the response state be build from query logs if missing from the shared-db-state?  Deprecated. Regardless of the value here it is now the case that:  False [and now even True] will mean &#x60;404 Not Found&#x60; in cases where it was a real query but has passed its &#x60;keepForSeconds&#x60; since the query completed (as well as &#39;this was not a query at all&#39; of course) Default: `false` |
| **includeAllFeedback** | **bool?** | query | optional | Should all the feedback be returned?  As opposed to just the new feedback. Default: `false` |

### Return type

[BackgroundQueryProgressResponse](BackgroundQueryProgressResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetProgressOfWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundQueryProgressResponse> response = apiInstance.GetProgressOfWithHttpInfo(executionId, buildFromLogs, includeAllFeedback);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="startquery"></a>
## StartQuery

> BackgroundQueryResponse StartQuery(string body, string? executionId = null, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeoutSeconds = null, int? keepForSeconds = null, SqlExecutionFlags? executionFlags = null)

StartQuery: Start to Execute Sql in the background

 Allow for starting a potentially long running query and getting back an immediate response with how to  - fetch the data in various formats (if available, or if not simply being informed it is not yet ready) - view progress information (up until this point) - cancel the query (if still running) / clear the data (if already returned)  This can still error on things like an outright syntax error, but more runtime errors (e.g. from providers) will not cause this to error (that will happen when attempting to fetch data)  Here is an example that intentionally takes one minute to run:  ```sql select Str, Takes500Ms from Testing1K where UseLinq = true and [Int] <= 120 ```  This is the only place in the Luminesce WebAPI where the following is supported. This will allow for the same user running a character-identical query not kick off a new query but simply be returned a reference  to the already running one for up to `N` seconds (where `N` should be `<=` `keepForSeconds`).  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - there was something wrong with your query syntax (the issue was detected at parse-time) - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlBackgroundExecutionApi>();
var body = select Str, Takes500Ms from Testing1K where UseLinq = true and [Int] <= 120;  // string
var executionId = "executionId_example";  // string? (optional)
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Intentionally slow test query;  // string? (optional)
var timeoutSeconds = 1200;  // int? (optional)
var keepForSeconds = 7200;  // int? (optional)
var executionFlags = new SqlExecutionFlags?(); // SqlExecutionFlags? (optional)
BackgroundQueryResponse result = apiInstance.StartQuery(body, executionId, scalarParameters, queryName, timeoutSeconds, keepForSeconds, executionFlags);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | The LuminesceSql query to kick off. |
| **executionId** | **string?** | query | optional | An explicit ExecutionId to use.  This must be blank OR assigned to a valid GUID-as-a-string. It might be ignored / replaced, for example if using the query cache and a cached query is found. |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | A name for this query.  This goes into logs and is available in &#x60;Sys.Logs.HcQueryStart&#x60;. |
| **timeoutSeconds** | **int?** | query | optional | Maximum time the query may run for, in seconds: &lt;0 → ∞, 0 → 7200 (2h) Default: `0` |
| **keepForSeconds** | **int?** | query | optional | Maximum time the result may be kept for, in seconds: &lt;0 → 1200 (20m), 0 → 28800 (8h), max &#x3D; 2,678,400 (31d) Default: `0` |
| **executionFlags** | [SqlExecutionFlags?](SqlExecutionFlags?.md) | query | optional | Optional request flags for the execution.  Currently limited by may grow in time: - ProvideLineage : Should Lineage be requested when running the query?  This must be set in order to later retrieve Lineage. |

### Return type

[BackgroundQueryResponse](BackgroundQueryResponse.md)

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
<summary>Using the StartQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BackgroundQueryResponse> response = apiInstance.StartQueryWithHttpInfo(body, executionId, scalarParameters, queryName, timeoutSeconds, keepForSeconds, executionFlags);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

