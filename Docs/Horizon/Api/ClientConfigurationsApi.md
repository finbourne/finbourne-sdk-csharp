# Finbourne.Sdk.Horizon.Api.ClientConfigurationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateClientConfigurationDraft**](#createclientconfigurationdraft) | **POST** `/horizon/api/clientconfiguration/{configType}/{name}/draft` | [EXPERIMENTAL] CreateClientConfigurationDraft: Create a draft client configuration. |
| [**GetClientConfiguration**](#getclientconfiguration) | **GET** `/horizon/api/clientconfiguration/{configType}/{name}` | [EXPERIMENTAL] GetClientConfiguration: Get a client configuration. |
| [**ListClientConfigurations**](#listclientconfigurations) | **GET** `/horizon/api/clientconfiguration/{configType}` | [EXPERIMENTAL] ListClientConfigurations: List client configurations. |
| [**LockClientConfigurationVersion**](#lockclientconfigurationversion) | **POST** `/horizon/api/clientconfiguration/{configType}/{name}/{majorVersion}/{minorVersion}/lock` | [EXPERIMENTAL] LockClientConfigurationVersion: Lock a client configuration version. |
| [**UpdateClientConfigurationDraft**](#updateclientconfigurationdraft) | **PUT** `/horizon/api/clientconfiguration/{configType}/{name}/{majorVersion}/{minorVersion}/draft` | [EXPERIMENTAL] UpdateClientConfigurationDraft: Update a draft client configuration. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ClientConfigurationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ClientConfigurationsApi>();
```

---

<a id="createclientconfigurationdraft"></a>
## CreateClientConfigurationDraft

> ClientConfigurationResponse CreateClientConfigurationDraft(string configType, string name, CreateClientConfigurationDraftRequest? createClientConfigurationDraftRequest = null)

[EXPERIMENTAL] CreateClientConfigurationDraft: Create a draft client configuration.

Creates a new draft configuration record. Configurations follow a draft/locked lifecycle: create a draft here, refine it with the update endpoint, then commit it with the lock endpoint. If both majorVersion and minorVersion are omitted in the request body, the next version is assigned automatically by incrementing the minor version of the current highest version (starting at 1.0 if none exists). The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ClientConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var createClientConfigurationDraftRequest = new CreateClientConfigurationDraftRequest?(); // CreateClientConfigurationDraftRequest? (optional)
ClientConfigurationResponse result = apiInstance.CreateClientConfigurationDraft(configType, name, createClientConfigurationDraftRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration. |
| **name** | **string** | path | **required** | The logical name of the configuration. |
| **createClientConfigurationDraftRequest** | [CreateClientConfigurationDraftRequest?](CreateClientConfigurationDraftRequest?.md) | body | optional | Options for the new draft, including optional explicit version and source version. |

### Return type

[ClientConfigurationResponse](ClientConfigurationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The client does not exist. |  -  |
| **409** | A configuration with the specified version already exists. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateClientConfigurationDraftWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClientConfigurationResponse> response = apiInstance.CreateClientConfigurationDraftWithHttpInfo(configType, name, createClientConfigurationDraftRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getclientconfiguration"></a>
## GetClientConfiguration

> ClientConfigurationResponse GetClientConfiguration(string configType, string name, int? majorVersion = null, int? minorVersion = null)

[EXPERIMENTAL] GetClientConfiguration: Get a client configuration.

Returns a specific configuration record. When both majorVersion and minorVersion are omitted, the highest available version is returned. Both must be supplied together or both omitted. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ClientConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var majorVersion = 56;  // int? (optional)
var minorVersion = 56;  // int? (optional)
ClientConfigurationResponse result = apiInstance.GetClientConfiguration(configType, name, majorVersion, minorVersion);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration. |
| **name** | **string** | path | **required** | The logical name of the configuration. |
| **majorVersion** | **int?** | query | optional | The major version to retrieve. Must be supplied together with minorVersion, or both omitted. |
| **minorVersion** | **int?** | query | optional | The minor version to retrieve. Must be supplied together with majorVersion, or both omitted. |

### Return type

[ClientConfigurationResponse](ClientConfigurationResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The client or configuration does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetClientConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClientConfigurationResponse> response = apiInstance.GetClientConfigurationWithHttpInfo(configType, name, majorVersion, minorVersion);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listclientconfigurations"></a>
## ListClientConfigurations

> List&lt;ClientConfigurationResponse&gt; ListClientConfigurations(string configType)

[EXPERIMENTAL] ListClientConfigurations: List client configurations.

Returns all configuration records for the given config type, across all versions and states (both draft and locked), ordered by version descending. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ClientConfigurationsApi>();
var configType = "configType_example";  // string
List<ClientConfigurationResponse> result = apiInstance.ListClientConfigurations(configType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration to list. |

### Return type

[List&lt;ClientConfigurationResponse&gt;](ClientConfigurationResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The client does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListClientConfigurationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<ClientConfigurationResponse>> response = apiInstance.ListClientConfigurationsWithHttpInfo(configType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="lockclientconfigurationversion"></a>
## LockClientConfigurationVersion

> ClientConfigurationResponse LockClientConfigurationVersion(string configType, string name, int majorVersion, int minorVersion)

[EXPERIMENTAL] LockClientConfigurationVersion: Lock a client configuration version.

Locks a draft configuration version, making it immutable and ready for use. Once locked, a version cannot be edited or unlocked. All versions are retained permanently. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ClientConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var majorVersion = 56;  // int
var minorVersion = 56;  // int
ClientConfigurationResponse result = apiInstance.LockClientConfigurationVersion(configType, name, majorVersion, minorVersion);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration. |
| **name** | **string** | path | **required** | The logical name of the configuration. |
| **majorVersion** | **int** | path | **required** | The major version to lock. |
| **minorVersion** | **int** | path | **required** | The minor version to lock. |

### Return type

[ClientConfigurationResponse](ClientConfigurationResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The client or configuration version does not exist, or the version is already locked. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the LockClientConfigurationVersionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClientConfigurationResponse> response = apiInstance.LockClientConfigurationVersionWithHttpInfo(configType, name, majorVersion, minorVersion);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateclientconfigurationdraft"></a>
## UpdateClientConfigurationDraft

> ClientConfigurationResponse UpdateClientConfigurationDraft(string configType, string name, int majorVersion, int minorVersion, UpdateClientConfigurationDraftRequest? updateClientConfigurationDraftRequest = null)

[EXPERIMENTAL] UpdateClientConfigurationDraft: Update a draft client configuration.

Updates the value of an existing draft configuration. Only draft versions can be updated; locked versions are immutable. This endpoint can be called multiple times before locking. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ClientConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var majorVersion = 56;  // int
var minorVersion = 56;  // int
var updateClientConfigurationDraftRequest = new UpdateClientConfigurationDraftRequest?(); // UpdateClientConfigurationDraftRequest? (optional)
ClientConfigurationResponse result = apiInstance.UpdateClientConfigurationDraft(configType, name, majorVersion, minorVersion, updateClientConfigurationDraftRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration. |
| **name** | **string** | path | **required** | The logical name of the configuration. |
| **majorVersion** | **int** | path | **required** | The major version of the draft to update. |
| **minorVersion** | **int** | path | **required** | The minor version of the draft to update. |
| **updateClientConfigurationDraftRequest** | [UpdateClientConfigurationDraftRequest?](UpdateClientConfigurationDraftRequest?.md) | body | optional | The updated value. |

### Return type

[ClientConfigurationResponse](ClientConfigurationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The client or configuration version does not exist, or the version is already locked. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateClientConfigurationDraftWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClientConfigurationResponse> response = apiInstance.UpdateClientConfigurationDraftWithHttpInfo(configType, name, majorVersion, minorVersion, updateClientConfigurationDraftRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

