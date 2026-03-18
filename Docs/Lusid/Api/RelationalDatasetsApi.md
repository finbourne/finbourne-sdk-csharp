# Finbourne.Sdk.Lusid.Api.RelationalDatasetsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchDeleteRelationalData**](#batchdeleterelationaldata) | **POST** `/api/api/relationaldatasets/{relationalDatasetDefinitionScope}/{relationalDatasetDefinitionCode}/$batchDelete` | BatchDeleteRelationalData: Batch Delete Relational Data Points for a given Relational Dataset Definition. |
| [**BatchUpsertRelationalData**](#batchupsertrelationaldata) | **POST** `/api/api/relationaldatasets/{relationalDatasetDefinitionScope}/{relationalDatasetDefinitionCode}/$batchUpsert` | BatchUpsertRelationalData: Batch Upsert Relational Data Points for a given Relational Dataset Definition. |
| [**QueryRelationalData**](#queryrelationaldata) | **POST** `/api/api/relationaldatasets/{relationalDatasetDefinitionScope}/{relationalDatasetDefinitionCode}/$query` | QueryRelationalData: Query Relational Data Points for a given Relational Dataset Definition. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RelationalDatasetsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetsApi>();
```

---

<a id="batchdeleterelationaldata"></a>
## BatchDeleteRelationalData

> BatchDeleteRelationalDataResponse BatchDeleteRelationalData(string relationalDatasetDefinitionScope, string relationalDatasetDefinitionCode, Dictionary<string, DeleteRelationalDataPointRequest> requestBody, string? successMode = null)

BatchDeleteRelationalData: Batch Delete Relational Data Points for a given Relational Dataset Definition.

Batch Delete Relational Data Points for a given Relational Dataset Definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetsApi>();
var relationalDatasetDefinitionScope = "relationalDatasetDefinitionScope_example";  // string
var relationalDatasetDefinitionCode = "relationalDatasetDefinitionCode_example";  // string
var requestBody = new Dictionary<string, DeleteRelationalDataPointRequest>(); // Dictionary<string, DeleteRelationalDataPointRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchDeleteRelationalDataResponse result = apiInstance.BatchDeleteRelationalData(relationalDatasetDefinitionScope, relationalDatasetDefinitionCode, requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **relationalDatasetDefinitionScope** | **string** | path | **required** | The Scope of the relational dataset definition. |
| **relationalDatasetDefinitionCode** | **string** | path | **required** | The Code of the relational dataset definition. |
| **requestBody** | [Dictionary&lt;string, DeleteRelationalDataPointRequest&gt;](DeleteRelationalDataPointRequest.md) | body | **required** | The Delete Request. |
| **successMode** | **string?** | query | optional | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial.              Note: If using partial failure modes, then it is important to check the response body for failures as any failures will still return a 200 status code. Default: `&quot;Partial&quot;` |

### Return type

[BatchDeleteRelationalDataResponse](BatchDeleteRelationalDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted DataPoint metadata. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchDeleteRelationalDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchDeleteRelationalDataResponse> response = apiInstance.BatchDeleteRelationalDataWithHttpInfo(relationalDatasetDefinitionScope, relationalDatasetDefinitionCode, requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchupsertrelationaldata"></a>
## BatchUpsertRelationalData

> BatchUpsertRelationalDatasetsResponse BatchUpsertRelationalData(string relationalDatasetDefinitionScope, string relationalDatasetDefinitionCode, Dictionary<string, UpsertRelationalDataPointRequest> requestBody, string? successMode = null)

BatchUpsertRelationalData: Batch Upsert Relational Data Points for a given Relational Dataset Definition.

Batch Upsert Relational Data Points for a given Relational Dataset Definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetsApi>();
var relationalDatasetDefinitionScope = "relationalDatasetDefinitionScope_example";  // string
var relationalDatasetDefinitionCode = "relationalDatasetDefinitionCode_example";  // string
var requestBody = new Dictionary<string, UpsertRelationalDataPointRequest>(); // Dictionary<string, UpsertRelationalDataPointRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchUpsertRelationalDatasetsResponse result = apiInstance.BatchUpsertRelationalData(relationalDatasetDefinitionScope, relationalDatasetDefinitionCode, requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **relationalDatasetDefinitionScope** | **string** | path | **required** | The Scope of the relational dataset definition. |
| **relationalDatasetDefinitionCode** | **string** | path | **required** | The Code of the relational dataset definition. |
| **requestBody** | [Dictionary&lt;string, UpsertRelationalDataPointRequest&gt;](UpsertRelationalDataPointRequest.md) | body | **required** | The DataPoints to upsert. |
| **successMode** | **string?** | query | optional | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial.              Note: If using partial failure modes, then it is important to check the response body for failures as any failures will still return a 200 status code. Default: `&quot;Partial&quot;` |

### Return type

[BatchUpsertRelationalDatasetsResponse](BatchUpsertRelationalDatasetsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relational data points that were upserted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertRelationalDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertRelationalDatasetsResponse> response = apiInstance.BatchUpsertRelationalDataWithHttpInfo(relationalDatasetDefinitionScope, relationalDatasetDefinitionCode, requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="queryrelationaldata"></a>
## QueryRelationalData

> PagedResourceListOfRelationalDataPointResponse QueryRelationalData(string relationalDatasetDefinitionScope, string relationalDatasetDefinitionCode, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, string? page = null, int? limit = null, QueryRelationalDatasetRequest? queryRelationalDatasetRequest = null)

QueryRelationalData: Query Relational Data Points for a given Relational Dataset Definition.

Query Relational Data Points for a given Relational Dataset Definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetsApi>();
var relationalDatasetDefinitionScope = "relationalDatasetDefinitionScope_example";  // string
var relationalDatasetDefinitionCode = "relationalDatasetDefinitionCode_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var queryRelationalDatasetRequest = new QueryRelationalDatasetRequest?(); // QueryRelationalDatasetRequest? (optional)
PagedResourceListOfRelationalDataPointResponse result = apiInstance.QueryRelationalData(relationalDatasetDefinitionScope, relationalDatasetDefinitionCode, asAt, effectiveAt, page, limit, queryRelationalDatasetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **relationalDatasetDefinitionScope** | **string** | path | **required** | The Scope of the relational dataset definition. |
| **relationalDatasetDefinitionCode** | **string** | path | **required** | The Code of the relational dataset definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the dataset(s). Defaults to returning the latest version of each dataset if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to query the datasets.              Defaults to the current LUSID system datetime if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue query datasets. This value is returned from the previous call.              If a pagination token is provided, the filter, customSortBy, effectiveAt and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **queryRelationalDatasetRequest** | [QueryRelationalDatasetRequest?](QueryRelationalDatasetRequest?.md) | body | optional | The query request. |

### Return type

[PagedResourceListOfRelationalDataPointResponse](PagedResourceListOfRelationalDataPointResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relational data points that were queried. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryRelationalDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRelationalDataPointResponse> response = apiInstance.QueryRelationalDataWithHttpInfo(relationalDatasetDefinitionScope, relationalDatasetDefinitionCode, asAt, effectiveAt, page, limit, queryRelationalDatasetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

