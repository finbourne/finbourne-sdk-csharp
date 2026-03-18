# Finbourne.Sdk.Identity.Api.PersonalAuthenticationTokensApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateApiKey**](#createapikey) | **POST** `/identity/api/keys` | CreateApiKey: Create a Personal Access Token |
| [**DeleteApiKey**](#deleteapikey) | **DELETE** `/identity/api/keys/{id}` | DeleteApiKey: Invalidate a Personal Access Token |
| [**ListOwnApiKeys**](#listownapikeys) | **GET** `/identity/api/keys` | ListOwnApiKeys: Gets the meta data for all of the user&#39;s existing Personal Access Tokens. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Identity.Api;
using Finbourne.Sdk.Identity.Client;
using Finbourne.Sdk.Identity.Extensions;
using Finbourne.Sdk.Services.Identity.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PersonalAuthenticationTokensApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonalAuthenticationTokensApi>();
```

---

<a id="createapikey"></a>
## CreateApiKey

> CreatedApiKey CreateApiKey(CreateApiKey createApiKey)

CreateApiKey: Create a Personal Access Token

Generates a Personal Access Token and returns the new key and its associated metadata.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonalAuthenticationTokensApi>();
var createApiKey = new CreateApiKey(); // CreateApiKey
CreatedApiKey result = apiInstance.CreateApiKey(createApiKey);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createApiKey** | [CreateApiKey](CreateApiKey.md) | body | **required** | The request to create a new Personal Access Token |

### Return type

[CreatedApiKey](CreatedApiKey.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Personal Access Token and associated meta data. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateApiKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CreatedApiKey> response = apiInstance.CreateApiKeyWithHttpInfo(createApiKey);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteapikey"></a>
## DeleteApiKey

> ApiKey DeleteApiKey(string id)

DeleteApiKey: Invalidate a Personal Access Token

Immediately invalidates the specified Personal Access Token

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonalAuthenticationTokensApi>();
var id = "id_example";  // string
ApiKey result = apiInstance.DeleteApiKey(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The id of the Personal Access Token to delete |

### Return type

[ApiKey](ApiKey.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invalidates a Personal Access Token |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteApiKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ApiKey> response = apiInstance.DeleteApiKeyWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listownapikeys"></a>
## ListOwnApiKeys

> List&lt;ApiKey&gt; ListOwnApiKeys()

ListOwnApiKeys: Gets the meta data for all of the user's existing Personal Access Tokens.

Gets the meta data for all of the user's Personal Access Tokens that have not been deleted. They may be invalid due to the deactivation date having passed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonalAuthenticationTokensApi>();
List<ApiKey> result = apiInstance.ListOwnApiKeys();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;ApiKey&gt;](ApiKey.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of user&#39;s existing Personal Access Tokens |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListOwnApiKeysWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<ApiKey>> response = apiInstance.ListOwnApiKeysWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

