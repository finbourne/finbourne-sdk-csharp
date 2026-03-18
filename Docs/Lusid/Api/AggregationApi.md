# Finbourne.Sdk.Lusid.Api.AggregationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GenerateConfigurationRecipe**](#generateconfigurationrecipe) | **POST** `/api/api/aggregation/{scope}/{code}/$generateconfigurationrecipe` | [EXPERIMENTAL] GenerateConfigurationRecipe: Generates a recipe sufficient to perform valuations for the given portfolio. |
| [**GetQueryableKeys**](#getqueryablekeys) | **GET** `/api/api/results/queryable/keys` | GetQueryableKeys: Query the set of supported \&quot;addresses\&quot; that can be queried from the aggregation endpoint. |
| [**GetValuation**](#getvaluation) | **POST** `/api/api/aggregation/$valuation` | GetValuation: Perform valuation for a list of portfolios and/or portfolio groups |
| [**GetValuationOfWeightedInstruments**](#getvaluationofweightedinstruments) | **POST** `/api/api/aggregation/$valuationinlined` | GetValuationOfWeightedInstruments: Perform valuation for an inlined portfolio |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AggregationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregationApi>();
```

---

<a id="generateconfigurationrecipe"></a>
## GenerateConfigurationRecipe

> ConfigurationRecipe GenerateConfigurationRecipe(string scope, string code, CreateRecipeRequest? createRecipeRequest = null)

[EXPERIMENTAL] GenerateConfigurationRecipe: Generates a recipe sufficient to perform valuations for the given portfolio.

Given a set of scopes, a portfolio Id and a basic recipe, this endpoint generates a configuration recipe with relevant rules that can value the instruments in the portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createRecipeRequest = new CreateRecipeRequest?(); // CreateRecipeRequest? (optional)
ConfigurationRecipe result = apiInstance.GenerateConfigurationRecipe(scope, code, createRecipeRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio |
| **code** | **string** | path | **required** | The code of the portfolio |
| **createRecipeRequest** | [CreateRecipeRequest?](CreateRecipeRequest?.md) | body | optional | The request specifying the parameters to generating the recipe |

### Return type

[ConfigurationRecipe](ConfigurationRecipe.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GenerateConfigurationRecipeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ConfigurationRecipe> response = apiInstance.GenerateConfigurationRecipeWithHttpInfo(scope, code, createRecipeRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getqueryablekeys"></a>
## GetQueryableKeys

> ResourceListOfAggregationQuery GetQueryableKeys(string? page = null, int? limit = null, string? filter = null)

GetQueryableKeys: Query the set of supported \"addresses\" that can be queried from the aggregation endpoint.

When a request is made for aggregation, the user needs to know what keys can be passed to it for queryable data. This endpoint allows to queries to provide the set of keys,  what they are and what they return.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregationApi>();
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfAggregationQuery result = apiInstance.GetQueryableKeys(page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing queryable keys from a previous call to list queryable keys.              This value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfAggregationQuery](ResourceListOfAggregationQuery.md)

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
<summary>Using the GetQueryableKeysWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAggregationQuery> response = apiInstance.GetQueryableKeysWithHttpInfo(page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluation"></a>
## GetValuation

> ListAggregationResponse GetValuation(ValuationRequest? valuationRequest = null)

GetValuation: Perform valuation for a list of portfolios and/or portfolio groups

Perform valuation on specified list of portfolio and/or portfolio groups for a set of dates.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregationApi>();
var valuationRequest = new ValuationRequest?(); // ValuationRequest? (optional)
ListAggregationResponse result = apiInstance.GetValuation(valuationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **valuationRequest** | [ValuationRequest?](ValuationRequest?.md) | body | optional | The request specifying the set of portfolios and dates on which to calculate a set of valuation metrics |

### Return type

[ListAggregationResponse](ListAggregationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ListAggregationResponse> response = apiInstance.GetValuationWithHttpInfo(valuationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationofweightedinstruments"></a>
## GetValuationOfWeightedInstruments

> ListAggregationResponse GetValuationOfWeightedInstruments(InlineValuationRequest? inlineValuationRequest = null)

GetValuationOfWeightedInstruments: Perform valuation for an inlined portfolio

Perform valuation on the portfolio that is defined by the weighted set of instruments passed to the request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregationApi>();
var inlineValuationRequest = new InlineValuationRequest?(); // InlineValuationRequest? (optional)
ListAggregationResponse result = apiInstance.GetValuationOfWeightedInstruments(inlineValuationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **inlineValuationRequest** | [InlineValuationRequest?](InlineValuationRequest?.md) | body | optional | The request specifying the set of portfolios and dates on which to calculate a set of valuation metrics |

### Return type

[ListAggregationResponse](ListAggregationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationOfWeightedInstrumentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ListAggregationResponse> response = apiInstance.GetValuationOfWeightedInstrumentsWithHttpInfo(inlineValuationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

