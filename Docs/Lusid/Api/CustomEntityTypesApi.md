# Finbourne.Sdk.Lusid.Api.CustomEntityTypesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCustomEntityType**](#createcustomentitytype) | **POST** `/api/api/customentitytypes` | [EARLY ACCESS] CreateCustomEntityType: Define a new Custom Entity Type. |
| [**GetCustomEntityType**](#getcustomentitytype) | **GET** `/api/api/customentitytypes/{entityType}` | [EARLY ACCESS] GetCustomEntityType: Get a Custom Entity Type. |
| [**ListCustomEntityTypes**](#listcustomentitytypes) | **GET** `/api/api/customentitytypes` | [EARLY ACCESS] ListCustomEntityTypes: List Custom Entity Types. |
| [**UpdateCustomEntityType**](#updatecustomentitytype) | **PUT** `/api/api/customentitytypes/{entityType}` | [EARLY ACCESS] UpdateCustomEntityType: Modify an existing Custom Entity Type. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CustomEntityTypesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityTypesApi>();
```

---

<a id="createcustomentitytype"></a>
## CreateCustomEntityType

> CustomEntityType CreateCustomEntityType(CreateCustomEntityTypeRequest createCustomEntityTypeRequest)

[EARLY ACCESS] CreateCustomEntityType: Define a new Custom Entity Type.

The API will return a Bad Request if the Custom Entity Type already exists.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityTypesApi>();
var createCustomEntityTypeRequest = new CreateCustomEntityTypeRequest(); // CreateCustomEntityTypeRequest
CustomEntityType result = apiInstance.CreateCustomEntityType(createCustomEntityTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createCustomEntityTypeRequest** | [CreateCustomEntityTypeRequest](CreateCustomEntityTypeRequest.md) | body | **required** | The payload containing the description of the Custom Entity Type. |

### Return type

[CustomEntityType](CustomEntityType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created Custom Entity Type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCustomEntityTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityType> response = apiInstance.CreateCustomEntityTypeWithHttpInfo(createCustomEntityTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcustomentitytype"></a>
## GetCustomEntityType

> CustomEntityType GetCustomEntityType(string entityType, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetCustomEntityType: Get a Custom Entity Type.

Retrieve a specific Custom Entity Type at a point in AsAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityTypesApi>();
var entityType = "entityType_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CustomEntityType result = apiInstance.GetCustomEntityType(entityType, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The identifier for the Custom Entity Type, derived from the \&quot;entityTypeName\&quot; provided on creation. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the definition. |

### Return type

[CustomEntityType](CustomEntityType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Custom Entity Type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustomEntityTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityType> response = apiInstance.GetCustomEntityTypeWithHttpInfo(entityType, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcustomentitytypes"></a>
## ListCustomEntityTypes

> PagedResourceListOfCustomEntityType ListCustomEntityTypes(DateTimeOffset? asAt = null, int? limit = null, string? filter = null, List<string>? sortBy = null, string? page = null)

[EARLY ACCESS] ListCustomEntityTypes: List Custom Entity Types.

List all Custom Entity Types matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityTypesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfCustomEntityType result = apiInstance.ListCustomEntityTypes(asAt, limit, filter, sortBy, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the entities. Defaults to returning the latest version              of each Custom Entity Type if not specified. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **page** | **string?** | query | optional | The pagination token to use to continue listing entities; this              value is returned from the previous call. If a pagination token is provided, the filter, limit, sortBy,              and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfCustomEntityType](PagedResourceListOfCustomEntityType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Custom Entity Types. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCustomEntityTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCustomEntityType> response = apiInstance.ListCustomEntityTypesWithHttpInfo(asAt, limit, filter, sortBy, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecustomentitytype"></a>
## UpdateCustomEntityType

> CustomEntityType UpdateCustomEntityType(string entityType, UpdateCustomEntityTypeRequest updateCustomEntityTypeRequest)

[EARLY ACCESS] UpdateCustomEntityType: Modify an existing Custom Entity Type.

The API will return a Bad Request if the Custom Entity Type does not exist.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntityTypesApi>();
var entityType = "entityType_example";  // string
var updateCustomEntityTypeRequest = new UpdateCustomEntityTypeRequest(); // UpdateCustomEntityTypeRequest
CustomEntityType result = apiInstance.UpdateCustomEntityType(entityType, updateCustomEntityTypeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The identifier for the Custom Entity Type, derived from the \&quot;entityTypeName\&quot; provided on creation. |
| **updateCustomEntityTypeRequest** | [UpdateCustomEntityTypeRequest](UpdateCustomEntityTypeRequest.md) | body | **required** | The payload containing the description of the Custom Entity Type. |

### Return type

[CustomEntityType](CustomEntityType.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Custom Entity Type. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateCustomEntityTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityType> response = apiInstance.UpdateCustomEntityTypeWithHttpInfo(entityType, updateCustomEntityTypeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

