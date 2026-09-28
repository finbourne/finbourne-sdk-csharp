# Finbourne.Sdk.Lusid.Api.EntityResolversApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateEntityResolver**](#createentityresolver) | **POST** `/api/api/entityresolvers` | [EXPERIMENTAL] CreateEntityResolver: Create an Entity Resolver |
| [**DeleteEntityResolver**](#deleteentityresolver) | **DELETE** `/api/api/entityresolvers/{scope}/{code}` | [EXPERIMENTAL] DeleteEntityResolver: Delete an Entity Resolver |
| [**GetEntityResolver**](#getentityresolver) | **GET** `/api/api/entityresolvers/{scope}/{code}` | [EXPERIMENTAL] GetEntityResolver: Get a single Entity Resolver |
| [**UpdateEntityResolver**](#updateentityresolver) | **PUT** `/api/api/entityresolvers/{scope}/{code}` | [EXPERIMENTAL] UpdateEntityResolver: Update an Entity Resolver |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<EntityResolversApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntityResolversApi>();
```

---

<a id="createentityresolver"></a>
## CreateEntityResolver

> EntityResolver CreateEntityResolver(CreateEntityResolverRequest? createEntityResolverRequest = null)

[EXPERIMENTAL] CreateEntityResolver: Create an Entity Resolver

Define a new Entity Resolver. The resolver's identifier matching order is the sequence of identifier  property keys that will be tried, in turn, when resolving an entity of the given type in the resolver's scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntityResolversApi>();
var createEntityResolverRequest = new CreateEntityResolverRequest?(); // CreateEntityResolverRequest? (optional)
EntityResolver result = apiInstance.CreateEntityResolver(createEntityResolverRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createEntityResolverRequest** | [CreateEntityResolverRequest?](../Model/CreateEntityResolverRequest?.md) | body | optional | The request defining the new Entity Resolver |

### Return type

[EntityResolver](../Model/EntityResolver.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created Entity Resolver |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateEntityResolverWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EntityResolver> response = apiInstance.CreateEntityResolverWithHttpInfo(createEntityResolverRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteentityresolver"></a>
## DeleteEntityResolver

> DeletedEntityResponse DeleteEntityResolver(string scope, string code)

[EXPERIMENTAL] DeleteEntityResolver: Delete an Entity Resolver

The deletion will take effect from the deletion datetime, i.e. the Entity Resolver will no longer exist  at any asAt datetime after the asAt datetime of deletion. Resolution in the affected scope reverts to  the default matching order.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntityResolversApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteEntityResolver(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Entity Resolver |
| **code** | **string** | path | **required** | The code of the Entity Resolver. Together with the scope this uniquely identifies the Entity Resolver |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteEntityResolverWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteEntityResolverWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getentityresolver"></a>
## GetEntityResolver

> EntityResolver GetEntityResolver(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetEntityResolver: Get a single Entity Resolver

Get a single Entity Resolver by scope and code at an optional asAt, defaulting to latest if not specified.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntityResolversApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
EntityResolver result = apiInstance.GetEntityResolver(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Entity Resolver |
| **code** | **string** | path | **required** | The code of the Entity Resolver. Together with the scope this uniquely identifies the Entity Resolver |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Entity Resolver. Defaults to return              the latest version if not specified. |

### Return type

[EntityResolver](../Model/EntityResolver.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Entity Resolver |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetEntityResolverWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EntityResolver> response = apiInstance.GetEntityResolverWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateentityresolver"></a>
## UpdateEntityResolver

> EntityResolver UpdateEntityResolver(string scope, string code, UpsertEntityResolverRequest? upsertEntityResolverRequest = null)

[EXPERIMENTAL] UpdateEntityResolver: Update an Entity Resolver

Overwrites the description and identifier matching order of an existing Entity Resolver.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntityResolversApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertEntityResolverRequest = new UpsertEntityResolverRequest?(); // UpsertEntityResolverRequest? (optional)
EntityResolver result = apiInstance.UpdateEntityResolver(scope, code, upsertEntityResolverRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Entity Resolver |
| **code** | **string** | path | **required** | The code of the Entity Resolver. Together with the scope this uniquely identifies the Entity Resolver |
| **upsertEntityResolverRequest** | [UpsertEntityResolverRequest?](../Model/UpsertEntityResolverRequest?.md) | body | optional | The request containing the updated details of the Entity Resolver |

### Return type

[EntityResolver](../Model/EntityResolver.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Entity Resolver |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateEntityResolverWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EntityResolver> response = apiInstance.UpdateEntityResolverWithHttpInfo(scope, code, upsertEntityResolverRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

