# Finbourne.Sdk.Lusid.Api.FeeTypesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateFeeType**](#createfeetype) | **POST** `/api/api/feetypes/{scope}` | [EXPERIMENTAL] CreateFeeType: Create a FeeType. |
| [**DeleteFeeType**](#deletefeetype) | **DELETE** `/api/api/feetypes/{scope}/{code}` | [EXPERIMENTAL] DeleteFeeType: Delete a FeeType. |
| [**GetFeeTemplateSpecifications**](#getfeetemplatespecifications) | **GET** `/api/api/feetypes/feetransactiontemplatespecification` | [EXPERIMENTAL] GetFeeTemplateSpecifications: Get FeeTemplateSpecifications used in the FeeType. |
| [**GetFeeType**](#getfeetype) | **GET** `/api/api/feetypes/{scope}/{code}` | [EXPERIMENTAL] GetFeeType: Get a FeeType |
| [**ListFeeTypes**](#listfeetypes) | **GET** `/api/api/feetypes` | [EXPERIMENTAL] ListFeeTypes: List FeeTypes |
| [**UpdateFeeType**](#updatefeetype) | **PUT** `/api/api/feetypes/{scope}/{code}` | [EXPERIMENTAL] UpdateFeeType: Update a FeeType. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FeeTypesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
```

---

<a id="createfeetype"></a>
## CreateFeeType

> FeeType CreateFeeType(string scope, FeeTypeRequest feeTypeRequest)

[EXPERIMENTAL] CreateFeeType: Create a FeeType.

Create a FeeType that contains templates used to create fee transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
var scope = "scope_example";  // string
var feeTypeRequest = new FeeTypeRequest(); // FeeTypeRequest
FeeType result = apiInstance.CreateFeeType(scope, feeTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FeeType. |
| **feeTypeRequest** | [FeeTypeRequest](FeeTypeRequest.md) | body | **required** | The contents of the FeeType. |

### Return type

[FeeType](FeeType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Create a FeeType. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeType> response = apiInstance.CreateFeeTypeWithHttpInfo(scope, feeTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletefeetype"></a>
## DeleteFeeType

> DeletedEntityResponse DeleteFeeType(string scope, string code)

[EXPERIMENTAL] DeleteFeeType: Delete a FeeType.

Delete a FeeType that contains templates used to create fee transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteFeeType(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FeeType. |
| **code** | **string** | path | **required** | The code of the fee type |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delete a FeeType. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteFeeTypeWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfeetemplatespecifications"></a>
## GetFeeTemplateSpecifications

> FeeTransactionTemplateSpecification GetFeeTemplateSpecifications()

[EXPERIMENTAL] GetFeeTemplateSpecifications: Get FeeTemplateSpecifications used in the FeeType.

Get FeeTemplateSpecifications used in the FeeType.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
FeeTransactionTemplateSpecification result = apiInstance.GetFeeTemplateSpecifications();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[FeeTransactionTemplateSpecification](FeeTransactionTemplateSpecification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Fee template specifications used with a FeeType. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFeeTemplateSpecificationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeTransactionTemplateSpecification> response = apiInstance.GetFeeTemplateSpecificationsWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfeetype"></a>
## GetFeeType

> FeeType GetFeeType(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetFeeType: Get a FeeType

Get a FeeType that contains templates used to create fee transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
FeeType result = apiInstance.GetFeeType(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FeeType |
| **code** | **string** | path | **required** | The code of the FeeType |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the FeeType. Defaults to returning the latest version of the FeeType, if not specified. |

### Return type

[FeeType](FeeType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested FeeType. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeType> response = apiInstance.GetFeeTypeWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfeetypes"></a>
## ListFeeTypes

> PagedResourceListOfFeeType ListFeeTypes(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListFeeTypes: List FeeTypes

List FeeTypes that contain templates used to create fee transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFeeType result = apiInstance.ListFeeTypes(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the FeeTypes. Defaults to returning the latest version of each FeeType if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing FeeTypes; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Code of the FeeType type, specify \&quot;id.Code eq &#39;FeeType1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfFeeType](PagedResourceListOfFeeType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fee Types |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFeeTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFeeType> response = apiInstance.ListFeeTypesWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatefeetype"></a>
## UpdateFeeType

> FeeType UpdateFeeType(string scope, string code, UpdateFeeTypeRequest updateFeeTypeRequest)

[EXPERIMENTAL] UpdateFeeType: Update a FeeType.

Update a FeeType that contains templates used to create fee transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateFeeTypeRequest = new UpdateFeeTypeRequest(); // UpdateFeeTypeRequest
FeeType result = apiInstance.UpdateFeeType(scope, code, updateFeeTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FeeType. |
| **code** | **string** | path | **required** | The code of the fee type |
| **updateFeeTypeRequest** | [UpdateFeeTypeRequest](UpdateFeeTypeRequest.md) | body | **required** | The contents of the FeeType. |

### Return type

[FeeType](FeeType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update a FeeType. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeType> response = apiInstance.UpdateFeeTypeWithHttpInfo(scope, code, updateFeeTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

