# Finbourne.Sdk.Lusid.Api.SearchApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**InstrumentsSearch**](#instrumentssearch) | **POST** `/api/api/search/instruments` | [EARLY ACCESS] InstrumentsSearch: Instruments search |
| [**SearchPortfolioGroups**](#searchportfoliogroups) | **GET** `/api/api/search/portfoliogroups` | SearchPortfolioGroups: Search Portfolio Groups |
| [**SearchPortfolios**](#searchportfolios) | **GET** `/api/api/search/portfolios` | SearchPortfolios: Search Portfolios |
| [**SearchProperties**](#searchproperties) | **GET** `/api/api/search/propertydefinitions` | SearchProperties: Search Property Definitions |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SearchApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
```

---

<a id="instrumentssearch"></a>
## InstrumentsSearch

> List&lt;InstrumentMatch&gt; InstrumentsSearch(List<InstrumentSearchProperty> instrumentSearchProperty, DateTimeOrCutLabel? masteredEffectiveAt = null, bool? masteredOnly = null, string? scope = null)

[EARLY ACCESS] InstrumentsSearch: Instruments search

Search across all instruments that have been mastered in LUSID. Optionally augment the results with instruments from an external symbology service,  currently OpenFIGI.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
var instrumentSearchProperty = new List<InstrumentSearchProperty>(); // List<InstrumentSearchProperty>
var masteredEffectiveAt = "masteredEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var masteredOnly = false;  // bool? (optional)
var scope = "scope_example";  // string? (optional)
List<InstrumentMatch> result = apiInstance.InstrumentsSearch(instrumentSearchProperty, masteredEffectiveAt, masteredOnly, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentSearchProperty** | [List&lt;InstrumentSearchProperty&gt;](InstrumentSearchProperty.md) | body | **required** | A collection of instrument properties to search for. LUSID will return instruments for any matched              properties. |
| **masteredEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label to use when searching mastered instruments. This parameter has no effect on instruments that  have not been mastered within LUSID. Defaults to the current LUSID system datetime if not specified. |
| **masteredOnly** | **bool?** | query | optional | If set to true, only search over instruments that have been mastered within LUSID. Defaults to false. Default: `false` |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. |

### Return type

[List&lt;InstrumentMatch&gt;](InstrumentMatch.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The instruments found by the search |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the InstrumentsSearchWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<InstrumentMatch>> response = apiInstance.InstrumentsSearchWithHttpInfo(instrumentSearchProperty, masteredEffectiveAt, masteredOnly, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="searchportfoliogroups"></a>
## SearchPortfolioGroups

> PagedResourceListOfPortfolioGroupSearchResult SearchPortfolioGroups(string? search = null, string? filter = null, string? sortBy = null, int? limit = null, string? page = null)

SearchPortfolioGroups: Search Portfolio Groups

Search through all portfolio groups

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
var search = "search_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfPortfolioGroupSearchResult result = apiInstance.SearchPortfolioGroups(search, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **search** | **string?** | query | optional | A parameter used for searching any portfolio group field. Wildcards(*) are supported at the end of words (e.g. &#39;Port*&#39;). Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **filter** | **string?** | query | optional | Expression to filter the result set.   For example, to filter on the Scope, use \&quot;id.scope eq &#39;string&#39;\&quot;  Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | **string?** | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. Multiple fields can be denoted by a comma e.g. -MyFieldName,AnotherFieldName,-AFurtherFieldName |
| **limit** | **int?** | query | optional | When paginating, only return this number of records |
| **page** | **string?** | query | optional | Encoded page string returned from a previous search result that will retrieve the next page of data. When this field is supplied, filter, sortBy and search fields should not be supplied. |

### Return type

[PagedResourceListOfPortfolioGroupSearchResult](PagedResourceListOfPortfolioGroupSearchResult.md)

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
<summary>Using the SearchPortfolioGroupsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPortfolioGroupSearchResult> response = apiInstance.SearchPortfolioGroupsWithHttpInfo(search, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="searchportfolios"></a>
## SearchPortfolios

> PagedResourceListOfPortfolioSearchResult SearchPortfolios(string? search = null, string? filter = null, string? sortBy = null, int? limit = null, string? page = null)

SearchPortfolios: Search Portfolios

Search through all portfolios

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
var search = "search_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfPortfolioSearchResult result = apiInstance.SearchPortfolios(search, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **search** | **string?** | query | optional | A parameter used for searching any portfolio field. Wildcards(*) are supported at the end of words (e.g. &#39;Port*&#39;). Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **filter** | **string?** | query | optional | Expression to filter the result set.   For example, to filter on the portfolio Type, use \&quot;type eq &#39;Transaction&#39;\&quot;  Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | **string?** | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. Multiple fields can be denoted by a comma e.g. -MyFieldName,AnotherFieldName,-AFurtherFieldName |
| **limit** | **int?** | query | optional | When paginating, only return this number of records |
| **page** | **string?** | query | optional | Encoded page string returned from a previous search result that will retrieve the next page of data. When this field is supplied, filter, sortBy and search fields should not be supplied. |

### Return type

[PagedResourceListOfPortfolioSearchResult](PagedResourceListOfPortfolioSearchResult.md)

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
<summary>Using the SearchPortfoliosWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPortfolioSearchResult> response = apiInstance.SearchPortfoliosWithHttpInfo(search, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="searchproperties"></a>
## SearchProperties

> PagedResourceListOfPropertyDefinitionSearchResult SearchProperties(string? search = null, string? filter = null, string? sortBy = null, int? limit = null, string? page = null)

SearchProperties: Search Property Definitions

Search through all Property Definitions

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
var search = "search_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfPropertyDefinitionSearchResult result = apiInstance.SearchProperties(search, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **search** | **string?** | query | optional | A parameter used for searching any field. Wildcards(*) are supported at the end of words (e.g. &#39;Port*&#39;). Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **filter** | **string?** | query | optional | Expression to filter the result set.   For example, to filter on the Value Type, use \&quot;valueType eq &#39;string&#39;\&quot;  Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | **string?** | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. Multiple fields can be denoted by a comma e.g. -MyFieldName,AnotherFieldName,-AFurtherFieldName |
| **limit** | **int?** | query | optional | When paginating, only return this number of records |
| **page** | **string?** | query | optional | Encoded page string returned from a previous search result that will retrieve the next page of data. When this field is supplied, filter, sortBy and search fields should not be supplied. |

### Return type

[PagedResourceListOfPropertyDefinitionSearchResult](PagedResourceListOfPropertyDefinitionSearchResult.md)

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
<summary>Using the SearchPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPropertyDefinitionSearchResult> response = apiInstance.SearchPropertiesWithHttpInfo(search, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

