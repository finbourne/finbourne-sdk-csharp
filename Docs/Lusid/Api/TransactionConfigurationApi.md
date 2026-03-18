# Finbourne.Sdk.Lusid.Api.TransactionConfigurationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteSideDefinition**](#deletesidedefinition) | **DELETE** `/api/api/transactionconfiguration/sides/{side}/$delete` | DeleteSideDefinition: Delete the given side definition |
| [**DeleteTransactionType**](#deletetransactiontype) | **DELETE** `/api/api/transactionconfiguration/types/{source}/{type}` | DeleteTransactionType: Delete a transaction type |
| [**DeleteTransactionTypeSource**](#deletetransactiontypesource) | **DELETE** `/api/api/transactionconfiguration/types/{source}/$delete` | DeleteTransactionTypeSource: Delete all transaction types for the given source and scope |
| [**GetSideDefinition**](#getsidedefinition) | **GET** `/api/api/transactionconfiguration/sides/{side}` | GetSideDefinition: Get the side definition for a given side name( or label) |
| [**GetTransactionType**](#gettransactiontype) | **GET** `/api/api/transactionconfiguration/types/{source}/{type}` | GetTransactionType: Get a single transaction configuration type |
| [**ListSideDefinitions**](#listsidedefinitions) | **GET** `/api/api/transactionconfiguration/sides` | ListSideDefinitions: List the side definitions |
| [**ListTransactionTypes**](#listtransactiontypes) | **GET** `/api/api/transactionconfiguration/types` | ListTransactionTypes: List transaction types |
| [**SetSideDefinition**](#setsidedefinition) | **PUT** `/api/api/transactionconfiguration/sides/{side}` | SetSideDefinition: Set a side definition |
| [**SetSideDefinitions**](#setsidedefinitions) | **PUT** `/api/api/transactionconfiguration/sides` | SetSideDefinitions: Set the given side definitions |
| [**SetTransactionType**](#settransactiontype) | **PUT** `/api/api/transactionconfiguration/types/{source}/{type}` | SetTransactionType: Set a specific transaction type |
| [**SetTransactionTypeSource**](#settransactiontypesource) | **PUT** `/api/api/transactionconfiguration/types/{source}` | SetTransactionTypeSource: Set the transaction types for the given source and scope |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransactionConfigurationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
```

---

<a id="deletesidedefinition"></a>
## DeleteSideDefinition

> DeletedEntityResponse DeleteSideDefinition(string side, string? scope = null)

DeleteSideDefinition: Delete the given side definition

Delete the side which user specify in the request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var side = "side_example";  // string
var scope = "\"default\"";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteSideDefinition(side, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **side** | **string** | path | **required** | The label to uniquely identify the side. |
| **scope** | **string?** | query | optional | The scope in which the side exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

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
<summary>Using the DeleteSideDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteSideDefinitionWithHttpInfo(side, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransactiontype"></a>
## DeleteTransactionType

> DeletedEntityResponse DeleteTransactionType(string source, string type, string? scope = null)

DeleteTransactionType: Delete a transaction type

/// WARNING! Changing existing transaction types has a material impact on how data, new and old,  is processed and aggregated by LUSID, and will affect your whole organisation. Only call this API if you are fully aware of the implications of the change.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var source = "source_example";  // string
var type = "type_example";  // string
var scope = "\"default\"";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteTransactionType(source, type, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source that the type is in |
| **type** | **string** | path | **required** | One of the type&#39;s aliases |
| **scope** | **string?** | query | optional | The scope in which the transaction types exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

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
<summary>Using the DeleteTransactionTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransactionTypeWithHttpInfo(source, type, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransactiontypesource"></a>
## DeleteTransactionTypeSource

> DeletedEntityResponse DeleteTransactionTypeSource(string source, string? scope = null)

DeleteTransactionTypeSource: Delete all transaction types for the given source and scope

Delete all the types for the given source and scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var source = "source_example";  // string
var scope = "\"default\"";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteTransactionTypeSource(source, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source to set the transaction types for. |
| **scope** | **string?** | query | optional | The scope in which the transaction types exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

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
<summary>Using the DeleteTransactionTypeSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransactionTypeSourceWithHttpInfo(source, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsidedefinition"></a>
## GetSideDefinition

> SideDefinition GetSideDefinition(string side, string? scope = null, DateTimeOffset? asAt = null)

GetSideDefinition: Get the side definition for a given side name( or label)

Get the side definition user requested.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var side = "side_example";  // string
var scope = "\"default\"";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
SideDefinition result = apiInstance.GetSideDefinition(side, scope, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **side** | **string** | path | **required** | The label to uniquely identify the side. |
| **scope** | **string?** | query | optional | The scope in which the side exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction types. Defaults to returning the latest versions if not specified. |

### Return type

[SideDefinition](SideDefinition.md)

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
<summary>Using the GetSideDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SideDefinition> response = apiInstance.GetSideDefinitionWithHttpInfo(side, scope, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactiontype"></a>
## GetTransactionType

> TransactionType GetTransactionType(string source, string type, DateTimeOffset? asAt = null, string? scope = null)

GetTransactionType: Get a single transaction configuration type

Get a single transaction type. Returns failure if not found

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var source = "source_example";  // string
var type = "type_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var scope = "\"default\"";  // string? (optional)
TransactionType result = apiInstance.GetTransactionType(source, type, asAt, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source that the type is in |
| **type** | **string** | path | **required** | One of the type&#39;s aliases |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction configuration.              Defaults to returning the latest version of the transaction configuration type if not specified |
| **scope** | **string?** | query | optional | The scope in which the transaction types exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[TransactionType](TransactionType.md)

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
<summary>Using the GetTransactionTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionType> response = apiInstance.GetTransactionTypeWithHttpInfo(source, type, asAt, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listsidedefinitions"></a>
## ListSideDefinitions

> ResourceListOfSideDefinition ListSideDefinitions(DateTimeOffset? asAt = null, string? scope = null)

ListSideDefinitions: List the side definitions

List all the side definitions in the given scope

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var scope = "\"default\"";  // string? (optional)
ResourceListOfSideDefinition result = apiInstance.ListSideDefinitions(asAt, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction types. Defaults to returning the latest versions if not specified. |
| **scope** | **string?** | query | optional | The scope in which the side exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[ResourceListOfSideDefinition](ResourceListOfSideDefinition.md)

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
<summary>Using the ListSideDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfSideDefinition> response = apiInstance.ListSideDefinitionsWithHttpInfo(asAt, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransactiontypes"></a>
## ListTransactionTypes

> Dictionary&lt;string, List&lt;TransactionType&gt;&gt; ListTransactionTypes(DateTimeOffset? asAt = null, string? scope = null)

ListTransactionTypes: List transaction types

Get the list of current transaction types. For information on the default transaction types provided with  LUSID, see https://support.lusid.com/knowledgebase/article/KA-01873/.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var scope = "\"default\"";  // string? (optional)
Dictionary<string, List<TransactionType>> result = apiInstance.ListTransactionTypes(asAt, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction types. Defaults              to returning the latest versions if not specified. |
| **scope** | **string?** | query | optional | The scope in which the side exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

**Dictionary<string, List<TransactionType>>**

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
<summary>Using the ListTransactionTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<TransactionType>>> response = apiInstance.ListTransactionTypesWithHttpInfo(asAt, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setsidedefinition"></a>
## SetSideDefinition

> SideDefinition SetSideDefinition(string side, SideDefinitionRequest sideDefinitionRequest, string? scope = null)

SetSideDefinition: Set a side definition

Set a new side definition for use in a transaction type. For more information, see https://support.lusid.com/knowledgebase/article/KA-01875.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var side = "side_example";  // string
var sideDefinitionRequest = new SideDefinitionRequest(); // SideDefinitionRequest
var scope = "\"default\"";  // string? (optional)
SideDefinition result = apiInstance.SetSideDefinition(side, sideDefinitionRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **side** | **string** | path | **required** | The label to uniquely identify the side. |
| **sideDefinitionRequest** | [SideDefinitionRequest](SideDefinitionRequest.md) | body | **required** | The side definition to create or replace. |
| **scope** | **string?** | query | optional | The scope in which the side exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[SideDefinition](SideDefinition.md)

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
<summary>Using the SetSideDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SideDefinition> response = apiInstance.SetSideDefinitionWithHttpInfo(side, sideDefinitionRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setsidedefinitions"></a>
## SetSideDefinitions

> ResourceListOfSideDefinition SetSideDefinitions(List<SidesDefinitionRequest> sidesDefinitionRequest, string? scope = null)

SetSideDefinitions: Set the given side definitions

Set a new side definition for use in a transaction type. For more information, see https://support.lusid.com/knowledgebase/article/KA-01875.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var sidesDefinitionRequest = new List<SidesDefinitionRequest>(); // List<SidesDefinitionRequest>
var scope = "\"default\"";  // string? (optional)
ResourceListOfSideDefinition result = apiInstance.SetSideDefinitions(sidesDefinitionRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sidesDefinitionRequest** | [List&lt;SidesDefinitionRequest&gt;](SidesDefinitionRequest.md) | body | **required** | The list of side definitions to create, or replace. |
| **scope** | **string?** | query | optional | The scope in which the side exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[ResourceListOfSideDefinition](ResourceListOfSideDefinition.md)

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
<summary>Using the SetSideDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfSideDefinition> response = apiInstance.SetSideDefinitionsWithHttpInfo(sidesDefinitionRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="settransactiontype"></a>
## SetTransactionType

> TransactionType SetTransactionType(string source, string type, TransactionTypeRequest transactionTypeRequest, string? scope = null)

SetTransactionType: Set a specific transaction type

Set a transaction type for the given source and type. If the requested transaction type does not exist, it will be created    WARNING! Changing existing transaction types has a material impact on how data, new and old, is processed and aggregated by LUSID, and will affect your whole organisation. Only call this API if you are fully aware of the implications of the change.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var source = "source_example";  // string
var type = "type_example";  // string
var transactionTypeRequest = new TransactionTypeRequest(); // TransactionTypeRequest
var scope = "\"default\"";  // string? (optional)
TransactionType result = apiInstance.SetTransactionType(source, type, transactionTypeRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source to set the transaction configuration for |
| **type** | **string** | path | **required** | One of the transaction configuration alias types to uniquely identify the configuration. If this type does not exist, then a new transaction type is created using the body of the request in the given source, without including this type |
| **transactionTypeRequest** | [TransactionTypeRequest](TransactionTypeRequest.md) | body | **required** | The transaction configuration to set |
| **scope** | **string?** | query | optional | The scope in which the transaction types exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[TransactionType](TransactionType.md)

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
<summary>Using the SetTransactionTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionType> response = apiInstance.SetTransactionTypeWithHttpInfo(source, type, transactionTypeRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="settransactiontypesource"></a>
## SetTransactionTypeSource

> ResourceListOfTransactionType SetTransactionTypeSource(string source, List<TransactionTypeRequest> transactionTypeRequest, string? scope = null)

SetTransactionTypeSource: Set the transaction types for the given source and scope

The complete set of transaction types for the source.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionConfigurationApi>();
var source = "source_example";  // string
var transactionTypeRequest = new List<TransactionTypeRequest>(); // List<TransactionTypeRequest>
var scope = "\"default\"";  // string? (optional)
ResourceListOfTransactionType result = apiInstance.SetTransactionTypeSource(source, transactionTypeRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source to set the transaction types for. |
| **transactionTypeRequest** | [List&lt;TransactionTypeRequest&gt;](TransactionTypeRequest.md) | body | **required** | The set of transaction types. |
| **scope** | **string?** | query | optional | The scope in which the transaction types exists. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[ResourceListOfTransactionType](ResourceListOfTransactionType.md)

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
<summary>Using the SetTransactionTypeSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTransactionType> response = apiInstance.SetTransactionTypeSourceWithHttpInfo(source, transactionTypeRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

