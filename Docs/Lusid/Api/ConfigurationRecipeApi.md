# Finbourne.Sdk.Lusid.Api.ConfigurationRecipeApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteConfigurationRecipe**](#deleteconfigurationrecipe) | **DELETE** `/api/api/recipes/{scope}/{code}` | DeleteConfigurationRecipe: Delete a Configuration Recipe, assuming that it is present. |
| [**DeleteRecipeComposer**](#deleterecipecomposer) | **DELETE** `/api/api/recipes/composer/{scope}/{code}` | DeleteRecipeComposer: Delete a Recipe Composer, assuming that it is present. |
| [**GetConfigurationRecipe**](#getconfigurationrecipe) | **GET** `/api/api/recipes/{scope}/{code}` | GetConfigurationRecipe: Get Configuration Recipe |
| [**GetDerivedRecipe**](#getderivedrecipe) | **GET** `/api/api/recipes/derived/{scope}/{code}` | GetDerivedRecipe: Get Configuration Recipe either from the store or expanded from a Recipe Composer. |
| [**GetRecipeComposer**](#getrecipecomposer) | **GET** `/api/api/recipes/composer/{scope}/{code}` | GetRecipeComposer: Get Recipe Composer |
| [**GetRecipeComposerResolvedInline**](#getrecipecomposerresolvedinline) | **POST** `/api/api/recipes/composer/resolvedinline$` | GetRecipeComposerResolvedInline: Given a Recipe Composer, this endpoint expands into a Configuration Recipe without persistence. Primarily used for testing purposes. |
| [**ListConfigurationRecipes**](#listconfigurationrecipes) | **GET** `/api/api/recipes` | ListConfigurationRecipes: List the set of Configuration Recipes |
| [**ListDerivedRecipes**](#listderivedrecipes) | **GET** `/api/api/recipes/derived` | ListDerivedRecipes: List the complete set of all Configuration Recipes, both from the configuration recipe store and also from expanded recipe composers. |
| [**ListRecipeComposers**](#listrecipecomposers) | **GET** `/api/api/recipes/composer` | ListRecipeComposers: List the set of Recipe Composers |
| [**UpsertConfigurationRecipe**](#upsertconfigurationrecipe) | **POST** `/api/api/recipes` | UpsertConfigurationRecipe: Upsert a Configuration Recipe. This creates or updates the data in Lusid. |
| [**UpsertRecipeComposer**](#upsertrecipecomposer) | **POST** `/api/api/recipes/composer` | UpsertRecipeComposer: Upsert a Recipe Composer. This creates or updates the data in Lusid. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ConfigurationRecipeApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
```

---

<a id="deleteconfigurationrecipe"></a>
## DeleteConfigurationRecipe

> AnnulSingleStructuredDataResponse DeleteConfigurationRecipe(string scope, string code)

DeleteConfigurationRecipe: Delete a Configuration Recipe, assuming that it is present.

Delete the specified Configuration Recipe from a single scope.                The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.                It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteConfigurationRecipe(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Configuration Recipe to delete. |
| **code** | **string** | path | **required** | The Configuration Recipe to delete. |

### Return type

[AnnulSingleStructuredDataResponse](AnnulSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The AsAt of deletion or failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteConfigurationRecipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteConfigurationRecipeWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterecipecomposer"></a>
## DeleteRecipeComposer

> AnnulSingleStructuredDataResponse DeleteRecipeComposer(string scope, string code)

DeleteRecipeComposer: Delete a Recipe Composer, assuming that it is present.

Delete the specified Recipe Composer from a single scope.                The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.                It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteRecipeComposer(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Recipe Composer to delete. |
| **code** | **string** | path | **required** | The Recipe Composer to delete. |

### Return type

[AnnulSingleStructuredDataResponse](AnnulSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The AsAt of deletion or failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRecipeComposerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteRecipeComposerWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getconfigurationrecipe"></a>
## GetConfigurationRecipe

> GetRecipeResponse GetConfigurationRecipe(string scope, string code, DateTimeOffset? asAt = null)

GetConfigurationRecipe: Get Configuration Recipe

Get a Configuration Recipe from a single scope.                The response will return either the recipe that has been stored, or a failure explaining why the request was unsuccessful.                It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetRecipeResponse result = apiInstance.GetConfigurationRecipe(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Configuration Recipe to retrieve. |
| **code** | **string** | path | **required** | The name of the recipe to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Configuration Recipe. Defaults to return the latest version if not specified. |

### Return type

[GetRecipeResponse](GetRecipeResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Configuration Recipe or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetConfigurationRecipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetRecipeResponse> response = apiInstance.GetConfigurationRecipeWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getderivedrecipe"></a>
## GetDerivedRecipe

> GetRecipeResponse GetDerivedRecipe(string scope, string code, DateTimeOffset? asAt = null)

GetDerivedRecipe: Get Configuration Recipe either from the store or expanded from a Recipe Composer.

If scope-code is referring to a Configuration Recipe it is returned, if it refers to Recipe Composer, it is expanded into a Configuration Recipe and returned.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetRecipeResponse result = apiInstance.GetDerivedRecipe(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Configuration Recipe or Recipe Composer to return. |
| **code** | **string** | path | **required** | The code of the Configuration Recipe or Recipe Composer to return. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Configuration Recipe. Defaults to return the latest version if not specified. |

### Return type

[GetRecipeResponse](GetRecipeResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Configuration Recipe or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDerivedRecipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetRecipeResponse> response = apiInstance.GetDerivedRecipeWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrecipecomposer"></a>
## GetRecipeComposer

> GetRecipeComposerResponse GetRecipeComposer(string scope, string code, DateTimeOffset? asAt = null)

GetRecipeComposer: Get Recipe Composer

Get a Recipe Composer from a single scope.                The response will return either the recipe composer that has been stored, or a failure explaining why the request was unsuccessful.                It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetRecipeComposerResponse result = apiInstance.GetRecipeComposer(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Recipe Composer to retrieve. |
| **code** | **string** | path | **required** | The name of the Recipe Composer to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Recipe Composer. Defaults to return the latest version if not specified. |

### Return type

[GetRecipeComposerResponse](GetRecipeComposerResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Recipe Composer or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRecipeComposerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetRecipeComposerResponse> response = apiInstance.GetRecipeComposerWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrecipecomposerresolvedinline"></a>
## GetRecipeComposerResolvedInline

> GetRecipeResponse GetRecipeComposerResolvedInline(UpsertRecipeComposerRequest upsertRecipeComposerRequest)

GetRecipeComposerResolvedInline: Given a Recipe Composer, this endpoint expands into a Configuration Recipe without persistence. Primarily used for testing purposes.

Resolves an inline recipe composer into a ConfigurationRecipe.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var upsertRecipeComposerRequest = new UpsertRecipeComposerRequest(); // UpsertRecipeComposerRequest
GetRecipeResponse result = apiInstance.GetRecipeComposerResolvedInline(upsertRecipeComposerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertRecipeComposerRequest** | [UpsertRecipeComposerRequest](UpsertRecipeComposerRequest.md) | body | **required** | Recipe composer used to expand into the Configuration Recipe. |

### Return type

[GetRecipeResponse](GetRecipeResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully resolved Configuration Recipe. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRecipeComposerResolvedInlineWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetRecipeResponse> response = apiInstance.GetRecipeComposerResolvedInlineWithHttpInfo(upsertRecipeComposerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listconfigurationrecipes"></a>
## ListConfigurationRecipes

> ResourceListOfGetRecipeResponse ListConfigurationRecipes(DateTimeOffset? asAt = null, string? filter = null)

ListConfigurationRecipes: List the set of Configuration Recipes

List the set of configuration recipes at the specified date/time and scope. Note this only returns recipes stored directly and does not include any recipes expanded from recipe composers.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfGetRecipeResponse result = apiInstance.ListConfigurationRecipes(asAt, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Configuration Recipes. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfGetRecipeResponse](ResourceListOfGetRecipeResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested configuration recipes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListConfigurationRecipesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetRecipeResponse> response = apiInstance.ListConfigurationRecipesWithHttpInfo(asAt, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listderivedrecipes"></a>
## ListDerivedRecipes

> ResourceListOfGetRecipeResponse ListDerivedRecipes(DateTimeOffset? asAt = null, string? filter = null)

ListDerivedRecipes: List the complete set of all Configuration Recipes, both from the configuration recipe store and also from expanded recipe composers.

This endpoints returns a union of the output of ListConfigurationRecipes and the resolved Recipe Composers from the ListRecipeComposers endpoints.  Recipe Composers that fail to generate a valid Configuration Recipe will not be reported.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfGetRecipeResponse result = apiInstance.ListDerivedRecipes(asAt, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Configuration Recipes. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set, note this functionality is not yet enabled for this endpoint. |

### Return type

[ResourceListOfGetRecipeResponse](ResourceListOfGetRecipeResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested configuration recipes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListDerivedRecipesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetRecipeResponse> response = apiInstance.ListDerivedRecipesWithHttpInfo(asAt, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrecipecomposers"></a>
## ListRecipeComposers

> ResourceListOfGetRecipeComposerResponse ListRecipeComposers(DateTimeOffset? asAt = null, string? filter = null)

ListRecipeComposers: List the set of Recipe Composers

List the set of Recipe Composers at the specified date/time and scope

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfGetRecipeComposerResponse result = apiInstance.ListRecipeComposers(asAt, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Recipes Composers. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set, note this functionality is not yet enabled for this endpoint. |

### Return type

[ResourceListOfGetRecipeComposerResponse](ResourceListOfGetRecipeComposerResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested recipe composers |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRecipeComposersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetRecipeComposerResponse> response = apiInstance.ListRecipeComposersWithHttpInfo(asAt, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertconfigurationrecipe"></a>
## UpsertConfigurationRecipe

> UpsertSingleStructuredDataResponse UpsertConfigurationRecipe(UpsertRecipeRequest upsertRecipeRequest)

UpsertConfigurationRecipe: Upsert a Configuration Recipe. This creates or updates the data in Lusid.

Update or insert one Configuration Recipe in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Configuration Recipe or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var upsertRecipeRequest = new UpsertRecipeRequest(); // UpsertRecipeRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertConfigurationRecipe(upsertRecipeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertRecipeRequest** | [UpsertRecipeRequest](UpsertRecipeRequest.md) | body | **required** | The Configuration Recipe to update or insert |

### Return type

[UpsertSingleStructuredDataResponse](UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted item or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertConfigurationRecipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertConfigurationRecipeWithHttpInfo(upsertRecipeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertrecipecomposer"></a>
## UpsertRecipeComposer

> UpsertSingleStructuredDataResponse UpsertRecipeComposer(UpsertRecipeComposerRequest upsertRecipeComposerRequest)

UpsertRecipeComposer: Upsert a Recipe Composer. This creates or updates the data in Lusid.

Update or insert one Recipe Composer in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Recipe Composer or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConfigurationRecipeApi>();
var upsertRecipeComposerRequest = new UpsertRecipeComposerRequest(); // UpsertRecipeComposerRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertRecipeComposer(upsertRecipeComposerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertRecipeComposerRequest** | [UpsertRecipeComposerRequest](UpsertRecipeComposerRequest.md) | body | **required** | The Recipe Composer to update or insert |

### Return type

[UpsertSingleStructuredDataResponse](UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted item or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertRecipeComposerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertRecipeComposerWithHttpInfo(upsertRecipeComposerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

