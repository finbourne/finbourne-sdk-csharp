# Finbourne.Sdk.Lusid.Api.TransactionFeeTypesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTransactionFeeType**](#createtransactionfeetype) | **POST** `/api/api/transactions/transactionfeetypes/{scope}/{code}` | [EXPERIMENTAL] CreateTransactionFeeType: Create a transaction fee type |
| [**DeleteTransactionFeeType**](#deletetransactionfeetype) | **DELETE** `/api/api/transactions/transactionfeetypes/{scope}/{code}` | [EXPERIMENTAL] DeleteTransactionFeeType: Delete a transaction fee type |
| [**GetTransactionFeeType**](#gettransactionfeetype) | **GET** `/api/api/transactions/transactionfeetypes/{scope}/{code}` | [EXPERIMENTAL] GetTransactionFeeType: Get a transaction fee type |
| [**ListTransactionFeeTypes**](#listtransactionfeetypes) | **GET** `/api/api/transactions/transactionfeetypes` | [EXPERIMENTAL] ListTransactionFeeTypes: List transaction fee types |
| [**UpdateTransactionFeeType**](#updatetransactionfeetype) | **PUT** `/api/api/transactions/transactionfeetypes/{scope}/{code}` | [EXPERIMENTAL] UpdateTransactionFeeType: Update a transaction fee type |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransactionFeeTypesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeeTypesApi>();
```

---

<a id="createtransactionfeetype"></a>
## CreateTransactionFeeType

> TransactionFeeType CreateTransactionFeeType(string scope, string code, CreateTransactionFeeTypeRequest createTransactionFeeTypeRequest)

[EXPERIMENTAL] CreateTransactionFeeType: Create a transaction fee type

Create a transaction fee type for the specified scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createTransactionFeeTypeRequest = new CreateTransactionFeeTypeRequest(); // CreateTransactionFeeTypeRequest
TransactionFeeType result = apiInstance.CreateTransactionFeeType(scope, code, createTransactionFeeTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction fee type. |
| **code** | **string** | path | **required** | The code of the transaction fee type.              Together with the scope this uniquely identifies the transaction fee type. |
| **createTransactionFeeTypeRequest** | [CreateTransactionFeeTypeRequest](CreateTransactionFeeTypeRequest.md) | body | **required** | The contents of the transaction fee type. |

### Return type

[TransactionFeeType](TransactionFeeType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created transaction fee type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTransactionFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionFeeType> response = apiInstance.CreateTransactionFeeTypeWithHttpInfo(scope, code, createTransactionFeeTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransactionfeetype"></a>
## DeleteTransactionFeeType

> DeletedEntityResponse DeleteTransactionFeeType(string scope, string code)

[EXPERIMENTAL] DeleteTransactionFeeType: Delete a transaction fee type

Delete a transaction fee type for the specified scope and code. To note, this will be a monotemporal delete, meaning that  the transaction fee type will be deleted for all effective time (including past and future versions of the transaction fee type).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTransactionFeeType(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction fee type. |
| **code** | **string** | path | **required** | The code of the specified transaction fee type.              Together with the scope this uniquely identifies the transaction fee type. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delete a transaction fee type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTransactionFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransactionFeeTypeWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionfeetype"></a>
## GetTransactionFeeType

> TransactionFeeType GetTransactionFeeType(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetTransactionFeeType: Get a transaction fee type

Get the transaction fee type for the specified scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
TransactionFeeType result = apiInstance.GetTransactionFeeType(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction fee type. |
| **code** | **string** | path | **required** | The code of the transaction fee type.              Together with the scope this uniquely identifies the transaction fee type. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to retrieve the transaction fee type properties.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction fee types.              Defaults to latest if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | The collection of &#x60;PropertyKey&#x60;s that we want to decorate on the transaction fee type. |

### Return type

[TransactionFeeType](TransactionFeeType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The transaction fee type matching the specified scope and code. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionFeeType> response = apiInstance.GetTransactionFeeTypeWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransactionfeetypes"></a>
## ListTransactionFeeTypes

> ResourceListOfTransactionFeeType ListTransactionFeeTypes(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListTransactionFeeTypes: List transaction fee types

List transaction fee types that match the specified criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeeTypesApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ResourceListOfTransactionFeeType result = apiInstance.ListTransactionFeeTypes(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to retrieve transaction fee type properties.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction fee types.              Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transaction fee types from a previous call to list transaction fee types.  This value is returned from the previous call. If a pagination token is provided the filter,  sortBy, effectiveAt and asAt field must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Scope, use \&quot;scope eq &#39;ExampleScope&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | The collection of &#x60;PropertyKey&#x60;s to filter on |

### Return type

[ResourceListOfTransactionFeeType](ResourceListOfTransactionFeeType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of transaction fee types matching the specified criteria. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTransactionFeeTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTransactionFeeType> response = apiInstance.ListTransactionFeeTypesWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetransactionfeetype"></a>
## UpdateTransactionFeeType

> TransactionFeeType UpdateTransactionFeeType(string scope, string code, UpdateTransactionFeeTypeRequest updateTransactionFeeTypeRequest)

[EXPERIMENTAL] UpdateTransactionFeeType: Update a transaction fee type

Update a transaction fee type by providing the new contents of the transaction fee type.  The displayName field cannot be updated.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeeTypesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateTransactionFeeTypeRequest = new UpdateTransactionFeeTypeRequest(); // UpdateTransactionFeeTypeRequest
TransactionFeeType result = apiInstance.UpdateTransactionFeeType(scope, code, updateTransactionFeeTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction fee type. |
| **code** | **string** | path | **required** | The code of the specified transaction fee type.              Together with the scope this uniquely identifies the transaction fee type. |
| **updateTransactionFeeTypeRequest** | [UpdateTransactionFeeTypeRequest](UpdateTransactionFeeTypeRequest.md) | body | **required** | The updated contents of the transaction fee type. |

### Return type

[TransactionFeeType](TransactionFeeType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated transaction fee type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTransactionFeeTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionFeeType> response = apiInstance.UpdateTransactionFeeTypeWithHttpInfo(scope, code, updateTransactionFeeTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

