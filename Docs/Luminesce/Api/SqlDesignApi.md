# Finbourne.Sdk.Luminesce.Api.SqlDesignApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetProviderTemplateForExport**](#getprovidertemplateforexport) | **GET** `/honeycomb/api/Sql/providertemplateforexport` | GetProviderTemplateForExport: Makes a fields template for file importing via a writer |
| [**PutCaseStatementDesignSqlToDesign**](#putcasestatementdesignsqltodesign) | **PUT** `/honeycomb/api/Sql/tocasestatementdesign` | PutCaseStatementDesignSqlToDesign: Convert SQL to a case statement design object |
| [**PutCaseStatementDesignToSql**](#putcasestatementdesigntosql) | **PUT** `/honeycomb/api/Sql/fromcasestatementdesign` | PutCaseStatementDesignToSql: Convert a case statement design object to SQL |
| [**PutFileReadDesignToSql**](#putfilereaddesigntosql) | **PUT** `/honeycomb/api/Sql/fromfilereaddesign` | PutFileReadDesignToSql: Make file read SQL from a design object |
| [**PutInlinedPropertiesDesignSqlToDesign**](#putinlinedpropertiesdesignsqltodesign) | **PUT** `/honeycomb/api/Sql/toinlinedpropertiesdesign` | PutInlinedPropertiesDesignSqlToDesign: Make an inlined properties design from SQL |
| [**PutInlinedPropertiesDesignToSql**](#putinlinedpropertiesdesigntosql) | **PUT** `/honeycomb/api/Sql/frominlinedpropertiesdesign` | PutInlinedPropertiesDesignToSql: Make inlined properties SQL from a design object |
| [**PutIntellisense**](#putintellisense) | **PUT** `/honeycomb/api/Sql/intellisense` | PutIntellisense: Make intellisense prompts given an SQL snip-it |
| [**PutIntellisenseError**](#putintellisenseerror) | **PUT** `/honeycomb/api/Sql/intellisenseError` | PutIntellisenseError: Get error ranges from SQL |
| [**PutLusidGridToQuery**](#putlusidgridtoquery) | **PUT** `/honeycomb/api/Sql/fromlusidgrid` | [EXPERIMENTAL] PutLusidGridToQuery: Generates SQL from a dashboard view |
| [**PutQueryDesignToSql**](#putquerydesigntosql) | **PUT** `/honeycomb/api/Sql/fromdesign` | PutQueryDesignToSql: Make SQL from a structured query design |
| [**PutQueryToFormat**](#putquerytoformat) | **PUT** `/honeycomb/api/Sql/pretty` | PutQueryToFormat: Format SQL into a more readable form |
| [**PutSqlToExtractScalarParameters**](#putsqltoextractscalarparameters) | **PUT** `/honeycomb/api/Sql/extractscalarparameters` | PutSqlToExtractScalarParameters: Extract scalar parameter information from SQL |
| [**PutSqlToFileReadDesign**](#putsqltofilereaddesign) | **PUT** `/honeycomb/api/Sql/tofilereaddesign` | PutSqlToFileReadDesign: Make a design object from file-read SQL |
| [**PutSqlToQueryDesign**](#putsqltoquerydesign) | **PUT** `/honeycomb/api/Sql/todesign` | PutSqlToQueryDesign: Make a SQL-design object from SQL if possible |
| [**PutSqlToViewDesign**](#putsqltoviewdesign) | **PUT** `/honeycomb/api/Sql/toviewdesign` | PutSqlToViewDesign: Make a view-design from view creation SQL |
| [**PutSqlToWriterDesign**](#putsqltowriterdesign) | **PUT** `/honeycomb/api/Sql/towriterdesign` | PutSqlToWriterDesign: Make a SQL-writer-design object from SQL |
| [**PutViewDesignToSql**](#putviewdesigntosql) | **PUT** `/honeycomb/api/Sql/fromviewdesign` | PutViewDesignToSql: Make view creation sql from a view-design |
| [**PutWriterDesignToSql**](#putwriterdesigntosql) | **PUT** `/honeycomb/api/Sql/fromwriterdesign` | PutWriterDesignToSql: Make writer SQL from a writer-design object |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SqlDesignApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
```

---

<a id="getprovidertemplateforexport"></a>
## GetProviderTemplateForExport

> System.IO.Stream GetProviderTemplateForExport(string provider, string contentType)

GetProviderTemplateForExport: Makes a fields template for file importing via a writer

Generates a template file for all the writable fields for a given provider returned in CSV or Excel (xlsx) format (as a file to be downloaded)

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var provider = "provider_example";  // string
var contentType = "contentType_example";  // string
System.IO.Stream result = apiInstance.GetProviderTemplateForExport(provider, contentType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **provider** | **string** | query | **required** | Name of the provider for which this template is for |
| **contentType** | **string** | query | **required** | File content type for the Template. csv or excel |

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
<summary>Using the GetProviderTemplateForExportWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.GetProviderTemplateForExportWithHttpInfo(provider, contentType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putcasestatementdesignsqltodesign"></a>
## PutCaseStatementDesignSqlToDesign

> CaseStatementDesign PutCaseStatementDesignSqlToDesign(string? body = null)

PutCaseStatementDesignSqlToDesign: Convert SQL to a case statement design object

Converts a SQL query to a CaseStatementDesign object  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = CASE \n WHEN [currency] = 'US' THEN 'USD' \n WHEN [currency] = 'Gb' THEN 'GBP' \n ELSE [currency] \n END;  // string? (optional)
CaseStatementDesign result = apiInstance.PutCaseStatementDesignSqlToDesign(body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string?** | body | optional | SQL to attempt to create an case statement Design object from |

### Return type

[CaseStatementDesign](CaseStatementDesign.md)

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
<summary>Using the PutCaseStatementDesignSqlToDesignWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CaseStatementDesign> response = apiInstance.PutCaseStatementDesignSqlToDesignWithHttpInfo(body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putcasestatementdesigntosql"></a>
## PutCaseStatementDesignToSql

> string PutCaseStatementDesignToSql(CaseStatementDesign caseStatementDesign)

PutCaseStatementDesignToSql: Convert a case statement design object to SQL

Generates a SQL case statement query from a structured CaseStatementDesign object  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var caseStatementDesign = new CaseStatementDesign(); // CaseStatementDesign
string result = apiInstance.PutCaseStatementDesignToSql(caseStatementDesign);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **caseStatementDesign** | [CaseStatementDesign](CaseStatementDesign.md) | body | **required** | CaseStatementDesign object to try and create a SQL query from |

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
<summary>Using the PutCaseStatementDesignToSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutCaseStatementDesignToSqlWithHttpInfo(caseStatementDesign);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putfilereaddesigntosql"></a>
## PutFileReadDesignToSql

> FileReaderBuilderResponse PutFileReadDesignToSql(FileReaderBuilderDef fileReaderBuilderDef, bool? executeQuery = null)

PutFileReadDesignToSql: Make file read SQL from a design object

Generates SQL from a FileReaderBuilderDef object  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var fileReaderBuilderDef = new FileReaderBuilderDef(); // FileReaderBuilderDef
var executeQuery = true;  // bool? (optional)
FileReaderBuilderResponse result = apiInstance.PutFileReadDesignToSql(fileReaderBuilderDef, executeQuery);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **fileReaderBuilderDef** | [FileReaderBuilderDef](FileReaderBuilderDef.md) | body | **required** | Structured file read design object to generate SQL from |
| **executeQuery** | **bool?** | query | optional | Should the generated query be executed to build preview data or determine errors.&gt; Default: `true` |

### Return type

[FileReaderBuilderResponse](FileReaderBuilderResponse.md)

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
<summary>Using the PutFileReadDesignToSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FileReaderBuilderResponse> response = apiInstance.PutFileReadDesignToSqlWithHttpInfo(fileReaderBuilderDef, executeQuery);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putinlinedpropertiesdesignsqltodesign"></a>
## PutInlinedPropertiesDesignSqlToDesign

> InlinedPropertyDesign PutInlinedPropertiesDesignSqlToDesign(string? body = null)

PutInlinedPropertiesDesignSqlToDesign: Make an inlined properties design from SQL

Generates a SQL-inlined-properties-design object from SQL string, if possible.  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = @keysToCatalog = values('Portfolio/3897-78d4-e91c-26/location', 'PortfolioLocation', false, '');\n @config = select column1 as [Key], column2 as Name, column3 as IsMain, column4 as Description from @keysToCatalog; \n select * from Sys.Admin.Lusid.Provider.Configure where Provider = 'Lusid.Portfolio' and Configuration = @config;;  // string? (optional)
InlinedPropertyDesign result = apiInstance.PutInlinedPropertiesDesignSqlToDesign(body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string?** | body | optional | SQL query to attempt to generate the inlined properties design object from |

### Return type

[InlinedPropertyDesign](InlinedPropertyDesign.md)

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
<summary>Using the PutInlinedPropertiesDesignSqlToDesignWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InlinedPropertyDesign> response = apiInstance.PutInlinedPropertiesDesignSqlToDesignWithHttpInfo(body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putinlinedpropertiesdesigntosql"></a>
## PutInlinedPropertiesDesignToSql

> string PutInlinedPropertiesDesignToSql(InlinedPropertyDesign inlinedPropertyDesign)

PutInlinedPropertiesDesignToSql: Make inlined properties SQL from a design object

Generates inlined properties SQL from a structured design  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var inlinedPropertyDesign = new InlinedPropertyDesign(); // InlinedPropertyDesign
string result = apiInstance.PutInlinedPropertiesDesignToSql(inlinedPropertyDesign);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **inlinedPropertyDesign** | [InlinedPropertyDesign](InlinedPropertyDesign.md) | body | **required** | Inlined properties Designer specification to generate SQL from |

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
<summary>Using the PutInlinedPropertiesDesignToSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutInlinedPropertiesDesignToSqlWithHttpInfo(inlinedPropertyDesign);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putintellisense"></a>
## PutIntellisense

> IntellisenseResponse PutIntellisense(IntellisenseRequest intellisenseRequest)

PutIntellisense: Make intellisense prompts given an SQL snip-it

Generate a set of possible intellisense prompts given a SQL snip-it (in need not yet be valid SQL) and cursor location  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var intellisenseRequest = new IntellisenseRequest(); // IntellisenseRequest
IntellisenseResponse result = apiInstance.PutIntellisense(intellisenseRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **intellisenseRequest** | [IntellisenseRequest](IntellisenseRequest.md) | body | **required** | SQL and a row/colum position within it from which to determine intellisense options for the user to potentially choose from. |

### Return type

[IntellisenseResponse](IntellisenseResponse.md)

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
<summary>Using the PutIntellisenseWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IntellisenseResponse> response = apiInstance.PutIntellisenseWithHttpInfo(intellisenseRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putintellisenseerror"></a>
## PutIntellisenseError

> ErrorHighlightResponse PutIntellisenseError(ErrorHighlightRequest errorHighlightRequest)

PutIntellisenseError: Get error ranges from SQL

Generate a set of error ranges, if any, in the given SQL (expressed as Lines)  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var errorHighlightRequest = new ErrorHighlightRequest(); // ErrorHighlightRequest
ErrorHighlightResponse result = apiInstance.PutIntellisenseError(errorHighlightRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **errorHighlightRequest** | [ErrorHighlightRequest](ErrorHighlightRequest.md) | body | **required** | SQL (by line) to syntax check and return error ranges from within, if any. |

### Return type

[ErrorHighlightResponse](ErrorHighlightResponse.md)

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
<summary>Using the PutIntellisenseErrorWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ErrorHighlightResponse> response = apiInstance.PutIntellisenseErrorWithHttpInfo(errorHighlightRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putlusidgridtoquery"></a>
## PutLusidGridToQuery

> string PutLusidGridToQuery(LusidGridData lusidGridData)

[EXPERIMENTAL] PutLusidGridToQuery: Generates SQL from a dashboard view

Used to convert dashboard views in LUSID to SQL that can be run in Lumi

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var lusidGridData = new LusidGridData(); // LusidGridData
string result = apiInstance.PutLusidGridToQuery(lusidGridData);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **lusidGridData** | [LusidGridData](LusidGridData.md) | body | **required** |  |

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
<summary>Using the PutLusidGridToQueryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutLusidGridToQueryWithHttpInfo(lusidGridData);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putquerydesigntosql"></a>
## PutQueryDesignToSql

> string PutQueryDesignToSql(QueryDesign queryDesign)

PutQueryDesignToSql: Make SQL from a structured query design

Generates SQL from a QueryDesign object  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var queryDesign = new QueryDesign(); // QueryDesign
string result = apiInstance.PutQueryDesignToSql(queryDesign);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **queryDesign** | [QueryDesign](QueryDesign.md) | body | **required** | Structured Query design object to generate SQL from |

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
<summary>Using the PutQueryDesignToSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutQueryDesignToSqlWithHttpInfo(queryDesign);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putquerytoformat"></a>
## PutQueryToFormat

> string PutQueryToFormat(string body, bool? trailingCommas = null, bool? uppercaseKeywords = null, bool? breakJoinOnSections = null, bool? spaceAfterExpandedComma = null, bool? keywordStandardization = null, bool? expandCommaLists = null, bool? expandInLists = null, bool? expandBooleanExpressions = null, bool? expandBetweenConditions = null, bool? expandCaseStatements = null, int? maxLineWidth = null, bool? spaceBeforeTrailingSingleLineComments = null, bool? multilineCommentExtraLineBreak = null)

PutQueryToFormat: Format SQL into a more readable form

 This formats SQL (given a set of options as to how to do so), a.k.a. Pretty-Print the SQL. It takes some SQL (or a fragment thereof, it need not fully parse as yet and certainly need not execute correctly) and returns the reformatted version. e.g. ```sql select x,y,z from a inner join b on a.x=b.x where x>y or y!=z ``` becomes ```sql select x, y, z from a inner join b    on a.x = b.x where x > y    or y != z ``` 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = select * from sys.field;  // string
var trailingCommas = true;  // bool? (optional)
var uppercaseKeywords = false;  // bool? (optional)
var breakJoinOnSections = true;  // bool? (optional)
var spaceAfterExpandedComma = true;  // bool? (optional)
var keywordStandardization = true;  // bool? (optional)
var expandCommaLists = false;  // bool? (optional)
var expandInLists = false;  // bool? (optional)
var expandBooleanExpressions = true;  // bool? (optional)
var expandBetweenConditions = true;  // bool? (optional)
var expandCaseStatements = true;  // bool? (optional)
var maxLineWidth = 120;  // int? (optional)
var spaceBeforeTrailingSingleLineComments = true;  // bool? (optional)
var multilineCommentExtraLineBreak = false;  // bool? (optional)
string result = apiInstance.PutQueryToFormat(body, trailingCommas, uppercaseKeywords, breakJoinOnSections, spaceAfterExpandedComma, keywordStandardization, expandCommaLists, expandInLists, expandBooleanExpressions, expandBetweenConditions, expandCaseStatements, maxLineWidth, spaceBeforeTrailingSingleLineComments, multilineCommentExtraLineBreak);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | LuminesceSql to Pretty-Print. Even if it doesn&#39;t parse an attempt will be made to format it |
| **trailingCommas** | **bool?** | query | optional | Should commas be after an expression (as opposed to before) Default: `true` |
| **uppercaseKeywords** | **bool?** | query | optional | Should key words be capitalized Default: `false` |
| **breakJoinOnSections** | **bool?** | query | optional | Should clauses on joins be given line breaks? Default: `true` |
| **spaceAfterExpandedComma** | **bool?** | query | optional | Should comma-lists have spaces after the commas? Default: `true` |
| **keywordStandardization** | **bool?** | query | optional | Should the \&quot;nicest\&quot; key words be used? (e.g. JOIN -&gt; INNER JOIN) Default: `true` |
| **expandCommaLists** | **bool?** | query | optional | Should comma-lists (e.g. select a,b,c) have line breaks added? Default: `false` |
| **expandInLists** | **bool?** | query | optional | Should IN-lists have line breaks added? Default: `false` |
| **expandBooleanExpressions** | **bool?** | query | optional | Should boolean expressions have line breaks added? Default: `true` |
| **expandBetweenConditions** | **bool?** | query | optional | Should between conditions have line breaks added? Default: `true` |
| **expandCaseStatements** | **bool?** | query | optional | Should case-statements have line breaks added? Default: `true` |
| **maxLineWidth** | **int?** | query | optional | Maximum number of characters to allow on one line (if possible) Default: `120` |
| **spaceBeforeTrailingSingleLineComments** | **bool?** | query | optional | Should the be a space before trailing single line comments? Default: `true` |
| **multilineCommentExtraLineBreak** | **bool?** | query | optional | Should an additional line break be added after multi-line comments? Default: `false` |

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
<summary>Using the PutQueryToFormatWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutQueryToFormatWithHttpInfo(body, trailingCommas, uppercaseKeywords, breakJoinOnSections, spaceAfterExpandedComma, keywordStandardization, expandCommaLists, expandInLists, expandBooleanExpressions, expandBetweenConditions, expandCaseStatements, maxLineWidth, spaceBeforeTrailingSingleLineComments, multilineCommentExtraLineBreak);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putsqltoextractscalarparameters"></a>
## PutSqlToExtractScalarParameters

> List&lt;ScalarParameter&gt; PutSqlToExtractScalarParameters(string body)

PutSqlToExtractScalarParameters: Extract scalar parameter information from SQL

Extracts information about all the scalar parameters defined in the given SQL statement  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = select abc, :p1:'this' as c1 from xxx where abc = :abcP:{1,2,3} or xyz in (:p2:, 'zzz');  // string
List<ScalarParameter> result = apiInstance.PutSqlToExtractScalarParameters(body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | SQL query to generate the design object from |

### Return type

[List&lt;ScalarParameter&gt;](ScalarParameter.md)

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
<summary>Using the PutSqlToExtractScalarParametersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<ScalarParameter>> response = apiInstance.PutSqlToExtractScalarParametersWithHttpInfo(body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putsqltofilereaddesign"></a>
## PutSqlToFileReadDesign

> FileReaderBuilderDef PutSqlToFileReadDesign(bool? determineAvailableSources = null, string? body = null)

PutSqlToFileReadDesign: Make a design object from file-read SQL

Generates a SQL-file-read-design object from SQL string, if possible.  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var determineAvailableSources = true;  // bool? (optional)
var body = @x = \nuse Drive.Csv\n  --file=/some/folder/somefile.csv\nenduse;\n\nselect * from @x;;  // string? (optional)
FileReaderBuilderDef result = apiInstance.PutSqlToFileReadDesign(determineAvailableSources, body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **determineAvailableSources** | **bool?** | query | optional | Should the available sources be determined from &#x60;Sys.Registration&#x60; Default: `true` |
| **body** | **string?** | body | optional | SQL query to generate the file read design object from |

### Return type

[FileReaderBuilderDef](FileReaderBuilderDef.md)

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
<summary>Using the PutSqlToFileReadDesignWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FileReaderBuilderDef> response = apiInstance.PutSqlToFileReadDesignWithHttpInfo(determineAvailableSources, body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putsqltoquerydesign"></a>
## PutSqlToQueryDesign

> QueryDesign PutSqlToQueryDesign(string body, bool? validateWithMetadata = null, QueryDesignerVersion? version = null)

PutSqlToQueryDesign: Make a SQL-design object from SQL if possible

Generates a QueryDesign object from simple SQL if possible  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = SELECT [TableName], Count(distinct [FieldName]) as [NumberOfFields], case [FieldType] when 'Column' then 'col' else [FieldType] end as FieldType2  FROM [Sys.Field] WHERE ([TableName] = 'Sys.Registration') GROUP BY [TableName], [FieldType2] ORDER BY [DataType] LIMIT 42;  // string
var validateWithMetadata = true;  // bool? (optional)
var version = new QueryDesignerVersion?(); // QueryDesignerVersion? (optional)
QueryDesign result = apiInstance.PutSqlToQueryDesign(body, validateWithMetadata, version);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | SQL query to generate the design object from |
| **validateWithMetadata** | **bool?** | query | optional | Should the table be validated against the users&#39; view of Sys.Field to fill in DataTypes, etc.? Default: `true` |
| **version** | [QueryDesignerVersion?](QueryDesignerVersion?.md) | query | optional | Designer version number used to support multiple web user interface versions. Only some values will be allowed and this will change over time (as mentioned this whole method is largely internal to the Finbourne web user interfaces and evolves over time). |

### Return type

[QueryDesign](QueryDesign.md)

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
<summary>Using the PutSqlToQueryDesignWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<QueryDesign> response = apiInstance.PutSqlToQueryDesignWithHttpInfo(body, validateWithMetadata, version);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putsqltoviewdesign"></a>
## PutSqlToViewDesign

> ConvertToViewData PutSqlToViewDesign(string body)

PutSqlToViewDesign: Make a view-design from view creation SQL

Converts SQL which creates a view into a structured ConvertToViewData object  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = @x = \nuse Sys.Admin.SetupView\n  --provider=YourView\n----\nselect * from Lusid.Instrument\nenduse;\n\nselect * from @x;;  // string
ConvertToViewData result = apiInstance.PutSqlToViewDesign(body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | SQL Query to generate the ConvertToViewData object from |

### Return type

[ConvertToViewData](ConvertToViewData.md)

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
<summary>Using the PutSqlToViewDesignWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConvertToViewData> response = apiInstance.PutSqlToViewDesignWithHttpInfo(body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putsqltowriterdesign"></a>
## PutSqlToWriterDesign

> WriterDesign PutSqlToWriterDesign(string body, bool? mergeAdditionalMappingFields = null)

PutSqlToWriterDesign: Make a SQL-writer-design object from SQL

Generates a SQL-writer-design object (WriterDesign) from a SQL query, if possible  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var body = Select abc from xyz;  // string
var mergeAdditionalMappingFields = false;  // bool? (optional)
WriterDesign result = apiInstance.PutSqlToWriterDesign(body, mergeAdditionalMappingFields);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **body** | **string** | body | **required** | SQL query to generate the writer design object from |
| **mergeAdditionalMappingFields** | **bool?** | query | optional | Should &#x60;Sys.Field&#x60; be used to find additional potential fields to map from? (not always possible) Default: `false` |

### Return type

[WriterDesign](WriterDesign.md)

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
<summary>Using the PutSqlToWriterDesignWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WriterDesign> response = apiInstance.PutSqlToWriterDesignWithHttpInfo(body, mergeAdditionalMappingFields);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putviewdesigntosql"></a>
## PutViewDesignToSql

> string PutViewDesignToSql(ConvertToViewData convertToViewData)

PutViewDesignToSql: Make view creation sql from a view-design

Converts a ConvertToView specification into SQL that creates a view  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var convertToViewData = new ConvertToViewData(); // ConvertToViewData
string result = apiInstance.PutViewDesignToSql(convertToViewData);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **convertToViewData** | [ConvertToViewData](ConvertToViewData.md) | body | **required** | Structured Query design object to generate SQL from |

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
<summary>Using the PutViewDesignToSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutViewDesignToSqlWithHttpInfo(convertToViewData);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putwriterdesigntosql"></a>
## PutWriterDesignToSql

> string PutWriterDesignToSql(WriterDesign writerDesign)

PutWriterDesignToSql: Make writer SQL from a writer-design object

Generates writer SQL from a valid WriterDesign structure  > This method is generally only intended for IDE generation purposes.  > It is largely internal to the Finbourne web user interfaces and subject to change without notice. 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SqlDesignApi>();
var writerDesign = new WriterDesign(); // WriterDesign
string result = apiInstance.PutWriterDesignToSql(writerDesign);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **writerDesign** | [WriterDesign](WriterDesign.md) | body | **required** | Structured Writer Design design object to generate Writer SQL from |

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
<summary>Using the PutWriterDesignToSqlWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.PutWriterDesignToSqlWithHttpInfo(writerDesign);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

