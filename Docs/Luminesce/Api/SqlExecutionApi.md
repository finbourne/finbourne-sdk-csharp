# Finbourne.Sdk.Luminesce.Api.SqlExecutionApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetByQueryCsv**](#getbyquerycsv) | **GET** `/honeycomb/api/Sql/csv/{query}` | GetByQueryCsv: Execute Sql from the url returning CSV |
| [**GetByQueryExcel**](#getbyqueryexcel) | **GET** `/honeycomb/api/Sql/excel/{query}` | GetByQueryExcel: Execute Sql from the url returning an Excel file |
| [**GetByQueryJson**](#getbyqueryjson) | **GET** `/honeycomb/api/Sql/json/{query}` | GetByQueryJson: Execute Sql from the url returning JSON |
| [**GetByQueryParquet**](#getbyqueryparquet) | **GET** `/honeycomb/api/Sql/parquet/{query}` | GetByQueryParquet: Execute Sql from the url returning a Parquet file |
| [**GetByQueryPipe**](#getbyquerypipe) | **GET** `/honeycomb/api/Sql/pipe/{query}` | GetByQueryPipe: Execute Sql from the url returning pipe-delimited |
| [**GetByQuerySqlite**](#getbyquerysqlite) | **GET** `/honeycomb/api/Sql/sqlite/{query}` | GetByQuerySqlite: Execute Sql from the url returning SqLite DB |
| [**GetByQueryXml**](#getbyqueryxml) | **GET** `/honeycomb/api/Sql/xml/{query}` | GetByQueryXml: Execute Sql from the url returning XML |
| [**PutByQueryCsv**](#putbyquerycsv) | **PUT** `/honeycomb/api/Sql/csv` | PutByQueryCsv: Execute Sql from the body returning CSV |
| [**PutByQueryExcel**](#putbyqueryexcel) | **PUT** `/honeycomb/api/Sql/excel` | PutByQueryExcel: Execute Sql from the body making an Excel file |
| [**PutByQueryJson**](#putbyqueryjson) | **PUT** `/honeycomb/api/Sql/json` | PutByQueryJson: Execute Sql from the body returning JSON |
| [**PutByQueryParquet**](#putbyqueryparquet) | **PUT** `/honeycomb/api/Sql/parquet` | PutByQueryParquet: Execute Sql from the body making a Parquet file |
| [**PutByQueryPipe**](#putbyquerypipe) | **PUT** `/honeycomb/api/Sql/pipe` | PutByQueryPipe: Execute Sql from the body making pipe-delimited |
| [**PutByQuerySqlite**](#putbyquerysqlite) | **PUT** `/honeycomb/api/Sql/sqlite` | PutByQuerySqlite: Execute Sql from the body returning SqLite DB |
| [**PutByQueryXml**](#putbyqueryxml) | **PUT** `/honeycomb/api/Sql/xml` | PutByQueryXml: Execute Sql from the body returning XML |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SqlExecutionApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
```

---

<a id="getbyquerycsv"></a>
## GetByQueryCsv

> string GetByQueryCsv(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, bool? download = null, int? timeout = null, string? delimiter = null, string? escape = null, string? dateTimeFormat = null)

GetByQueryCsv: Execute Sql from the url returning CSV

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var download = false;  // bool? (optional)
var timeout = 150;  // int? (optional)
var delimiter = "delimiter_example";  // string? (optional)
var escape = "escape_example";  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
string result = apiInstance.GetByQueryCsv(query, scalarParameters, queryName, download, timeout, delimiter, escape, dateTimeFormat);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |
| **delimiter** | **string?** | query | optional | Delimiter string to override the default |
| **escape** | **string?** | query | optional | Escape character to override the default |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |

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
<summary>Using the GetByQueryCsvWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetByQueryCsvWithHttpInfo(query, scalarParameters, queryName, download, timeout, delimiter, escape, dateTimeFormat);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbyqueryexcel"></a>
## GetByQueryExcel

> System.IO.Stream GetByQueryExcel(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, string? dateTimeFormat = null, int? timeout = null)

GetByQueryExcel: Execute Sql from the url returning an Excel file

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var timeout = 150;  // int? (optional)
System.IO.Stream result = apiInstance.GetByQueryExcel(query, scalarParameters, queryName, dateTimeFormat, timeout);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.000&#x60; (Excel support for this is limited) |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

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
<summary>Using the GetByQueryExcelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.GetByQueryExcelWithHttpInfo(query, scalarParameters, queryName, dateTimeFormat, timeout);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbyqueryjson"></a>
## GetByQueryJson

> string GetByQueryJson(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeout = null, bool? jsonProper = null, bool? includeLineage = null)

GetByQueryJson: Execute Sql from the url returning JSON

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var timeout = 150;  // int? (optional)
var jsonProper = false;  // bool? (optional)
var includeLineage = false;  // bool? (optional)
string result = apiInstance.GetByQueryJson(query, scalarParameters, queryName, timeout, jsonProper, includeLineage);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |
| **jsonProper** | **bool?** | query | optional | Should this be text/json (not json-encoded-as-a-string) Default: `false` |
| **includeLineage** | **bool?** | query | optional | Should lineage be included? If true this will be &#x60;properJson&#x60; and the jsonProper flag ignored Default: `false` |

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
<summary>Using the GetByQueryJsonWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetByQueryJsonWithHttpInfo(query, scalarParameters, queryName, timeout, jsonProper, includeLineage);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbyqueryparquet"></a>
## GetByQueryParquet

> System.IO.Stream GetByQueryParquet(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeout = null)

GetByQueryParquet: Execute Sql from the url returning a Parquet file

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var timeout = 150;  // int? (optional)
System.IO.Stream result = apiInstance.GetByQueryParquet(query, scalarParameters, queryName, timeout);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

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
<summary>Using the GetByQueryParquetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.GetByQueryParquetWithHttpInfo(query, scalarParameters, queryName, timeout);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbyquerypipe"></a>
## GetByQueryPipe

> string GetByQueryPipe(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, bool? download = null, string? dateTimeFormat = null, int? timeout = null)

GetByQueryPipe: Execute Sql from the url returning pipe-delimited

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var download = false;  // bool? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var timeout = 150;  // int? (optional)
string result = apiInstance.GetByQueryPipe(query, scalarParameters, queryName, download, dateTimeFormat, timeout);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

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
<summary>Using the GetByQueryPipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetByQueryPipeWithHttpInfo(query, scalarParameters, queryName, download, dateTimeFormat, timeout);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbyquerysqlite"></a>
## GetByQuerySqlite

> System.IO.Stream GetByQuerySqlite(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeout = null)

GetByQuerySqlite: Execute Sql from the url returning SqLite DB

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var timeout = 150;  // int? (optional)
System.IO.Stream result = apiInstance.GetByQuerySqlite(query, scalarParameters, queryName, timeout);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

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
<summary>Using the GetByQuerySqliteWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.GetByQuerySqliteWithHttpInfo(query, scalarParameters, queryName, timeout);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbyqueryxml"></a>
## GetByQueryXml

> string GetByQueryXml(string query, Dictionary<string, string>? scalarParameters = null, string? queryName = null, bool? download = null, int? timeout = null)

GetByQueryXml: Execute Sql from the url returning XML

 Returns data from a simple single-line query execution which is specified on the url. e.g. `select ^ from Sys.Field order by 1, 2`, returned in the format of the method name.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var query = select ^ from Sys.Field order by 1, 2;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var download = false;  // bool? (optional)
var timeout = 150;  // int? (optional)
string result = apiInstance.GetByQueryXml(query, scalarParameters, queryName, download, timeout);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | path | **required** | LuminesceSql to Execute (must be one line only) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **timeout** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

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
<summary>Using the GetByQueryXmlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetByQueryXmlWithHttpInfo(query, scalarParameters, queryName, download, timeout);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyquerycsv"></a>
## PutByQueryCsv

> string PutByQueryCsv(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, bool? download = null, int? timeoutSeconds = null, string? delimiter = null, string? escape = null, string? dateTimeFormat = null)

PutByQueryCsv: Execute Sql from the body returning CSV

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var download = false;  // bool? (optional)
var timeoutSeconds = 150;  // int? (optional)
var delimiter = "delimiter_example";  // string? (optional)
var escape = "escape_example";  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
string result = apiInstance.PutByQueryCsv(body, scalarParameters, queryName, download, timeoutSeconds, delimiter, escape, dateTimeFormat);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |
| **delimiter** | **string?** | query | optional | Delimiter string to override the default |
| **escape** | **string?** | query | optional | Escape character to override the default |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQueryCsvWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutByQueryCsvWithHttpInfo(body, scalarParameters, queryName, download, timeoutSeconds, delimiter, escape, dateTimeFormat);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyqueryexcel"></a>
## PutByQueryExcel

> System.IO.Stream PutByQueryExcel(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, string? dateTimeFormat = null, int? timeoutSeconds = null)

PutByQueryExcel: Execute Sql from the body making an Excel file

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var timeoutSeconds = 150;  // int? (optional)
System.IO.Stream result = apiInstance.PutByQueryExcel(body, scalarParameters, queryName, dateTimeFormat, timeoutSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.000&#x60; (Excel support for this is limited) |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

### Return type

**System.IO.Stream**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQueryExcelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.PutByQueryExcelWithHttpInfo(body, scalarParameters, queryName, dateTimeFormat, timeoutSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyqueryjson"></a>
## PutByQueryJson

> string PutByQueryJson(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeoutSeconds = null, bool? jsonProper = null, bool? includeLineage = null)

PutByQueryJson: Execute Sql from the body returning JSON

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var timeoutSeconds = 150;  // int? (optional)
var jsonProper = false;  // bool? (optional)
var includeLineage = false;  // bool? (optional)
string result = apiInstance.PutByQueryJson(body, scalarParameters, queryName, timeoutSeconds, jsonProper, includeLineage);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |
| **jsonProper** | **bool?** | query | optional | Should this be text/json (not json-encoded-as-a-string) Default: `false` |
| **includeLineage** | **bool?** | query | optional | Should lineage be included? If true this will be &#x60;properJson&#x60; and the jsonProper flag ignored Default: `false` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQueryJsonWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutByQueryJsonWithHttpInfo(body, scalarParameters, queryName, timeoutSeconds, jsonProper, includeLineage);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyqueryparquet"></a>
## PutByQueryParquet

> System.IO.Stream PutByQueryParquet(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeoutSeconds = null)

PutByQueryParquet: Execute Sql from the body making a Parquet file

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var timeoutSeconds = 150;  // int? (optional)
System.IO.Stream result = apiInstance.PutByQueryParquet(body, scalarParameters, queryName, timeoutSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

### Return type

**System.IO.Stream**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQueryParquetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.PutByQueryParquetWithHttpInfo(body, scalarParameters, queryName, timeoutSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyquerypipe"></a>
## PutByQueryPipe

> string PutByQueryPipe(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, bool? download = null, string? dateTimeFormat = null, int? timeoutSeconds = null)

PutByQueryPipe: Execute Sql from the body making pipe-delimited

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var download = false;  // bool? (optional)
var dateTimeFormat = "dateTimeFormat_example";  // string? (optional)
var timeoutSeconds = 150;  // int? (optional)
string result = apiInstance.PutByQueryPipe(body, scalarParameters, queryName, download, dateTimeFormat, timeoutSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **dateTimeFormat** | **string?** | query | optional | Format to apply for DateTime data, leaving blank gives the Luminesce Exporter default, currently &#x60;yyyy-MM-dd HH:mm:ss.fff&#x60; |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQueryPipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutByQueryPipeWithHttpInfo(body, scalarParameters, queryName, download, dateTimeFormat, timeoutSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyquerysqlite"></a>
## PutByQuerySqlite

> System.IO.Stream PutByQuerySqlite(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, int? timeoutSeconds = null)

PutByQuerySqlite: Execute Sql from the body returning SqLite DB

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var timeoutSeconds = 150;  // int? (optional)
System.IO.Stream result = apiInstance.PutByQuerySqlite(body, scalarParameters, queryName, timeoutSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

### Return type

**System.IO.Stream**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQuerySqliteWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.PutByQuerySqliteWithHttpInfo(body, scalarParameters, queryName, timeoutSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putbyqueryxml"></a>
## PutByQueryXml

> string PutByQueryXml(string body, Dictionary<string, string>? scalarParameters = null, string? queryName = null, bool? download = null, int? timeoutSeconds = null)

PutByQueryXml: Execute Sql from the body returning XML

 For more complex LuminesceSql a PUT will allow for longer and line break delimited Sql, whic will be returned in the format of the method name. e.g.: ```sql @@cutoff = select #2020-02-01#; @issues = select Id, SortId, Summary, Created, Updated from Dev.Jira.Issue where Project='HC' and Created < @@cutoff and Updated > @@cutoff;  select i.Id, i.SortId, i.Summary, LinkText, LinkedIssueId, LinkedIssueSortId, LinkedIssueSummary from @issues i inner join Dev.Jira.Issue.Link li     on i.Id = li.IssueId ```  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something failed with the execution or parsing of your query - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlExecutionApi>();
var body = select * from sys.field;  // string
var scalarParameters = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
var queryName = Get tables/fields;  // string? (optional)
var download = false;  // bool? (optional)
var timeoutSeconds = 150;  // int? (optional)
string result = apiInstance.PutByQueryXml(body, scalarParameters, queryName, download, timeoutSeconds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Execute (may be multi-line) |
| **scalarParameters** | [Dictionary&lt;string, string&gt;?](string.md) | query | optional | Json encoded dictionary of key-value pairs for scalar parameter values to use in the sql execution. |
| **queryName** | **string?** | query | optional | Name to apply to the query in logs and &#x60;Sys.Logs.HcQueryStart&#x60; |
| **download** | **bool?** | query | optional | Makes this a file-download request (as opposed to returning the data in the response-body) Default: `false` |
| **timeoutSeconds** | **int?** | query | optional | In seconds: &lt;0 or &gt; 175 → 175s (Maximum allowed), 0 → 120s Default: `0` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: `text/plain`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the PutByQueryXmlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutByQueryXmlWithHttpInfo(body, scalarParameters, queryName, download, timeoutSeconds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

