# Finbourne.Sdk.Horizon.Api.VersionedConfigurationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateVersionedConfigurationDraft**](#createversionedconfigurationdraft) | **POST** `/horizon/api/versionedconfiguration/{configType}/{name}/draft` | [EXPERIMENTAL] CreateVersionedConfigurationDraft: Create a draft versioned configuration. |
| [**GetVersionedConfiguration**](#getversionedconfiguration) | **GET** `/horizon/api/versionedconfiguration/{configType}/{name}` | [EXPERIMENTAL] GetVersionedConfiguration: Get a versioned configuration. |
| [**ListVersionedConfigurations**](#listversionedconfigurations) | **GET** `/horizon/api/versionedconfiguration/{configType}` | [EXPERIMENTAL] ListVersionedConfigurations: List versioned configurations. |
| [**LockVersionedConfigurationVersion**](#lockversionedconfigurationversion) | **POST** `/horizon/api/versionedconfiguration/{configType}/{name}/{majorVersion}/{minorVersion}/lock` | [EXPERIMENTAL] LockVersionedConfigurationVersion: Lock a versioned configuration version. |
| [**UpdateVersionedConfigurationDraft**](#updateversionedconfigurationdraft) | **PUT** `/horizon/api/versionedconfiguration/{configType}/{name}/{majorVersion}/{minorVersion}/draft` | [EXPERIMENTAL] UpdateVersionedConfigurationDraft: Update a draft versioned configuration. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<VersionedConfigurationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VersionedConfigurationsApi>();
```

---

<a id="createversionedconfigurationdraft"></a>
## CreateVersionedConfigurationDraft

> VersionedConfigurationResponse CreateVersionedConfigurationDraft(string configType, string name, CreateVersionedConfigurationDraftRequest? createVersionedConfigurationDraftRequest = null)

[EXPERIMENTAL] CreateVersionedConfigurationDraft: Create a draft versioned configuration.

Creates a new draft configuration record. Configurations follow a draft/locked lifecycle: create a draft here, refine it with the update endpoint, then commit it with the lock endpoint. If both majorVersion and minorVersion are omitted in the request body, the next version is assigned automatically by incrementing the minor version of the current highest version (starting at 1.0 if none exists). The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VersionedConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var createVersionedConfigurationDraftRequest = new CreateVersionedConfigurationDraftRequest?(); // CreateVersionedConfigurationDraftRequest? (optional)
VersionedConfigurationResponse result = apiInstance.CreateVersionedConfigurationDraft(configType, name, createVersionedConfigurationDraftRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration. |
| **name** | **string** | path | **required** | The logical name of the configuration. |
| **createVersionedConfigurationDraftRequest** | [CreateVersionedConfigurationDraftRequest?](CreateVersionedConfigurationDraftRequest?.md) | body | optional | Options for the new draft, including optional explicit version and source version. |

### Return type

[VersionedConfigurationResponse](VersionedConfigurationResponse.md)

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
<summary>Using the CreateVersionedConfigurationDraftWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedConfigurationResponse> response = apiInstance.CreateVersionedConfigurationDraftWithHttpInfo(configType, name, createVersionedConfigurationDraftRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getversionedconfiguration"></a>
## GetVersionedConfiguration

> VersionedConfigurationResponse GetVersionedConfiguration(string configType, string name, int? majorVersion = null, int? minorVersion = null)

[EXPERIMENTAL] GetVersionedConfiguration: Get a versioned configuration.

Returns a specific configuration record. When both majorVersion and minorVersion are omitted, the highest available version is returned. Both must be supplied together or both omitted. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VersionedConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var majorVersion = 56;  // int? (optional)
var minorVersion = 56;  // int? (optional)
VersionedConfigurationResponse result = apiInstance.GetVersionedConfiguration(configType, name, majorVersion, minorVersion);
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

[VersionedConfigurationResponse](VersionedConfigurationResponse.md)

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
<summary>Using the GetVersionedConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedConfigurationResponse> response = apiInstance.GetVersionedConfigurationWithHttpInfo(configType, name, majorVersion, minorVersion);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listversionedconfigurations"></a>
## ListVersionedConfigurations

> List&lt;VersionedConfigurationResponse&gt; ListVersionedConfigurations(string configType)

[EXPERIMENTAL] ListVersionedConfigurations: List versioned configurations.

Returns all configuration records for the given config type, across all versions and states (both draft and locked), ordered by version descending. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VersionedConfigurationsApi>();
var configType = "configType_example";  // string
List<VersionedConfigurationResponse> result = apiInstance.ListVersionedConfigurations(configType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration to list. |

### Return type

[List&lt;VersionedConfigurationResponse&gt;](VersionedConfigurationResponse.md)

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
<summary>Using the ListVersionedConfigurationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<VersionedConfigurationResponse>> response = apiInstance.ListVersionedConfigurationsWithHttpInfo(configType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="lockversionedconfigurationversion"></a>
## LockVersionedConfigurationVersion

> VersionedConfigurationResponse LockVersionedConfigurationVersion(string configType, string name, int majorVersion, int minorVersion)

[EXPERIMENTAL] LockVersionedConfigurationVersion: Lock a versioned configuration version.

Locks a draft configuration version, making it immutable and ready for use. Once locked, a version cannot be edited or unlocked. All versions are retained permanently. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VersionedConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var majorVersion = 56;  // int
var minorVersion = 56;  // int
VersionedConfigurationResponse result = apiInstance.LockVersionedConfigurationVersion(configType, name, majorVersion, minorVersion);
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

[VersionedConfigurationResponse](VersionedConfigurationResponse.md)

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
<summary>Using the LockVersionedConfigurationVersionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedConfigurationResponse> response = apiInstance.LockVersionedConfigurationVersionWithHttpInfo(configType, name, majorVersion, minorVersion);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateversionedconfigurationdraft"></a>
## UpdateVersionedConfigurationDraft

> VersionedConfigurationResponse UpdateVersionedConfigurationDraft(string configType, string name, int majorVersion, int minorVersion, UpdateVersionedConfigurationDraftRequest? updateVersionedConfigurationDraftRequest = null)

[EXPERIMENTAL] UpdateVersionedConfigurationDraft: Update a draft versioned configuration.

Updates the value of an existing draft configuration. Only draft versions can be updated; locked versions are immutable. This endpoint can be called multiple times before locking. The user must be authenticated and entitled to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VersionedConfigurationsApi>();
var configType = "configType_example";  // string
var name = "name_example";  // string
var majorVersion = 56;  // int
var minorVersion = 56;  // int
var updateVersionedConfigurationDraftRequest = new UpdateVersionedConfigurationDraftRequest?(); // UpdateVersionedConfigurationDraftRequest? (optional)
VersionedConfigurationResponse result = apiInstance.UpdateVersionedConfigurationDraft(configType, name, majorVersion, minorVersion, updateVersionedConfigurationDraftRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **configType** | **string** | path | **required** | The category of configuration. |
| **name** | **string** | path | **required** | The logical name of the configuration. |
| **majorVersion** | **int** | path | **required** | The major version of the draft to update. |
| **minorVersion** | **int** | path | **required** | The minor version of the draft to update. |
| **updateVersionedConfigurationDraftRequest** | [UpdateVersionedConfigurationDraftRequest?](UpdateVersionedConfigurationDraftRequest?.md) | body | optional | The updated value. |

### Return type

[VersionedConfigurationResponse](VersionedConfigurationResponse.md)

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
<summary>Using the UpdateVersionedConfigurationDraftWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedConfigurationResponse> response = apiInstance.UpdateVersionedConfigurationDraftWithHttpInfo(configType, name, majorVersion, minorVersion, updateVersionedConfigurationDraftRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

