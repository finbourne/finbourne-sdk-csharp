# Finbourne.Sdk.Lusid.Api.ScopesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListEntityScopes**](#listentityscopes) | **GET** `/api/api/scopes/{entityType}` | ListEntityScopes: List Entity Scopes |
| [**ListScopes**](#listscopes) | **GET** `/api/api/scopes` | ListScopes: List Scopes |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ScopesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScopesApi>();
```

---

<a id="listentityscopes"></a>
## ListEntityScopes

> ResourceListOfScopeDefinition ListEntityScopes(string entityType, DateTimeOffset? asAt = null, string? page = null, int? limit = null)

ListEntityScopes: List Entity Scopes

List all the scopes for a given entity type that contain data.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScopesApi>();
var entityType = "entityType_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfScopeDefinition result = apiInstance.ListEntityScopes(entityType, asAt, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type to list scopes for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve scopes. Defaults to latest datetime if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing scopes from a previous call to list scopes.              This value is returned from the previous call. If a pagination token is provided, the limit and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this number. Defaults to 100 if not specified. |

### Return type

[ResourceListOfScopeDefinition](ResourceListOfScopeDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of scopes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListEntityScopesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScopeDefinition> response = apiInstance.ListEntityScopesWithHttpInfo(entityType, asAt, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listscopes"></a>
## ListScopes

> ResourceListOfScopeDefinition ListScopes(string? filter = null)

ListScopes: List Scopes

List all the scopes that contain data.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScopesApi>();
var filter = "filter_example";  // string? (optional)
ResourceListOfScopeDefinition result = apiInstance.ListScopes(filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Scope, use \&quot;scope eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfScopeDefinition](ResourceListOfScopeDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of scopes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListScopesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScopeDefinition> response = apiInstance.ListScopesWithHttpInfo(filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

