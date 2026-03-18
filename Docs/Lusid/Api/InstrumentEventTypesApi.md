# Finbourne.Sdk.Lusid.Api.InstrumentEventTypesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTransactionTemplate**](#createtransactiontemplate) | **POST** `/api/api/instrumenteventtypes/{instrumentEventType}/transactiontemplates/{instrumentType}/{scope}` | CreateTransactionTemplate: Create Transaction Template |
| [**DeleteTransactionTemplate**](#deletetransactiontemplate) | **DELETE** `/api/api/instrumenteventtypes/{instrumentEventType}/transactiontemplates/{instrumentType}/{scope}` | DeleteTransactionTemplate: Delete Transaction Template |
| [**GetTransactionTemplate**](#gettransactiontemplate) | **GET** `/api/api/instrumenteventtypes/{instrumentEventType}/transactiontemplates/{instrumentType}/{scope}` | GetTransactionTemplate: Get Transaction Template |
| [**GetTransactionTemplateSpecification**](#gettransactiontemplatespecification) | **GET** `/api/api/instrumenteventtypes/{instrumentEventType}/transactiontemplatespecification` | GetTransactionTemplateSpecification: Get Transaction Template Specification. |
| [**ListTransactionTemplateSpecifications**](#listtransactiontemplatespecifications) | **GET** `/api/api/instrumenteventtypes/transactiontemplatespecifications` | ListTransactionTemplateSpecifications: List Transaction Template Specifications. |
| [**ListTransactionTemplates**](#listtransactiontemplates) | **GET** `/api/api/instrumenteventtypes/transactiontemplates` | ListTransactionTemplates: List Transaction Templates |
| [**UpdateTransactionTemplate**](#updatetransactiontemplate) | **PUT** `/api/api/instrumenteventtypes/{instrumentEventType}/transactiontemplates/{instrumentType}/{scope}` | UpdateTransactionTemplate: Update Transaction Template |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<InstrumentEventTypesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
```

---

<a id="createtransactiontemplate"></a>
## CreateTransactionTemplate

> TransactionTemplate CreateTransactionTemplate(string instrumentEventType, string instrumentType, string scope, TransactionTemplateRequest transactionTemplateRequest)

CreateTransactionTemplate: Create Transaction Template

Create a transaction template for a particular instrument event type in a scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var instrumentEventType = "instrumentEventType_example";  // string
var instrumentType = "instrumentType_example";  // string
var scope = "scope_example";  // string
var transactionTemplateRequest = new TransactionTemplateRequest(); // TransactionTemplateRequest
TransactionTemplate result = apiInstance.CreateTransactionTemplate(instrumentEventType, instrumentType, scope, transactionTemplateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentEventType** | **string** | path | **required** | The type of instrument events that the template is applied to. |
| **instrumentType** | **string** | path | **required** | The instrument type of the transaction template. The combination of the instrument              event type, instrument type and scope uniquely identifies a transaction template |
| **scope** | **string** | path | **required** | The scope in which the template lies. |
| **transactionTemplateRequest** | [TransactionTemplateRequest](TransactionTemplateRequest.md) | body | **required** | A request defining a new transaction template to be created. |

### Return type

[TransactionTemplate](TransactionTemplate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The response of the transaction template that was created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTransactionTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionTemplate> response = apiInstance.CreateTransactionTemplateWithHttpInfo(instrumentEventType, instrumentType, scope, transactionTemplateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransactiontemplate"></a>
## DeleteTransactionTemplate

> DateTimeOffset DeleteTransactionTemplate(string instrumentEventType, string instrumentType, string scope)

DeleteTransactionTemplate: Delete Transaction Template

Delete a transaction template for a particular instrument event type in a scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var instrumentEventType = "instrumentEventType_example";  // string
var instrumentType = "instrumentType_example";  // string
var scope = "scope_example";  // string
DateTimeOffset result = apiInstance.DeleteTransactionTemplate(instrumentEventType, instrumentType, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentEventType** | **string** | path | **required** | The type of instrument events that the template is applied to. |
| **instrumentType** | **string** | path | **required** | The instrument type of the transaction template. The combination of the instrument              event type, instrument type and scope uniquely identifies a transaction template |
| **scope** | **string** | path | **required** | The scope of the template. |

### Return type

**DateTimeOffset**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The AsAt Time the Template was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTransactionTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DateTimeOffset> response = apiInstance.DeleteTransactionTemplateWithHttpInfo(instrumentEventType, instrumentType, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactiontemplate"></a>
## GetTransactionTemplate

> TransactionTemplate GetTransactionTemplate(string instrumentEventType, string instrumentType, string scope, DateTimeOffset? asAt = null)

GetTransactionTemplate: Get Transaction Template

Gets the Transaction Template that for the instrument event type within the scope specified.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var instrumentEventType = "instrumentEventType_example";  // string
var instrumentType = "instrumentType_example";  // string
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TransactionTemplate result = apiInstance.GetTransactionTemplate(instrumentEventType, instrumentType, scope, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentEventType** | **string** | path | **required** | The instrument event type of the transaction template |
| **instrumentType** | **string** | path | **required** | The instrument type of the transaction template. The combination of the instrument              event type, instrument type and scope uniquely identifies a transaction template |
| **scope** | **string** | path | **required** | The scope in which the template lies. When not supplied the scope is &#39;default&#39;. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt time of the requested Transaction Template |

### Return type

[TransactionTemplate](TransactionTemplate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The transaction template. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionTemplate> response = apiInstance.GetTransactionTemplateWithHttpInfo(instrumentEventType, instrumentType, scope, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactiontemplatespecification"></a>
## GetTransactionTemplateSpecification

> TransactionTemplateSpecification GetTransactionTemplateSpecification(string instrumentEventType)

GetTransactionTemplateSpecification: Get Transaction Template Specification.

Retrieve the transaction template specification for a particular event type.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var instrumentEventType = "instrumentEventType_example";  // string
TransactionTemplateSpecification result = apiInstance.GetTransactionTemplateSpecification(instrumentEventType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentEventType** | **string** | path | **required** | The requested instrument event type. |

### Return type

[TransactionTemplateSpecification](TransactionTemplateSpecification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Transaction Template Specification. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionTemplateSpecificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionTemplateSpecification> response = apiInstance.GetTransactionTemplateSpecificationWithHttpInfo(instrumentEventType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransactiontemplatespecifications"></a>
## ListTransactionTemplateSpecifications

> PagedResourceListOfTransactionTemplateSpecification ListTransactionTemplateSpecifications(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

ListTransactionTemplateSpecifications: List Transaction Template Specifications.

Retrieves all transaction template specifications.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfTransactionTemplateSpecification result = apiInstance.ListTransactionTemplateSpecifications(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | AsAt of the request |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Transaction Template Specifications from              a previous call to list Transaction Template Specifications.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt              fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfTransactionTemplateSpecification](PagedResourceListOfTransactionTemplateSpecification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Transaction Template Specifications. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTransactionTemplateSpecificationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTransactionTemplateSpecification> response = apiInstance.ListTransactionTemplateSpecificationsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransactiontemplates"></a>
## ListTransactionTemplates

> PagedResourceListOfTransactionTemplate ListTransactionTemplates(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

ListTransactionTemplates: List Transaction Templates

Lists all Transaction Templates.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfTransactionTemplate result = apiInstance.ListTransactionTemplates(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt time at which to retrieve the Transaction Templates |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Transaction Templates from a previous call to list Transaction Templates.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, limit, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfTransactionTemplate](PagedResourceListOfTransactionTemplate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The transaction templates. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTransactionTemplatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTransactionTemplate> response = apiInstance.ListTransactionTemplatesWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetransactiontemplate"></a>
## UpdateTransactionTemplate

> TransactionTemplate UpdateTransactionTemplate(string instrumentEventType, string instrumentType, string scope, TransactionTemplateRequest transactionTemplateRequest)

UpdateTransactionTemplate: Update Transaction Template

Update a transaction template for a particular instrument event type in a scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventTypesApi>();
var instrumentEventType = "instrumentEventType_example";  // string
var instrumentType = "instrumentType_example";  // string
var scope = "scope_example";  // string
var transactionTemplateRequest = new TransactionTemplateRequest(); // TransactionTemplateRequest
TransactionTemplate result = apiInstance.UpdateTransactionTemplate(instrumentEventType, instrumentType, scope, transactionTemplateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentEventType** | **string** | path | **required** | The type of instrument events that the template is applied to. |
| **instrumentType** | **string** | path | **required** | The instrument type of the transaction template. The combination of the instrument              event type, instrument type and scope uniquely identifies a transaction template |
| **scope** | **string** | path | **required** | The scope in which the template lies. |
| **transactionTemplateRequest** | [TransactionTemplateRequest](TransactionTemplateRequest.md) | body | **required** | A request defining the updated values for the transaction template. |

### Return type

[TransactionTemplate](TransactionTemplate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response of the transaction template that was updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTransactionTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionTemplate> response = apiInstance.UpdateTransactionTemplateWithHttpInfo(instrumentEventType, instrumentType, scope, transactionTemplateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

