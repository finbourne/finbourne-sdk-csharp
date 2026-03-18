# Finbourne.Sdk.Lusid.Api.DataTypesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDataType**](#createdatatype) | **POST** `/api/api/datatypes` | [EARLY ACCESS] CreateDataType: Create data type definition |
| [**DeleteDataType**](#deletedatatype) | **DELETE** `/api/api/datatypes/{scope}/{code}` | DeleteDataType: Delete a data type definition. |
| [**GetDataType**](#getdatatype) | **GET** `/api/api/datatypes/{scope}/{code}` | GetDataType: Get data type definition |
| [**GetUnitsFromDataType**](#getunitsfromdatatype) | **GET** `/api/api/datatypes/{scope}/{code}/units` | [EARLY ACCESS] GetUnitsFromDataType: Get units from data type |
| [**ListDataTypeSummaries**](#listdatatypesummaries) | **GET** `/api/api/datatypes` | [EARLY ACCESS] ListDataTypeSummaries: List all data type summaries, without the reference data |
| [**ListDataTypes**](#listdatatypes) | **GET** `/api/api/datatypes/{scope}` | ListDataTypes: List data types |
| [**UpdateDataType**](#updatedatatype) | **PUT** `/api/api/datatypes/{scope}/{code}` | [EARLY ACCESS] UpdateDataType: Update data type definition |
| [**UpdateReferenceData**](#updatereferencedata) | **PUT** `/api/api/datatypes/{scope}/{code}/referencedata` | [EARLY ACCESS] UpdateReferenceData: Update all reference data on a data type, includes the reference values, the field definitions, field values |
| [**UpdateReferenceValues**](#updatereferencevalues) | **PUT** `/api/api/datatypes/{scope}/{code}/referencedatavalues` | [EARLY ACCESS] UpdateReferenceValues: Update reference data on a data type |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<DataTypesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
```

---

<a id="createdatatype"></a>
## CreateDataType

> DataType CreateDataType(CreateDataTypeRequest? createDataTypeRequest = null)

[EARLY ACCESS] CreateDataType: Create data type definition

Create a new data type definition    Data types cannot be created in either the \"default\" or \"system\" scopes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var createDataTypeRequest = new CreateDataTypeRequest?(); // CreateDataTypeRequest? (optional)
DataType result = apiInstance.CreateDataType(createDataTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createDataTypeRequest** | [CreateDataTypeRequest?](CreateDataTypeRequest?.md) | body | optional | The definition of the new data type |

### Return type

[DataType](DataType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateDataTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DataType> response = apiInstance.CreateDataTypeWithHttpInfo(createDataTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletedatatype"></a>
## DeleteDataType

> DeletedEntityResponse DeleteDataType(string scope, string code)

DeleteDataType: Delete a data type definition.

Delete an existing data type definition.    Data types cannot be deleted in either the \"default\" or \"system\" scopes, scopes beginning with \"LUSID-\",  or data types that are in use on a property definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteDataType(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the data type |
| **code** | **string** | path | **required** | The code of the data type |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

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
<summary>Using the DeleteDataTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteDataTypeWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdatatype"></a>
## GetDataType

> DataType GetDataType(string scope, string code, DateTimeOffset? asAt = null)

GetDataType: Get data type definition

Get the definition of a specified data type

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DataType result = apiInstance.GetDataType(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the data type |
| **code** | **string** | path | **required** | The code of the data type |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the data type definition. Defaults to              return the latest version of the instrument definition if not specified. |

### Return type

[DataType](DataType.md)

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
<summary>Using the GetDataTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DataType> response = apiInstance.GetDataTypeWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getunitsfromdatatype"></a>
## GetUnitsFromDataType

> ResourceListOfIUnitDefinitionDto GetUnitsFromDataType(string scope, string code, List<string>? units = null, string? filter = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetUnitsFromDataType: Get units from data type

Get the definitions of the specified units associated bound to a specific data type

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var units = new List<string>?(); // List<string>? (optional)
var filter = "filter_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfIUnitDefinitionDto result = apiInstance.GetUnitsFromDataType(scope, code, units, filter, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the data type |
| **code** | **string** | path | **required** | The code of the data type |
| **units** | [List&lt;string&gt;?](string.md) | query | optional | One or more unit identifiers for which the definition is being requested |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.               For example, to filter on the Schema, use \&quot;schema eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The as at of the requested data type |

### Return type

[ResourceListOfIUnitDefinitionDto](ResourceListOfIUnitDefinitionDto.md)

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
<summary>Using the GetUnitsFromDataTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfIUnitDefinitionDto> response = apiInstance.GetUnitsFromDataTypeWithHttpInfo(scope, code, units, filter, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listdatatypesummaries"></a>
## ListDataTypeSummaries

> PagedResourceListOfDataTypeSummary ListDataTypeSummaries(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EARLY ACCESS] ListDataTypeSummaries: List all data type summaries, without the reference data

List all data type summaries

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfDataTypeSummary result = apiInstance.ListDataTypeSummaries(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the data type summaries. Defaults to returning the latest version               of each summary if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing data type summaries. This  value is returned from the previous call. If a pagination token is provided, the filter, sortBy  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.                For example, to filter on the Scope, use \&quot;id.scope eq &#39;myscope&#39;\&quot;, to filter on Schema, use \&quot;schema eq &#39;string&#39;\&quot;,               to filter on AcceptableValues use \&quot;acceptableValues any (~ eq &#39;value&#39;)\&quot;               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfDataTypeSummary](PagedResourceListOfDataTypeSummary.md)

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
<summary>Using the ListDataTypeSummariesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfDataTypeSummary> response = apiInstance.ListDataTypeSummariesWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listdatatypes"></a>
## ListDataTypes

> ResourceListOfDataType ListDataTypes(string scope, DateTimeOffset? asAt = null, bool? includeSystem = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

ListDataTypes: List data types

List all data types in a specified scope

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var includeSystem = true;  // bool? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfDataType result = apiInstance.ListDataTypes(scope, asAt, includeSystem, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The requested scope of the data types |
| **asAt** | **DateTimeOffset?** | query | optional | The as at of the requested data types |
| **includeSystem** | **bool?** | query | optional | Whether to additionally include those data types in the \&quot;system\&quot; scope |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.              For example, to filter on the Display Name, use \&quot;displayName eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfDataType](ResourceListOfDataType.md)

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
<summary>Using the ListDataTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfDataType> response = apiInstance.ListDataTypesWithHttpInfo(scope, asAt, includeSystem, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatedatatype"></a>
## UpdateDataType

> DataType UpdateDataType(string scope, string code, UpdateDataTypeRequest updateDataTypeRequest)

[EARLY ACCESS] UpdateDataType: Update data type definition

Update the definition of the specified existing data type    Not all elements within a data type definition are modifiable due to the potential implications for data  already stored against the types

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateDataTypeRequest = new UpdateDataTypeRequest(); // UpdateDataTypeRequest
DataType result = apiInstance.UpdateDataType(scope, code, updateDataTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the data type |
| **code** | **string** | path | **required** | The code of the data type |
| **updateDataTypeRequest** | [UpdateDataTypeRequest](UpdateDataTypeRequest.md) | body | **required** | The updated definition of the data type |

### Return type

[DataType](DataType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateDataTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DataType> response = apiInstance.UpdateDataTypeWithHttpInfo(scope, code, updateDataTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatereferencedata"></a>
## UpdateReferenceData

> DataType UpdateReferenceData(string scope, string code, UpdateReferenceDataRequest updateReferenceDataRequest)

[EARLY ACCESS] UpdateReferenceData: Update all reference data on a data type, includes the reference values, the field definitions, field values

Replaces the whole set of reference data

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateReferenceDataRequest = new UpdateReferenceDataRequest(); // UpdateReferenceDataRequest
DataType result = apiInstance.UpdateReferenceData(scope, code, updateReferenceDataRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the data type |
| **code** | **string** | path | **required** | The code of the data type |
| **updateReferenceDataRequest** | [UpdateReferenceDataRequest](UpdateReferenceDataRequest.md) | body | **required** | The updated reference data |

### Return type

[DataType](DataType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateReferenceDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DataType> response = apiInstance.UpdateReferenceDataWithHttpInfo(scope, code, updateReferenceDataRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatereferencevalues"></a>
## UpdateReferenceValues

> DataType UpdateReferenceValues(string scope, string code, List<FieldValue> fieldValue)

[EARLY ACCESS] UpdateReferenceValues: Update reference data on a data type

Replaces the whole set of reference values

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DataTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fieldValue = new List<FieldValue>(); // List<FieldValue>
DataType result = apiInstance.UpdateReferenceValues(scope, code, fieldValue);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the data type |
| **code** | **string** | path | **required** | The code of the data type |
| **fieldValue** | [List&lt;FieldValue&gt;](FieldValue.md) | body | **required** | The updated reference values |

### Return type

[DataType](DataType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateReferenceValuesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DataType> response = apiInstance.UpdateReferenceValuesWithHttpInfo(scope, code, fieldValue);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

