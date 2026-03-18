# Finbourne.Sdk.Lusid.Api.StructuredResultDataApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDataMap**](#createdatamap) | **POST** `/api/api/unitresults/datamap/{scope}` | CreateDataMap: Create data map |
| [**DeleteStructuredResultData**](#deletestructuredresultdata) | **POST** `/api/api/unitresults/{scope}/$delete` | DeleteStructuredResultData: Delete structured result data |
| [**GetAddressKeyDefinitionsForDocument**](#getaddresskeydefinitionsfordocument) | **GET** `/api/api/unitresults/virtualdocument/{scope}/{code}/{source}/{resultType}/addresskeydefinitions` | GetAddressKeyDefinitionsForDocument: Get AddressKeyDefinitions for a virtual document. |
| [**GetDataMap**](#getdatamap) | **POST** `/api/api/unitresults/datamap/{scope}/$get` | GetDataMap: Get data map |
| [**GetStructuredResultData**](#getstructuredresultdata) | **POST** `/api/api/unitresults/{scope}/$get` | GetStructuredResultData: Get structured result data |
| [**GetVirtualDocument**](#getvirtualdocument) | **POST** `/api/api/unitresults/virtualdocument/{scope}/$get` | GetVirtualDocument: Get Virtual Documents |
| [**GetVirtualDocumentRows**](#getvirtualdocumentrows) | **GET** `/api/api/unitresults/virtualdocument/{scope}/{code}/{source}/{resultType}` | GetVirtualDocumentRows: Get Virtual Document Rows |
| [**UpsertResultValue**](#upsertresultvalue) | **POST** `/api/api/unitresults/resultvalue/{scope}` | UpsertResultValue: Upsert result value |
| [**UpsertStructuredResultData**](#upsertstructuredresultdata) | **POST** `/api/api/unitresults/{scope}` | UpsertStructuredResultData: Upsert structured result data |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<StructuredResultDataApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
```

---

<a id="createdatamap"></a>
## CreateDataMap

> UpsertStructuredDataResponse CreateDataMap(string scope, Dictionary<string, CreateDataMapRequest> requestBody)

CreateDataMap: Create data map

Create or update one or more structured result store address definition data maps in a particular scope. Note these are immutable and cannot be changed once created.                In the request, each data map must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data map object in the response.                The response returns both the collection of successfully created or updated data maps, as well as those that failed.  For each failure, a reason is provided.                It is important to check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, CreateDataMapRequest>(); // Dictionary<string, CreateDataMapRequest>
UpsertStructuredDataResponse result = apiInstance.CreateDataMap(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create or update data maps. |
| **requestBody** | [Dictionary&lt;string, CreateDataMapRequest&gt;](CreateDataMapRequest.md) | body | **required** | Individual data map creation requests. |

### Return type

[UpsertStructuredDataResponse](UpsertStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully created or updated data maps along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateDataMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertStructuredDataResponse> response = apiInstance.CreateDataMapWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletestructuredresultdata"></a>
## DeleteStructuredResultData

> AnnulStructuredDataResponse DeleteStructuredResultData(string scope, Dictionary<string, StructuredResultDataId> requestBody)

DeleteStructuredResultData: Delete structured result data

Delete one or more structured result data items from a particular scope. Each item is identified by a unique ID which includes  information about its type as well as the exact effective datetime (to the microsecond) at which it entered the system (became valid).                In the request, each data item must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data item in the response.                The response returns both the collection of successfully deleted data items, as well as those that failed.  For each failure, a reason is provided.                It is important to check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, StructuredResultDataId>(); // Dictionary<string, StructuredResultDataId>
AnnulStructuredDataResponse result = apiInstance.DeleteStructuredResultData(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope from which to delete data items. |
| **requestBody** | [Dictionary&lt;string, StructuredResultDataId&gt;](StructuredResultDataId.md) | body | **required** | The data IDs to delete, each keyed by a unique, ephemeral correlation ID. |

### Return type

[AnnulStructuredDataResponse](AnnulStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully deleted data items along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteStructuredResultDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulStructuredDataResponse> response = apiInstance.DeleteStructuredResultDataWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaddresskeydefinitionsfordocument"></a>
## GetAddressKeyDefinitionsForDocument

> ResourceListOfAddressKeyDefinition GetAddressKeyDefinitionsForDocument(string scope, string code, string source, string resultType, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

GetAddressKeyDefinitionsForDocument: Get AddressKeyDefinitions for a virtual document.

For a given virtual document retrieve all the address key definitions that are in use.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var source = "source_example";  // string
var resultType = "resultType_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfAddressKeyDefinition result = apiInstance.GetAddressKeyDefinitionsForDocument(scope, code, source, resultType, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the document for which address key definitions are retrieved. |
| **code** | **string** | path | **required** | The code of the document for which address key definitions are retrieved. |
| **source** | **string** | path | **required** | The source of the document for which address key definitions are retrieved. |
| **resultType** | **string** | path | **required** | The result type of the document for which address key definitions are retrieved. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime to query the document for which the address key definitions are retrieved.              Defaults to querying the latest version if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime to query the document for which the address key definitions are retrieved.              Defaults to querying the latest version if not specified. |

### Return type

[ResourceListOfAddressKeyDefinition](ResourceListOfAddressKeyDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of address key definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAddressKeyDefinitionsForDocumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAddressKeyDefinition> response = apiInstance.GetAddressKeyDefinitionsForDocumentWithHttpInfo(scope, code, source, resultType, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdatamap"></a>
## GetDataMap

> GetDataMapResponse GetDataMap(string scope, Dictionary<string, DataMapKey> requestBody)

GetDataMap: Get data map

Retrieve one or more structured result store address definition data maps from a particular scope.                Each data map can be identified by its invariant key, which can be thought of as a permanent URL.  For each ID, LUSID returns the most recently matched item.                In the request, each data map must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data map in the response.                The response returns three collections. The first contains successfully retrieved data maps. The second contains those with a  valid identifier but that could not be found. The third contains those that failed because LUSID could not construct a valid identifier from the request.                For the IDs that failed to resolve or could not be found, a reason is provided.                It is important to check the failed sets for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, DataMapKey>(); // Dictionary<string, DataMapKey>
GetDataMapResponse result = apiInstance.GetDataMap(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope from which to retrieve data maps. |
| **requestBody** | [Dictionary&lt;string, DataMapKey&gt;](DataMapKey.md) | body | **required** | The data map keys to look up, each keyed by a unique, ephemeral correlation ID. |

### Return type

[GetDataMapResponse](GetDataMapResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved data maps along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDataMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetDataMapResponse> response = apiInstance.GetDataMapWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getstructuredresultdata"></a>
## GetStructuredResultData

> GetStructuredResultDataResponse GetStructuredResultData(string scope, Dictionary<string, StructuredResultDataId> requestBody, DateTimeOffset? asAt = null, string? maxAge = null)

GetStructuredResultData: Get structured result data

Retrieve one or more structured result data items from a particular scope.                Each item can be identified by its time invariant structured result data identifier. For each ID, LUSID  returns the most recently matched item with respect to the provided (or default) effective datetime.                 An optional maximum age range window can be specified to control how far back to look from the specified  effective datetime. LUSID returns the most recent item within this window.                In the request, each data item must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data item in the response.    The response returns three collections. The first contains successfully retrieved data items. The second contains those with a  valid identifier but that could not be found. The third contains those that failed because LUSID could not construct a valid identifier from the request.    For the IDs that failed to resolve or could not be found, a reason is provided.                It is important to check the failed sets for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, StructuredResultDataId>(); // Dictionary<string, StructuredResultDataId>
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var maxAge = "maxAge_example";  // string? (optional)
GetStructuredResultDataResponse result = apiInstance.GetStructuredResultData(scope, requestBody, asAt, maxAge);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope from which to retrieve data items. |
| **requestBody** | [Dictionary&lt;string, StructuredResultDataId&gt;](StructuredResultDataId.md) | body | **required** | The time invariant set of structured data identifiers to retrieve, keyed by a unique, ephemeral correlation ID. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the structured result data. Defaults to returning the latest version if not specified. |
| **maxAge** | **string?** | query | optional | The duration of the look-back window in ISO8601 time interval format, for example &#39;P1Y2M3DT4H30M&#39; (1 year, 2 months, 3 days, 4 hours and 30 minutes).               This is subtracted from the provided effectiveAt datetime to generate a effective datetime window inside which a data item must exist to be retrieved. |

### Return type

[GetStructuredResultDataResponse](GetStructuredResultDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved data items along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetStructuredResultDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetStructuredResultDataResponse> response = apiInstance.GetStructuredResultDataWithHttpInfo(scope, requestBody, asAt, maxAge);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvirtualdocument"></a>
## GetVirtualDocument

> GetVirtualDocumentResponse GetVirtualDocument(string scope, Dictionary<string, StructuredResultDataId> requestBody, DateTimeOffset? asAt = null)

GetVirtualDocument: Get Virtual Documents

Retrieve one or more virtual documents from a particular scope.                Each item can be identified by its time invariant structured result data identifier. For each ID, LUSID  returns the most recently matched item with respect to the provided effective datetime.                In the request, each data item must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data item in the response.                The response returns two collections. The first contains successfully retrieved data items. The second contains those with a  valid identifier but that could not be found, or those that failed because LUSID could not construct a valid identifier from the request.                For the IDs that failed to resolve or could not be found, a reason is provided.                It is important to check the failed sets for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, StructuredResultDataId>(); // Dictionary<string, StructuredResultDataId>
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetVirtualDocumentResponse result = apiInstance.GetVirtualDocument(scope, requestBody, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to construct the virtual documents. |
| **requestBody** | [Dictionary&lt;string, StructuredResultDataId&gt;](StructuredResultDataId.md) | body | **required** | The time invariant set of structured data identifiers to retrieve, keyed by a unique, ephemeral correlation ID. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the structured result data. Defaults to returning the latest version if not specified. |

### Return type

[GetVirtualDocumentResponse](GetVirtualDocumentResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved virtual documents along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetVirtualDocumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetVirtualDocumentResponse> response = apiInstance.GetVirtualDocumentWithHttpInfo(scope, requestBody, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvirtualdocumentrows"></a>
## GetVirtualDocumentRows

> PagedResourceListOfVirtualRow GetVirtualDocumentRows(string scope, string code, string source, string resultType, DateTimeOrCutLabel effectiveAt, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

GetVirtualDocumentRows: Get Virtual Document Rows

Retrieve the rows of the virtual document with the specified identifiers and the given effectiveAt date time.    Get virtual document rows merges multiple StructuredResultData items upserted with UpsertStructuredResultData  for a single StructuredResultDataId.                Since an item of StructuredResultData is always upserted with a StructuredResultDataId, of which  effectiveAt is a part, then merging across the asAt dimension is supported but not merging across the  effectiveAt dimension.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var source = "source_example";  // string
var resultType = "resultType_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfVirtualRow result = apiInstance.GetVirtualDocumentRows(scope, code, source, resultType, effectiveAt, asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to retrieve the virtual document. |
| **code** | **string** | path | **required** | The code of the virtual document to retrieve. |
| **source** | **string** | path | **required** | The source of the virtual document to retrieve. |
| **resultType** | **string** | path | **required** | The result type of the virtual document to retrieve. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The effectiveAt datetime at which to retrieve the virtual document. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the virtual document. Defaults to returning the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing virtual document rows from a previous               call to list virtual document rows. This value is returned from the previous call. If a pagination token is               provided the filter, effectiveAt, and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:               https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfVirtualRow](PagedResourceListOfVirtualRow.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rows of the virtual document. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetVirtualDocumentRowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfVirtualRow> response = apiInstance.GetVirtualDocumentRowsWithHttpInfo(scope, code, source, resultType, effectiveAt, asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertresultvalue"></a>
## UpsertResultValue

> UpsertStructuredDataResponse UpsertResultValue(string scope, Dictionary<string, UpsertResultValuesDataRequest> requestBody)

UpsertResultValue: Upsert result value

Create or update one or more Upsert one or more result values in a particular scope. An item is updated if it already exists  and created if it does not.                In the request, each data item must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data item in the response.                The response returns both the collection of successfully created or updated data items, as well as those that failed.  For each failure, a reason is provided.                It is important to check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, UpsertResultValuesDataRequest>(); // Dictionary<string, UpsertResultValuesDataRequest>
UpsertStructuredDataResponse result = apiInstance.UpsertResultValue(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to construct the virtual documents. |
| **requestBody** | [Dictionary&lt;string, UpsertResultValuesDataRequest&gt;](UpsertResultValuesDataRequest.md) | body | **required** | The time invariant set of structured data identifiers to retrieve, keyed by a unique, ephemeral correlation ID. |

### Return type

[UpsertStructuredDataResponse](UpsertStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved virtual documents along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertResultValueWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertStructuredDataResponse> response = apiInstance.UpsertResultValueWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertstructuredresultdata"></a>
## UpsertStructuredResultData

> UpsertStructuredDataResponse UpsertStructuredResultData(string scope, Dictionary<string, UpsertStructuredResultDataRequest> requestBody)

UpsertStructuredResultData: Upsert structured result data

Create or update one or more structured result data items in a particular scope. An item is updated if it already exists  and created if it does not.                In the request, each data item must be keyed by a unique correlation ID. This ID is ephemeral and not stored by LUSID.  It serves only to easily identify each data item in the response.                The response returns both the collection of successfully created or updated data items, as well as those that failed.  For each failure, a reason is provided.                It is important to check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StructuredResultDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, UpsertStructuredResultDataRequest>(); // Dictionary<string, UpsertStructuredResultDataRequest>
UpsertStructuredDataResponse result = apiInstance.UpsertStructuredResultData(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create or update data items. |
| **requestBody** | [Dictionary&lt;string, UpsertStructuredResultDataRequest&gt;](UpsertStructuredResultDataRequest.md) | body | **required** | The set of data items to create or update, keyed by a unique, ephemeral correlation ID. |

### Return type

[UpsertStructuredDataResponse](UpsertStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully created or updated data items along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertStructuredResultDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertStructuredDataResponse> response = apiInstance.UpsertStructuredResultDataWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

