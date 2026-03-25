# Finbourne.Sdk.Lusid.Api.TransactionTransactionFeesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTransactionFee**](#createtransactionfee) | **POST** `/api/api/transactions/transactionfees/{scope}/{code}` | [EXPERIMENTAL] CreateTransactionFee: Create a TransactionFee |
| [**DeleteTransactionFee**](#deletetransactionfee) | **DELETE** `/api/api/transactions/transactionfees/{scope}/{code}` | [EXPERIMENTAL] DeleteTransactionFee: Delete a TransactionFee |
| [**GetTransactionFee**](#gettransactionfee) | **GET** `/api/api/transactions/transactionfees/{scope}/{code}` | [EXPERIMENTAL] GetTransactionFee: Get a TransactionFee |
| [**ListTransactionFees**](#listtransactionfees) | **GET** `/api/api/transactions/transactionfees` | [EXPERIMENTAL] ListTransactionFees: List TransactionFees |
| [**UpdateTransactionFee**](#updatetransactionfee) | **PUT** `/api/api/transactions/transactionfees/{scope}/{code}` | [EXPERIMENTAL] UpdateTransactionFee: Update a TransactionFee |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransactionTransactionFeesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionTransactionFeesApi>();
```

---

<a id="createtransactionfee"></a>
## CreateTransactionFee

> TransactionFee CreateTransactionFee(string scope, string code, CreateTransactionFeeRequest createTransactionFeeRequest)

[EXPERIMENTAL] CreateTransactionFee: Create a TransactionFee

Create a TransactionFee for the specified scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionTransactionFeesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createTransactionFeeRequest = new CreateTransactionFeeRequest(); // CreateTransactionFeeRequest
TransactionFee result = apiInstance.CreateTransactionFee(scope, code, createTransactionFeeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the TransactionFee. |
| **code** | **string** | path | **required** | The code of the TransactionFee.              Together with the scope this uniquely identifies the TransactionFee. |
| **createTransactionFeeRequest** | [CreateTransactionFeeRequest](CreateTransactionFeeRequest.md) | body | **required** | The contents of the TransactionFee. |

### Return type

[TransactionFee](TransactionFee.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created TransactionFee. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTransactionFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionFee> response = apiInstance.CreateTransactionFeeWithHttpInfo(scope, code, createTransactionFeeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransactionfee"></a>
## DeleteTransactionFee

> DeletedEntityResponse DeleteTransactionFee(string scope, string code)

[EXPERIMENTAL] DeleteTransactionFee: Delete a TransactionFee

Delete a TransactionFee for the specified scope and code. To note, this will be a monotemporal delete, meaning that  the TransactionFee will be deleted for all effective time (including past and future versions of the TransactionFee).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionTransactionFeesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTransactionFee(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the TransactionFee. |
| **code** | **string** | path | **required** | The code of the specified TransactionFee.              Together with the scope this uniquely identifies the TransactionFee. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delete a TransactionFee. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTransactionFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransactionFeeWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionfee"></a>
## GetTransactionFee

> TransactionFee GetTransactionFee(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetTransactionFee: Get a TransactionFee

Get the TransactionFee for the specified scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionTransactionFeesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
TransactionFee result = apiInstance.GetTransactionFee(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the TransactionFee. |
| **code** | **string** | path | **required** | The code of the TransactionFee.              Together with the scope this uniquely identifies the TransactionFee. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to retrieve the TransactionFee properties.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the TransactionFees.              Defaults to latest if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | The collection of &#x60;PropertyKey&#x60;s that we want to decorate on identifies the TransactionFee. |

### Return type

[TransactionFee](TransactionFee.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The TransactionFee matching the specified scope and code. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionFee> response = apiInstance.GetTransactionFeeWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransactionfees"></a>
## ListTransactionFees

> ResourceListOfTransactionFee ListTransactionFees(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListTransactionFees: List TransactionFees

List TransactionFees that match the specified criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionTransactionFeesApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ResourceListOfTransactionFee result = apiInstance.ListTransactionFees(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to retrieve TransactionFee properties.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the TransactionFees.              Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing TransactionFees from a previous call to list TransactionFees.  This value is returned from the previous call. If a pagination token is provided the filter,  sortBy, effectiveAt and asAt field must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Scope, use \&quot;scope eq &#39;ExampleScope&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | The collection of &#x60;PropertyKey&#x60;s to filter on |

### Return type

[ResourceListOfTransactionFee](ResourceListOfTransactionFee.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of TransactionFees matching the specified criteria. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTransactionFeesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTransactionFee> response = apiInstance.ListTransactionFeesWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetransactionfee"></a>
## UpdateTransactionFee

> TransactionFee UpdateTransactionFee(string scope, string code, UpdateTransactionFeeRequest updateTransactionFeeRequest)

[EXPERIMENTAL] UpdateTransactionFee: Update a TransactionFee

Update a TransactionFee by providing the new contents of the TransactionFee.  The name field and the capitalisation field can not be updated.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionTransactionFeesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateTransactionFeeRequest = new UpdateTransactionFeeRequest(); // UpdateTransactionFeeRequest
TransactionFee result = apiInstance.UpdateTransactionFee(scope, code, updateTransactionFeeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the TransactionFee. |
| **code** | **string** | path | **required** | The code of the specified TransactionFee.              Together with the scope this uniquely identifies the TransactionFee. |
| **updateTransactionFeeRequest** | [UpdateTransactionFeeRequest](UpdateTransactionFeeRequest.md) | body | **required** | The updated contents of the TransactionFee. |

### Return type

[TransactionFee](TransactionFee.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated TransactionFee. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTransactionFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionFee> response = apiInstance.UpdateTransactionFeeWithHttpInfo(scope, code, updateTransactionFeeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

