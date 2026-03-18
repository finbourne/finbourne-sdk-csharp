# Finbourne.Sdk.Lusid.Api.SystemConfigurationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateConfigurationTransactionType**](#createconfigurationtransactiontype) | **POST** `/api/api/systemconfiguration/transactions/type` | [EARLY ACCESS] CreateConfigurationTransactionType: Create transaction type |
| [**CreateSideDefinition**](#createsidedefinition) | **POST** `/api/api/systemconfiguration/transactions/side` | [EXPERIMENTAL] CreateSideDefinition: Create side definition |
| [**DeleteTransactionConfigurationSource**](#deletetransactionconfigurationsource) | **DELETE** `/api/api/systemconfiguration/transactions/type/{source}` | [EXPERIMENTAL] DeleteTransactionConfigurationSource: Delete all transaction configurations for a source |
| [**GetTransactionConfigurationSource**](#gettransactionconfigurationsource) | **GET** `/api/api/systemconfiguration/transactions/type/{source}` | [EXPERIMENTAL] GetTransactionConfigurationSource: Get all transaction configurations for a source |
| [**ListConfigurationTransactionTypes**](#listconfigurationtransactiontypes) | **GET** `/api/api/systemconfiguration/transactions` | [EARLY ACCESS] ListConfigurationTransactionTypes: List transaction types |
| [**SetConfigurationTransactionTypes**](#setconfigurationtransactiontypes) | **PUT** `/api/api/systemconfiguration/transactions` | [EXPERIMENTAL] SetConfigurationTransactionTypes: Set transaction types |
| [**SetTransactionConfigurationSource**](#settransactionconfigurationsource) | **PUT** `/api/api/systemconfiguration/transactions/type/{source}` | [EXPERIMENTAL] SetTransactionConfigurationSource: Set transaction types for a source |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SystemConfigurationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
```

---

<a id="createconfigurationtransactiontype"></a>
## CreateConfigurationTransactionType

> TransactionSetConfigurationData CreateConfigurationTransactionType(TransactionConfigurationDataRequest? transactionConfigurationDataRequest = null)

[EARLY ACCESS] CreateConfigurationTransactionType: Create transaction type

Create a new transaction type by specifying a definition and mappings to movements.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var transactionConfigurationDataRequest = new TransactionConfigurationDataRequest?(); // TransactionConfigurationDataRequest? (optional)
TransactionSetConfigurationData result = apiInstance.CreateConfigurationTransactionType(transactionConfigurationDataRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **transactionConfigurationDataRequest** | [TransactionConfigurationDataRequest?](TransactionConfigurationDataRequest?.md) | body | optional | A transaction type definition. |

### Return type

[TransactionSetConfigurationData](TransactionSetConfigurationData.md)

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
<summary>Using the CreateConfigurationTransactionTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSetConfigurationData> response = apiInstance.CreateConfigurationTransactionTypeWithHttpInfo(transactionConfigurationDataRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createsidedefinition"></a>
## CreateSideDefinition

> TransactionSetConfigurationData CreateSideDefinition(SideConfigurationDataRequest? sideConfigurationDataRequest = null)

[EXPERIMENTAL] CreateSideDefinition: Create side definition

Create a new side definition for use in a transaction type. For more information, see https://support.lusid.com/knowledgebase/article/KA-01875.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var sideConfigurationDataRequest = new SideConfigurationDataRequest?(); // SideConfigurationDataRequest? (optional)
TransactionSetConfigurationData result = apiInstance.CreateSideDefinition(sideConfigurationDataRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sideConfigurationDataRequest** | [SideConfigurationDataRequest?](SideConfigurationDataRequest?.md) | body | optional | The definition of the side. |

### Return type

[TransactionSetConfigurationData](TransactionSetConfigurationData.md)

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
<summary>Using the CreateSideDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSetConfigurationData> response = apiInstance.CreateSideDefinitionWithHttpInfo(sideConfigurationDataRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransactionconfigurationsource"></a>
## DeleteTransactionConfigurationSource

> DeletedEntityResponse DeleteTransactionConfigurationSource(string source)

[EXPERIMENTAL] DeleteTransactionConfigurationSource: Delete all transaction configurations for a source

/// WARNING! Changing existing transaction types has a material impact on how data, new and old,  is processed and aggregated by LUSID, and will affect your whole organisation. Only call this API if you are fully aware of the implications of the change.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var source = "source_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTransactionConfigurationSource(source);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source to delete transaction configurations for |

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
<summary>Using the DeleteTransactionConfigurationSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransactionConfigurationSourceWithHttpInfo(source);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionconfigurationsource"></a>
## GetTransactionConfigurationSource

> TransactionSetConfigurationData GetTransactionConfigurationSource(string source, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetTransactionConfigurationSource: Get all transaction configurations for a source

Returns failure if requested source is not found

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var source = "source_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TransactionSetConfigurationData result = apiInstance.GetTransactionConfigurationSource(source, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source for which to retrieve transaction configurations |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction configurations.              Defaults to returning the latest version of the transaction configurations if not specified. |

### Return type

[TransactionSetConfigurationData](TransactionSetConfigurationData.md)

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
<summary>Using the GetTransactionConfigurationSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSetConfigurationData> response = apiInstance.GetTransactionConfigurationSourceWithHttpInfo(source, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listconfigurationtransactiontypes"></a>
## ListConfigurationTransactionTypes

> TransactionSetConfigurationData ListConfigurationTransactionTypes(DateTimeOffset? asAt = null)

[EARLY ACCESS] ListConfigurationTransactionTypes: List transaction types

Get the list of current transaction types. For information on the default transaction types provided with  LUSID, see https://support.lusid.com/knowledgebase/article/KA-01873/.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TransactionSetConfigurationData result = apiInstance.ListConfigurationTransactionTypes(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transaction types. Defaults              to returning the latest versions if not specified. |

### Return type

[TransactionSetConfigurationData](TransactionSetConfigurationData.md)

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
<summary>Using the ListConfigurationTransactionTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSetConfigurationData> response = apiInstance.ListConfigurationTransactionTypesWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setconfigurationtransactiontypes"></a>
## SetConfigurationTransactionTypes

> TransactionSetConfigurationData SetConfigurationTransactionTypes(TransactionSetConfigurationDataRequest? transactionSetConfigurationDataRequest = null)

[EXPERIMENTAL] SetConfigurationTransactionTypes: Set transaction types

Configure all existing transaction types. Note it is not possible to configure a single existing transaction type on its own.                WARNING! Changing existing transaction types has a material impact on how data, new and old, is processed and aggregated by LUSID, and will affect your whole organisation. Only call this API if you are fully aware of the implications of the change.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var transactionSetConfigurationDataRequest = new TransactionSetConfigurationDataRequest?(); // TransactionSetConfigurationDataRequest? (optional)
TransactionSetConfigurationData result = apiInstance.SetConfigurationTransactionTypes(transactionSetConfigurationDataRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **transactionSetConfigurationDataRequest** | [TransactionSetConfigurationDataRequest?](TransactionSetConfigurationDataRequest?.md) | body | optional | The complete set of transaction type definitions. |

### Return type

[TransactionSetConfigurationData](TransactionSetConfigurationData.md)

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
<summary>Using the SetConfigurationTransactionTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSetConfigurationData> response = apiInstance.SetConfigurationTransactionTypesWithHttpInfo(transactionSetConfigurationDataRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="settransactionconfigurationsource"></a>
## SetTransactionConfigurationSource

> TransactionSetConfigurationData SetTransactionConfigurationSource(string source, List<SetTransactionConfigurationSourceRequest> setTransactionConfigurationSourceRequest)

[EXPERIMENTAL] SetTransactionConfigurationSource: Set transaction types for a source

This will replace all the existing transaction configurations for the given source                WARNING! Changing existing transaction types has a material impact on how data, new and old, is processed and aggregated by LUSID, and will affect your whole organisation. Only call this API if you are fully aware of the implications of the change.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SystemConfigurationApi>();
var source = "source_example";  // string
var setTransactionConfigurationSourceRequest = new List<SetTransactionConfigurationSourceRequest>(); // List<SetTransactionConfigurationSourceRequest>
TransactionSetConfigurationData result = apiInstance.SetTransactionConfigurationSource(source, setTransactionConfigurationSourceRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **source** | **string** | path | **required** | The source to set the transaction configurations for |
| **setTransactionConfigurationSourceRequest** | [List&lt;SetTransactionConfigurationSourceRequest&gt;](SetTransactionConfigurationSourceRequest.md) | body | **required** | The set of transaction configurations |

### Return type

[TransactionSetConfigurationData](TransactionSetConfigurationData.md)

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
<summary>Using the SetTransactionConfigurationSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSetConfigurationData> response = apiInstance.SetTransactionConfigurationSourceWithHttpInfo(source, setTransactionConfigurationSourceRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

