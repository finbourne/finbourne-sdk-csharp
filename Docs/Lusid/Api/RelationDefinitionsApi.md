# Finbourne.Sdk.Lusid.Api.RelationDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateRelationDefinition**](#createrelationdefinition) | **POST** `/api/api/relationdefinitions` | [EXPERIMENTAL] CreateRelationDefinition: Create a relation definition |
| [**DeleteRelationDefinition**](#deleterelationdefinition) | **DELETE** `/api/api/relationdefinitions/{scope}/{code}` | [EXPERIMENTAL] DeleteRelationDefinition: Delete relation definition |
| [**GetRelationDefinition**](#getrelationdefinition) | **GET** `/api/api/relationdefinitions/{scope}/{code}` | [EXPERIMENTAL] GetRelationDefinition: Get relation definition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RelationDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationDefinitionsApi>();
```

---

<a id="createrelationdefinition"></a>
## CreateRelationDefinition

> RelationDefinition CreateRelationDefinition(CreateRelationDefinitionRequest createRelationDefinitionRequest)

[EXPERIMENTAL] CreateRelationDefinition: Create a relation definition

Define a new relation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationDefinitionsApi>();
var createRelationDefinitionRequest = new CreateRelationDefinitionRequest(); // CreateRelationDefinitionRequest
RelationDefinition result = apiInstance.CreateRelationDefinition(createRelationDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createRelationDefinitionRequest** | [CreateRelationDefinitionRequest](CreateRelationDefinitionRequest.md) | body | **required** | The definition of the new relation. |

### Return type

[RelationDefinition](RelationDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created relation definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRelationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationDefinition> response = apiInstance.CreateRelationDefinitionWithHttpInfo(createRelationDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterelationdefinition"></a>
## DeleteRelationDefinition

> DeletedEntityResponse DeleteRelationDefinition(string scope, string code)

[EXPERIMENTAL] DeleteRelationDefinition: Delete relation definition

Delete the definition of the specified relation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteRelationDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relation to be deleted. |
| **code** | **string** | path | **required** | The code of the relation to be deleted. Together with the domain and scope this uniquely              identifies the relation. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time that the relation definition was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRelationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteRelationDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrelationdefinition"></a>
## GetRelationDefinition

> RelationDefinition GetRelationDefinition(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetRelationDefinition: Get relation definition

Retrieve the definition of a specified relation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
RelationDefinition result = apiInstance.GetRelationDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified relation. |
| **code** | **string** | path | **required** | The code of the specified relation. Together with the domain and scope this uniquely              identifies the relation. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the relation definition. Defaults to return              the latest version of the definition if not specified. |

### Return type

[RelationDefinition](RelationDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested relation definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRelationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationDefinition> response = apiInstance.GetRelationDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

