# Finbourne.Sdk.Configuration.Api.ConfigurationSetsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddConfigurationToSet**](#addconfigurationtoset) | **POST** `/configuration/api/sets/{type}/{scope}/{code}/items` | [EARLY ACCESS] AddConfigurationToSet: Add a configuration item to an existing set |
| [**CheckAccessTokenExists**](#checkaccesstokenexists) | **HEAD** `/configuration/api/sets/personal/me` | [DEPRECATED] CheckAccessTokenExists: Check the Personal Access Token exists for the current user |
| [**CreateConfigurationSet**](#createconfigurationset) | **POST** `/configuration/api/sets` | [EARLY ACCESS] CreateConfigurationSet: Create a configuration set |
| [**DeleteAccessToken**](#deleteaccesstoken) | **DELETE** `/configuration/api/sets/personal/me` | [DEPRECATED] DeleteAccessToken: Delete any stored Personal Access Token for the current user |
| [**DeleteConfigurationItem**](#deleteconfigurationitem) | **DELETE** `/configuration/api/sets/{type}/{scope}/{code}/items/{key}` | [EARLY ACCESS] DeleteConfigurationItem: Remove the specified configuration item from the specified configuration set |
| [**DeleteConfigurationSet**](#deleteconfigurationset) | **DELETE** `/configuration/api/sets/{type}/{scope}/{code}` | [EARLY ACCESS] DeleteConfigurationSet: Deletes a configuration set along with all their configuration items |
| [**GenerateAccessToken**](#generateaccesstoken) | **PUT** `/configuration/api/sets/personal/me` | [DEPRECATED] GenerateAccessToken: Generate a Personal Access Token for the current user and stores it in the me token |
| [**GetConfigurationItem**](#getconfigurationitem) | **GET** `/configuration/api/sets/{type}/{scope}/{code}/items/{key}` | GetConfigurationItem: Get the specific configuration item within an existing set |
| [**GetConfigurationSet**](#getconfigurationset) | **GET** `/configuration/api/sets/{type}/{scope}/{code}` | GetConfigurationSet: Get a configuration set, including all the associated metadata. By default secrets will not be revealed |
| [**GetSystemConfigurationItems**](#getsystemconfigurationitems) | **GET** `/configuration/api/sets/system/{code}/items/{key}` | [EARLY ACCESS] GetSystemConfigurationItems: Get the specific system configuration items within a system set All users have access to this endpoint |
| [**GetSystemConfigurationSets**](#getsystemconfigurationsets) | **GET** `/configuration/api/sets/system/{code}` | GetSystemConfigurationSets: Get the specified system configuration sets, including all their associated metadata. By default secrets will not be revealed All users have access to this endpoint |
| [**ListConfigurationSets**](#listconfigurationsets) | **GET** `/configuration/api/sets` | [EARLY ACCESS] ListConfigurationSets: List all configuration sets summaries (I.e. list of scope/code combinations available) |
| [**UpdateConfigurationItem**](#updateconfigurationitem) | **PUT** `/configuration/api/sets/{type}/{scope}/{code}/items/{key}` | [EARLY ACCESS] UpdateConfigurationItem: Update a configuration item&#39;s value and/or description |
| [**UpdateConfigurationSet**](#updateconfigurationset) | **PUT** `/configuration/api/sets/{type}/{scope}/{code}` | [EARLY ACCESS] UpdateConfigurationSet: Update the description of a configuration set |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Configuration.Api;
using Finbourne.Sdk.Configuration.Client;
using Finbourne.Sdk.Configuration.Extensions;
using Finbourne.Sdk.Services.Configuration.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ConfigurationSetsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
```

---

<a id="addconfigurationtoset"></a>
## AddConfigurationToSet

> ConfigurationSet AddConfigurationToSet(string type, string scope, string code, CreateConfigurationItem createConfigurationItem, string? userId = null)

[EARLY ACCESS] AddConfigurationToSet: Add a configuration item to an existing set

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var createConfigurationItem = new CreateConfigurationItem(); // CreateConfigurationItem
var userId = "userId_example";  // string? (optional)
ConfigurationSet result = apiInstance.AddConfigurationToSet(type, scope, code, createConfigurationItem, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **createConfigurationItem** | [CreateConfigurationItem](CreateConfigurationItem.md) | body | **required** | The data to create a configuration item |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ConfigurationSet](ConfigurationSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration set exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddConfigurationToSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationSet> response = apiInstance.AddConfigurationToSetWithHttpInfo(type, scope, code, createConfigurationItem, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="checkaccesstokenexists"></a>
## CheckAccessTokenExists

> void CheckAccessTokenExists()

[DEPRECATED] CheckAccessTokenExists: Check the Personal Access Token exists for the current user

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
apiInstance.CheckAccessTokenExists();
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Personal Access Token exists |  -  |
| **404** | The Personal Access Token does not exist |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CheckAccessTokenExistsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.CheckAccessTokenExistsWithHttpInfo();
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createconfigurationset"></a>
## CreateConfigurationSet

> ConfigurationSet CreateConfigurationSet(CreateConfigurationSet createConfigurationSet, string? userId = null)

[EARLY ACCESS] CreateConfigurationSet: Create a configuration set

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var createConfigurationSet = new CreateConfigurationSet(); // CreateConfigurationSet
var userId = "userId_example";  // string? (optional)
ConfigurationSet result = apiInstance.CreateConfigurationSet(createConfigurationSet, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createConfigurationSet** | [CreateConfigurationSet](CreateConfigurationSet.md) | body | **required** | The data to create a configuration set |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ConfigurationSet](ConfigurationSet.md)

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
<summary>Using the CreateConfigurationSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationSet> response = apiInstance.CreateConfigurationSetWithHttpInfo(createConfigurationSet, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteaccesstoken"></a>
## DeleteAccessToken

> void DeleteAccessToken()

[DEPRECATED] DeleteAccessToken: Delete any stored Personal Access Token for the current user

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
apiInstance.DeleteAccessToken();
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteAccessTokenWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteAccessTokenWithHttpInfo();
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteconfigurationitem"></a>
## DeleteConfigurationItem

> void DeleteConfigurationItem(string type, string scope, string code, string key, string? userId = null)

[EARLY ACCESS] DeleteConfigurationItem: Remove the specified configuration item from the specified configuration set

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var key = "key_example";  // string
var userId = "userId_example";  // string? (optional)
apiInstance.DeleteConfigurationItem(type, scope, code, key, userId);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **key** | **string** | path | **required** | The key that identifies a configuration item |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration item exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteConfigurationItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteConfigurationItemWithHttpInfo(type, scope, code, key, userId);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteconfigurationset"></a>
## DeleteConfigurationSet

> void DeleteConfigurationSet(string type, string scope, string code, string? userId = null)

[EARLY ACCESS] DeleteConfigurationSet: Deletes a configuration set along with all their configuration items

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var userId = "userId_example";  // string? (optional)
apiInstance.DeleteConfigurationSet(type, scope, code, userId);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration set exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteConfigurationSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteConfigurationSetWithHttpInfo(type, scope, code, userId);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="generateaccesstoken"></a>
## GenerateAccessToken

> PersonalAccessToken GenerateAccessToken(string? action = null)

[DEPRECATED] GenerateAccessToken: Generate a Personal Access Token for the current user and stores it in the me token

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var action = "action_example";  // string? (optional)
PersonalAccessToken result = apiInstance.GenerateAccessToken(action);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **action** | **string?** | query | optional | action&#x3D;regenerate &#x3D; Even if an existing parameter exists, forcibly regenerate a new one (deleting the old) action&#x3D;ensure &#x3D; If no parameter exists, create one. If one does already exist, verify that it is still valid (call a service?), and if so, return it. If it is not still valid, then regenerate a new one. action&#x3D;default &#x3D; If a parameter exists, return it. If not then create one. If this parameter is not provided, this is the default behaviour. |

### Return type

[PersonalAccessToken](PersonalAccessToken.md)

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
<summary>Using the GenerateAccessTokenWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PersonalAccessToken> response = apiInstance.GenerateAccessTokenWithHttpInfo(action);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getconfigurationitem"></a>
## GetConfigurationItem

> ConfigurationItem GetConfigurationItem(string type, string scope, string code, string key, bool? reveal = null, string? userId = null)

GetConfigurationItem: Get the specific configuration item within an existing set

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var key = "key_example";  // string
var reveal = true;  // bool? (optional)
var userId = "userId_example";  // string? (optional)
ConfigurationItem result = apiInstance.GetConfigurationItem(type, scope, code, key, reveal, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **key** | **string** | path | **required** | The key that identifies a configuration item |
| **reveal** | **bool?** | query | optional | Whether to reveal the secrets. This is only available when the userId query setting has not been specified. |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ConfigurationItem](ConfigurationItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration item exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetConfigurationItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationItem> response = apiInstance.GetConfigurationItemWithHttpInfo(type, scope, code, key, reveal, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getconfigurationset"></a>
## GetConfigurationSet

> ConfigurationSet GetConfigurationSet(string type, string scope, string code, bool? reveal = null, string? userId = null)

GetConfigurationSet: Get a configuration set, including all the associated metadata. By default secrets will not be revealed

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var reveal = true;  // bool? (optional)
var userId = "userId_example";  // string? (optional)
ConfigurationSet result = apiInstance.GetConfigurationSet(type, scope, code, reveal, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **reveal** | **bool?** | query | optional | Whether to reveal the secrets. This is only available when the userId query setting has not been specified. |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ConfigurationSet](ConfigurationSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration set exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetConfigurationSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationSet> response = apiInstance.GetConfigurationSetWithHttpInfo(type, scope, code, reveal, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsystemconfigurationitems"></a>
## GetSystemConfigurationItems

> ResourceListOfConfigurationItem GetSystemConfigurationItems(string code, string key, bool? reveal = null)

[EARLY ACCESS] GetSystemConfigurationItems: Get the specific system configuration items within a system set All users have access to this endpoint

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var code = "code_example";  // string
var key = "key_example";  // string
var reveal = true;  // bool? (optional)
ResourceListOfConfigurationItem result = apiInstance.GetSystemConfigurationItems(code, key, reveal);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code that identifies a system configuration set |
| **key** | **string** | path | **required** | The key that identifies a system configuration item |
| **reveal** | **bool?** | query | optional | Whether to reveal the secrets |

### Return type

[ResourceListOfConfigurationItem](ResourceListOfConfigurationItem.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No system configuration item exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSystemConfigurationItemsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfConfigurationItem> response = apiInstance.GetSystemConfigurationItemsWithHttpInfo(code, key, reveal);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsystemconfigurationsets"></a>
## GetSystemConfigurationSets

> ResourceListOfConfigurationSet GetSystemConfigurationSets(string code, bool? reveal = null)

GetSystemConfigurationSets: Get the specified system configuration sets, including all their associated metadata. By default secrets will not be revealed All users have access to this endpoint

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var code = "code_example";  // string
var reveal = true;  // bool? (optional)
ResourceListOfConfigurationSet result = apiInstance.GetSystemConfigurationSets(code, reveal);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code that identifies a system configuration set |
| **reveal** | **bool?** | query | optional | Whether to reveal the secrets |

### Return type

[ResourceListOfConfigurationSet](ResourceListOfConfigurationSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No system configuration set exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSystemConfigurationSetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfConfigurationSet> response = apiInstance.GetSystemConfigurationSetsWithHttpInfo(code, reveal);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listconfigurationsets"></a>
## ListConfigurationSets

> ResourceListOfConfigurationSetSummary ListConfigurationSets(string? type = null, string? userId = null)

[EARLY ACCESS] ListConfigurationSets: List all configuration sets summaries (I.e. list of scope/code combinations available)

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string? (optional)
var userId = "userId_example";  // string? (optional)
ResourceListOfConfigurationSetSummary result = apiInstance.ListConfigurationSets(type, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string?** | query | optional | Whether the configuration set is Personal or Shared |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ResourceListOfConfigurationSetSummary](ResourceListOfConfigurationSetSummary.md)

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
<summary>Using the ListConfigurationSetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfConfigurationSetSummary> response = apiInstance.ListConfigurationSetsWithHttpInfo(type, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateconfigurationitem"></a>
## UpdateConfigurationItem

> ConfigurationItem UpdateConfigurationItem(string type, string scope, string code, string key, UpdateConfigurationItem updateConfigurationItem, string? userId = null)

[EARLY ACCESS] UpdateConfigurationItem: Update a configuration item's value and/or description

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var key = "key_example";  // string
var updateConfigurationItem = new UpdateConfigurationItem(); // UpdateConfigurationItem
var userId = "userId_example";  // string? (optional)
ConfigurationItem result = apiInstance.UpdateConfigurationItem(type, scope, code, key, updateConfigurationItem, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **key** | **string** | path | **required** | The key that identifies a configuration item |
| **updateConfigurationItem** | [UpdateConfigurationItem](UpdateConfigurationItem.md) | body | **required** | The data to update a configuration item |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ConfigurationItem](ConfigurationItem.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration item exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateConfigurationItemWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationItem> response = apiInstance.UpdateConfigurationItemWithHttpInfo(type, scope, code, key, updateConfigurationItem, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateconfigurationset"></a>
## UpdateConfigurationSet

> ConfigurationSet UpdateConfigurationSet(string type, string scope, string code, UpdateConfigurationSet updateConfigurationSet, string? userId = null)

[EARLY ACCESS] UpdateConfigurationSet: Update the description of a configuration set

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationSetsApi>();
var type = "type_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateConfigurationSet = new UpdateConfigurationSet(); // UpdateConfigurationSet
var userId = "userId_example";  // string? (optional)
ConfigurationSet result = apiInstance.UpdateConfigurationSet(type, scope, code, updateConfigurationSet, userId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | **string** | path | **required** | Whether the configuration set is Personal or Shared |
| **scope** | **string** | path | **required** | The scope that identifies a configuration set |
| **code** | **string** | path | **required** | The code that identifies a configuration set |
| **updateConfigurationSet** | [UpdateConfigurationSet](UpdateConfigurationSet.md) | body | **required** | The data to update a configuration set |
| **userId** | **string?** | query | optional | Feature that allows Administrators to administer personal settings  (but never reveal the value of secrets) of a specific user. |

### Return type

[ConfigurationSet](ConfigurationSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No configuration set exists with the provided identifiers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateConfigurationSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationSet> response = apiInstance.UpdateConfigurationSetWithHttpInfo(type, scope, code, updateConfigurationSet, userId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

