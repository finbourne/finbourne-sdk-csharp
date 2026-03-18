# Finbourne.Sdk.Lusid.Api.RelationshipDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateRelationshipDefinition**](#createrelationshipdefinition) | **POST** `/api/api/relationshipdefinitions` | [EARLY ACCESS] CreateRelationshipDefinition: Create Relationship Definition |
| [**DeleteRelationshipDefinition**](#deleterelationshipdefinition) | **DELETE** `/api/api/relationshipdefinitions/{scope}/{code}` | [EARLY ACCESS] DeleteRelationshipDefinition: Delete Relationship Definition |
| [**GetRelationshipDefinition**](#getrelationshipdefinition) | **GET** `/api/api/relationshipdefinitions/{scope}/{code}` | [EARLY ACCESS] GetRelationshipDefinition: Get relationship definition |
| [**ListRelationshipDefinitions**](#listrelationshipdefinitions) | **GET** `/api/api/relationshipdefinitions` | [EARLY ACCESS] ListRelationshipDefinitions: List relationship definitions |
| [**UpdateRelationshipDefinition**](#updaterelationshipdefinition) | **PUT** `/api/api/relationshipdefinitions/{scope}/{code}` | [EARLY ACCESS] UpdateRelationshipDefinition: Update Relationship Definition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RelationshipDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipDefinitionsApi>();
```

---

<a id="createrelationshipdefinition"></a>
## CreateRelationshipDefinition

> RelationshipDefinition CreateRelationshipDefinition(CreateRelationshipDefinitionRequest createRelationshipDefinitionRequest)

[EARLY ACCESS] CreateRelationshipDefinition: Create Relationship Definition

Create a new relationship definition to be used for creating relationships between entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipDefinitionsApi>();
var createRelationshipDefinitionRequest = new CreateRelationshipDefinitionRequest(); // CreateRelationshipDefinitionRequest
RelationshipDefinition result = apiInstance.CreateRelationshipDefinition(createRelationshipDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createRelationshipDefinitionRequest** | [CreateRelationshipDefinitionRequest](CreateRelationshipDefinitionRequest.md) | body | **required** | The definition of the new relationship. |

### Return type

[RelationshipDefinition](RelationshipDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created relationship definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRelationshipDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationshipDefinition> response = apiInstance.CreateRelationshipDefinitionWithHttpInfo(createRelationshipDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterelationshipdefinition"></a>
## DeleteRelationshipDefinition

> DeletedEntityResponse DeleteRelationshipDefinition(string scope, string code)

[EARLY ACCESS] DeleteRelationshipDefinition: Delete Relationship Definition

Delete the definition of the specified relationship.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteRelationshipDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relationship definition to be deleted. |
| **code** | **string** | path | **required** | The code of the relationship definition to be deleted. Together with the domain and scope this uniquely              identifies the relationship. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time that the relationship definition was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRelationshipDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteRelationshipDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrelationshipdefinition"></a>
## GetRelationshipDefinition

> RelationshipDefinition GetRelationshipDefinition(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetRelationshipDefinition: Get relationship definition

Retrieve the specified relationship definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
RelationshipDefinition result = apiInstance.GetRelationshipDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified relationship definition. |
| **code** | **string** | path | **required** | The code of the specified relationship definition. Together with the domain and scope this uniquely              identifies the relationship definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the relationship definition. Defaults to return              the latest version of the definition if not specified. |

### Return type

[RelationshipDefinition](RelationshipDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested relationship definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRelationshipDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationshipDefinition> response = apiInstance.GetRelationshipDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrelationshipdefinitions"></a>
## ListRelationshipDefinitions

> PagedResourceListOfRelationshipDefinition ListRelationshipDefinitions(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EARLY ACCESS] ListRelationshipDefinitions: List relationship definitions

Retrieve one or more specified relationship definitions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipDefinitionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfRelationshipDefinition result = apiInstance.ListRelationshipDefinitions(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the relationship definitions. Defaults to return              the latest version of each definition if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing relationship definitions from a previous call to list relationship definitions. This  value is returned from the previous call. If a pagination token is provided the filter, sortBy and asAt field  must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Scope, use \&quot;scope eq &#39;ExampleScope&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfRelationshipDefinition](PagedResourceListOfRelationshipDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested relationship definitions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRelationshipDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRelationshipDefinition> response = apiInstance.ListRelationshipDefinitionsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterelationshipdefinition"></a>
## UpdateRelationshipDefinition

> RelationshipDefinition UpdateRelationshipDefinition(string scope, string code, UpdateRelationshipDefinitionRequest updateRelationshipDefinitionRequest)

[EARLY ACCESS] UpdateRelationshipDefinition: Update Relationship Definition

Update the definition of a specified existing relationship. Not all elements within a relationship definition  are modifiable due to the potential implications for values already stored against the relationship.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateRelationshipDefinitionRequest = new UpdateRelationshipDefinitionRequest(); // UpdateRelationshipDefinitionRequest
RelationshipDefinition result = apiInstance.UpdateRelationshipDefinition(scope, code, updateRelationshipDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relationship definition being updated. |
| **code** | **string** | path | **required** | The code of the relationship definition being updated. Together with the scope this uniquely              identifies the relationship definition. |
| **updateRelationshipDefinitionRequest** | [UpdateRelationshipDefinitionRequest](UpdateRelationshipDefinitionRequest.md) | body | **required** | The details of relationship definition to update. |

### Return type

[RelationshipDefinition](RelationshipDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated relationship definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRelationshipDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationshipDefinition> response = apiInstance.UpdateRelationshipDefinitionWithHttpInfo(scope, code, updateRelationshipDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

