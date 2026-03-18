# Finbourne.Sdk.Lusid.Api.RelationalDatasetDefinitionApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateRelationalDatasetDefinition**](#createrelationaldatasetdefinition) | **POST** `/api/api/relationaldatasetdefinitions` | CreateRelationalDatasetDefinition: Create a Relational Dataset Definition |
| [**DeleteRelationalDatasetDefinition**](#deleterelationaldatasetdefinition) | **DELETE** `/api/api/relationaldatasetdefinitions/{scope}/{code}` | DeleteRelationalDatasetDefinition: Delete a Relational Dataset Definition |
| [**GetRelationalDatasetDefinition**](#getrelationaldatasetdefinition) | **GET** `/api/api/relationaldatasetdefinitions/{scope}/{code}` | GetRelationalDatasetDefinition: Get a Relational Dataset Definition |
| [**ListRelationalDatasetDefinitions**](#listrelationaldatasetdefinitions) | **GET** `/api/api/relationaldatasetdefinitions` | ListRelationalDatasetDefinitions: List Relational Dataset Definitions |
| [**UpdateRelationalDatasetDefinition**](#updaterelationaldatasetdefinition) | **PUT** `/api/api/relationaldatasetdefinitions/{scope}/{code}` | UpdateRelationalDatasetDefinition: Update a Relational Dataset Definition |
| [**UpdateRelationalDatasetDetails**](#updaterelationaldatasetdetails) | **POST** `/api/api/relationaldatasetdefinitions/{scope}/{code}/details/$update` | UpdateRelationalDatasetDetails: Update Relational Dataset Details: DisplayName, Description and ApplicableEntityTypes |
| [**UpdateRelationalDatasetFieldSchema**](#updaterelationaldatasetfieldschema) | **POST** `/api/api/relationaldatasetdefinitions/{scope}/{code}/fieldschema/$update` | UpdateRelationalDatasetFieldSchema: Update Relational Dataset Field Schema |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RelationalDatasetDefinitionApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
```

---

<a id="createrelationaldatasetdefinition"></a>
## CreateRelationalDatasetDefinition

> RelationalDatasetDefinition CreateRelationalDatasetDefinition(CreateRelationalDatasetDefinitionRequest createRelationalDatasetDefinitionRequest)

CreateRelationalDatasetDefinition: Create a Relational Dataset Definition

Create a new relational dataset definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var createRelationalDatasetDefinitionRequest = new CreateRelationalDatasetDefinitionRequest(); // CreateRelationalDatasetDefinitionRequest
RelationalDatasetDefinition result = apiInstance.CreateRelationalDatasetDefinition(createRelationalDatasetDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createRelationalDatasetDefinitionRequest** | [CreateRelationalDatasetDefinitionRequest](CreateRelationalDatasetDefinitionRequest.md) | body | **required** | The relational dataset definition to create. |

### Return type

[RelationalDatasetDefinition](RelationalDatasetDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created relational dataset definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRelationalDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationalDatasetDefinition> response = apiInstance.CreateRelationalDatasetDefinitionWithHttpInfo(createRelationalDatasetDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterelationaldatasetdefinition"></a>
## DeleteRelationalDatasetDefinition

> DeletedEntityResponse DeleteRelationalDatasetDefinition(string scope, string code)

DeleteRelationalDatasetDefinition: Delete a Relational Dataset Definition

Delete a relational dataset definition.  WARNING! This operation is irreversible. Deleting a relational dataset definition will also delete all associated data points.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteRelationalDatasetDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relational dataset definition. |
| **code** | **string** | path | **required** | The code of the relational dataset definition. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

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
<summary>Using the DeleteRelationalDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteRelationalDatasetDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrelationaldatasetdefinition"></a>
## GetRelationalDatasetDefinition

> RelationalDatasetDefinition GetRelationalDatasetDefinition(string scope, string code, DateTimeOffset? asAt = null)

GetRelationalDatasetDefinition: Get a Relational Dataset Definition

Retrieve a relational dataset definition by its identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
RelationalDatasetDefinition result = apiInstance.GetRelationalDatasetDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relational dataset definition. |
| **code** | **string** | path | **required** | The code of the relational dataset definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the relational dataset definition. Defaults to return the latest version if not specified. |

### Return type

[RelationalDatasetDefinition](RelationalDatasetDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested relational dataset definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRelationalDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationalDatasetDefinition> response = apiInstance.GetRelationalDatasetDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrelationaldatasetdefinitions"></a>
## ListRelationalDatasetDefinitions

> PagedResourceListOfRelationalDatasetDefinition ListRelationalDatasetDefinitions(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

ListRelationalDatasetDefinitions: List Relational Dataset Definitions

List all relational dataset definitions matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfRelationalDatasetDefinition result = apiInstance.ListRelationalDatasetDefinitions(asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the relational dataset definitions. Defaults to return the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing relational dataset definitions from a previous call to list relational dataset definitions. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |

### Return type

[PagedResourceListOfRelationalDatasetDefinition](PagedResourceListOfRelationalDatasetDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of relational dataset definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRelationalDatasetDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRelationalDatasetDefinition> response = apiInstance.ListRelationalDatasetDefinitionsWithHttpInfo(asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterelationaldatasetdefinition"></a>
## UpdateRelationalDatasetDefinition

> RelationalDatasetDefinition UpdateRelationalDatasetDefinition(string scope, string code, UpdateRelationalDatasetDefinitionRequest? updateRelationalDatasetDefinitionRequest = null)

UpdateRelationalDatasetDefinition: Update a Relational Dataset Definition

Update an existing relational dataset definition.  Applicable only to the definitions that are not yet in use i.e. there are no DataPoints associated with this definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateRelationalDatasetDefinitionRequest = new UpdateRelationalDatasetDefinitionRequest?(); // UpdateRelationalDatasetDefinitionRequest? (optional)
RelationalDatasetDefinition result = apiInstance.UpdateRelationalDatasetDefinition(scope, code, updateRelationalDatasetDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relational dataset definition. |
| **code** | **string** | path | **required** | The code of the relational dataset definition. |
| **updateRelationalDatasetDefinitionRequest** | [UpdateRelationalDatasetDefinitionRequest?](UpdateRelationalDatasetDefinitionRequest?.md) | body | optional | The updated relational dataset definition. |

### Return type

[RelationalDatasetDefinition](RelationalDatasetDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated relational dataset definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRelationalDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationalDatasetDefinition> response = apiInstance.UpdateRelationalDatasetDefinitionWithHttpInfo(scope, code, updateRelationalDatasetDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterelationaldatasetdetails"></a>
## UpdateRelationalDatasetDetails

> RelationalDatasetDefinition UpdateRelationalDatasetDetails(string scope, string code, UpdateRelationalDatasetDetails? updateRelationalDatasetDetails = null)

UpdateRelationalDatasetDetails: Update Relational Dataset Details: DisplayName, Description and ApplicableEntityTypes

Update an existing relational dataset definition.  Applicable only to the definitions that are already in use i.e. contain DataPoints associated with this definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateRelationalDatasetDetails = new UpdateRelationalDatasetDetails?(); // UpdateRelationalDatasetDetails? (optional)
RelationalDatasetDefinition result = apiInstance.UpdateRelationalDatasetDetails(scope, code, updateRelationalDatasetDetails);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relational dataset definition. |
| **code** | **string** | path | **required** | The code of the relational dataset definition. |
| **updateRelationalDatasetDetails** | [UpdateRelationalDatasetDetails?](UpdateRelationalDatasetDetails?.md) | body | optional | The updated details of the relational dataset. |

### Return type

[RelationalDatasetDefinition](RelationalDatasetDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated relational dataset definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRelationalDatasetDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationalDatasetDefinition> response = apiInstance.UpdateRelationalDatasetDetailsWithHttpInfo(scope, code, updateRelationalDatasetDetails);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterelationaldatasetfieldschema"></a>
## UpdateRelationalDatasetFieldSchema

> RelationalDatasetDefinition UpdateRelationalDatasetFieldSchema(string scope, string code, UpdateRelationalDatasetFieldSchema? updateRelationalDatasetFieldSchema = null)

UpdateRelationalDatasetFieldSchema: Update Relational Dataset Field Schema

Update an existing relational dataset definition with the new field schema.  Applicable only to the definitions that are already in use i.e. contain DataPoints associated with this definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationalDatasetDefinitionApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateRelationalDatasetFieldSchema = new UpdateRelationalDatasetFieldSchema?(); // UpdateRelationalDatasetFieldSchema? (optional)
RelationalDatasetDefinition result = apiInstance.UpdateRelationalDatasetFieldSchema(scope, code, updateRelationalDatasetFieldSchema);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relational dataset definition. |
| **code** | **string** | path | **required** | The code of the relational dataset definition. |
| **updateRelationalDatasetFieldSchema** | [UpdateRelationalDatasetFieldSchema?](UpdateRelationalDatasetFieldSchema?.md) | body | optional | Relational dataset fields to add, update or remove. |

### Return type

[RelationalDatasetDefinition](RelationalDatasetDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated relational dataset definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRelationalDatasetFieldSchemaWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RelationalDatasetDefinition> response = apiInstance.UpdateRelationalDatasetFieldSchemaWithHttpInfo(scope, code, updateRelationalDatasetFieldSchema);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

