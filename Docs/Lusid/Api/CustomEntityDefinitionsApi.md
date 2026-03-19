# Finbourne.Sdk.Lusid.Api.CustomEntityDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCustomEntityDefinition**](#createcustomentitydefinition) | **POST** `/api/api/customentities/entitytypes` | [EARLY ACCESS] CreateCustomEntityDefinition: Define a new Custom Entity type. |
| [**DeleteDefinition**](#deletedefinition) | **DELETE** `/api/api/customentities/entitytypes/{entityType}` | [EARLY ACCESS] DeleteDefinition: Delete a Custom Entity type definition. |
| [**GetDefinition**](#getdefinition) | **GET** `/api/api/customentities/entitytypes/{entityType}` | [EARLY ACCESS] GetDefinition: Get a Custom Entity type definition. |
| [**ListCustomEntityDefinitions**](#listcustomentitydefinitions) | **GET** `/api/api/customentities/entitytypes` | [EARLY ACCESS] ListCustomEntityDefinitions: List the Custom Entity type definitions |
| [**UpdateCustomEntityDefinition**](#updatecustomentitydefinition) | **PUT** `/api/api/customentities/entitytypes/{entityType}` | [EARLY ACCESS] UpdateCustomEntityDefinition: Modify an existing Custom Entity type. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CustomEntityDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityDefinitionsApi>();
```

---

<a id="createcustomentitydefinition"></a>
## CreateCustomEntityDefinition

> CustomEntityDefinition CreateCustomEntityDefinition(CustomEntityDefinitionRequest customEntityDefinitionRequest)

[EARLY ACCESS] CreateCustomEntityDefinition: Define a new Custom Entity type.

The API will return a Bad Request if the Custom Entity type already exists.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityDefinitionsApi>();
var customEntityDefinitionRequest = new CustomEntityDefinitionRequest(); // CustomEntityDefinitionRequest
CustomEntityDefinition result = apiInstance.CreateCustomEntityDefinition(customEntityDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **customEntityDefinitionRequest** | [CustomEntityDefinitionRequest](CustomEntityDefinitionRequest.md) | body | **required** | The payload containing the description of the Custom Entity type. |

### Return type

[CustomEntityDefinition](CustomEntityDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created Custom Entity type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCustomEntityDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityDefinition> response = apiInstance.CreateCustomEntityDefinitionWithHttpInfo(customEntityDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletedefinition"></a>
## DeleteDefinition

> DeletedEntityResponse DeleteDefinition(string entityType)

[EARLY ACCESS] DeleteDefinition: Delete a Custom Entity type definition.

Delete a Custom Entity type definition by a specific entityType. This will delete all versions of the definition and all associated Custom Entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityDefinitionsApi>();
var entityType = "entityType_example";  // string
DeletedEntityResponse result = apiInstance.DeleteDefinition(entityType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The identifier for the Custom Entity type, derived from the \&quot;entityTypeName\&quot; provided on creation. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteDefinitionWithHttpInfo(entityType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdefinition"></a>
## GetDefinition

> CustomEntityDefinition GetDefinition(string entityType, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetDefinition: Get a Custom Entity type definition.

Retrieve a CustomEntityDefinition by a specific entityType at a point in AsAt time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityDefinitionsApi>();
var entityType = "entityType_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CustomEntityDefinition result = apiInstance.GetDefinition(entityType, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The identifier for the Custom Entity type, derived from the \&quot;entityTypeName\&quot; provided on creation. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the definition. |

### Return type

[CustomEntityDefinition](CustomEntityDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Custom Entity definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityDefinition> response = apiInstance.GetDefinitionWithHttpInfo(entityType, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcustomentitydefinitions"></a>
## ListCustomEntityDefinitions

> PagedResourceListOfCustomEntityDefinition ListCustomEntityDefinitions(DateTimeOffset? asAt = null, int? limit = null, string? filter = null, string? page = null)

[EARLY ACCESS] ListCustomEntityDefinitions: List the Custom Entity type definitions

List all Custom Entity type definitions matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityDefinitionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfCustomEntityDefinition result = apiInstance.ListCustomEntityDefinitions(asAt, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the entities. Defaults to returning the latest version              of each portfolio if not specified. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing entities; this              value is returned from the previous call. If a pagination token is provided, the filter, limit              and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfCustomEntityDefinition](PagedResourceListOfCustomEntityDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Custom Entity type definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCustomEntityDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCustomEntityDefinition> response = apiInstance.ListCustomEntityDefinitionsWithHttpInfo(asAt, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecustomentitydefinition"></a>
## UpdateCustomEntityDefinition

> CustomEntityDefinition UpdateCustomEntityDefinition(string entityType, UpdateCustomEntityDefinitionRequest updateCustomEntityDefinitionRequest)

[EARLY ACCESS] UpdateCustomEntityDefinition: Modify an existing Custom Entity type.

The API will return a Bad Request if the Custom Entity type does not exist.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityDefinitionsApi>();
var entityType = "entityType_example";  // string
var updateCustomEntityDefinitionRequest = new UpdateCustomEntityDefinitionRequest(); // UpdateCustomEntityDefinitionRequest
CustomEntityDefinition result = apiInstance.UpdateCustomEntityDefinition(entityType, updateCustomEntityDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The identifier for the Custom Entity type, derived from the \&quot;entityTypeName\&quot; provided on creation. |
| **updateCustomEntityDefinitionRequest** | [UpdateCustomEntityDefinitionRequest](UpdateCustomEntityDefinitionRequest.md) | body | **required** | The payload containing the description of the Custom Entity type. |

### Return type

[CustomEntityDefinition](CustomEntityDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Custom Entity type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateCustomEntityDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityDefinition> response = apiInstance.UpdateCustomEntityDefinitionWithHttpInfo(entityType, updateCustomEntityDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

