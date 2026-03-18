# Finbourne.Sdk.Lusid.Api.QuotesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteQuoteAccessMetadataRule**](#deletequoteaccessmetadatarule) | **DELETE** `/api/api/metadata/quotes/rules/{scope}` | [EXPERIMENTAL] DeleteQuoteAccessMetadataRule: Delete a Quote Access Metadata Rule |
| [**DeleteQuotes**](#deletequotes) | **POST** `/api/api/quotes/{scope}/$delete` | DeleteQuotes: Delete quotes |
| [**GetQuotes**](#getquotes) | **POST** `/api/api/quotes/{scope}/$get` | GetQuotes: Get quotes |
| [**GetQuotesAccessMetadataRule**](#getquotesaccessmetadatarule) | **GET** `/api/api/metadata/quotes/rules` | [EXPERIMENTAL] GetQuotesAccessMetadataRule: Get a quote access metadata rule |
| [**ListQuotes**](#listquotes) | **GET** `/api/api/quotes/{scope}/$deprecated` | [DEPRECATED] ListQuotes: List quotes |
| [**ListQuotesAccessMetadataRules**](#listquotesaccessmetadatarules) | **GET** `/api/api/metadata/quotes/rules/{scope}` | [EXPERIMENTAL] ListQuotesAccessMetadataRules: List all quote access metadata rules in a scope |
| [**ListQuotesForScope**](#listquotesforscope) | **GET** `/api/api/quotes/{scope}` | ListQuotesForScope: List quotes for scope |
| [**UpsertQuoteAccessMetadataRule**](#upsertquoteaccessmetadatarule) | **POST** `/api/api/metadata/quotes/rules/{scope}` | [EXPERIMENTAL] UpsertQuoteAccessMetadataRule: Upsert a Quote Access Metadata Rule. This creates or updates the data in LUSID. |
| [**UpsertQuotes**](#upsertquotes) | **POST** `/api/api/quotes/{scope}` | UpsertQuotes: Upsert quotes |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<QuotesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
```

---

<a id="deletequoteaccessmetadatarule"></a>
## DeleteQuoteAccessMetadataRule

> QuoteAccessMetadataRule DeleteQuoteAccessMetadataRule(string scope, string? provider = null, string? priceSource = null, string? instrumentIdType = null, string? instrumentId = null, string? quoteType = null, string? field = null, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteQuoteAccessMetadataRule: Delete a Quote Access Metadata Rule

Delete the Quote Access Metadata Rule that exactly matches the provided identifier parts

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var provider = "provider_example";  // string? (optional)
var priceSource = "priceSource_example";  // string? (optional)
var instrumentIdType = "instrumentIdType_example";  // string? (optional)
var instrumentId = "instrumentId_example";  // string? (optional)
var quoteType = "quoteType_example";  // string? (optional)
var field = "field_example";  // string? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
QuoteAccessMetadataRule result = apiInstance.DeleteQuoteAccessMetadataRule(scope, provider, priceSource, instrumentIdType, instrumentId, quoteType, field, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Quote Access Metadata Rule to retrieve. |
| **provider** | **string?** | query | optional | The Provider of the rule |
| **priceSource** | **string?** | query | optional | The PriceSource of the rule |
| **instrumentIdType** | **string?** | query | optional | The InstrumentIdType of the rule |
| **instrumentId** | **string?** | query | optional | The InstrumentId of the rule |
| **quoteType** | **string?** | query | optional | The QuoteType of the rule |
| **field** | **string?** | query | optional | The Field of the rule |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date to delete at, if this is not supplied, it will delete all data found |

### Return type

[QuoteAccessMetadataRule](QuoteAccessMetadataRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rule that has been deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteQuoteAccessMetadataRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<QuoteAccessMetadataRule> response = apiInstance.DeleteQuoteAccessMetadataRuleWithHttpInfo(scope, provider, priceSource, instrumentIdType, instrumentId, quoteType, field, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletequotes"></a>
## DeleteQuotes

> AnnulQuotesResponse DeleteQuotes(string scope, Dictionary<string, QuoteId>? requestBody = null)

DeleteQuotes: Delete quotes

Delete one or more specified quotes from a single scope. A quote is identified by its unique id which includes information about  the type of quote as well as the exact effective datetime (to the microsecond) from which it became valid.                In the request each quote must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each quote in the response.                The response will return both the collection of successfully deleted quotes, as well as those that failed.  For the failures a reason will be provided explaining why the quote could not be deleted.                It is important to always check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, QuoteId>?(); // Dictionary<string, QuoteId>? (optional)
AnnulQuotesResponse result = apiInstance.DeleteQuotes(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the quotes to delete. |
| **requestBody** | [Dictionary&lt;string, QuoteId&gt;?](QuoteId.md) | body | optional | The quotes to delete keyed by a unique correlation id. |

### Return type

[AnnulQuotesResponse](AnnulQuotesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully deleted quotes along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteQuotesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulQuotesResponse> response = apiInstance.DeleteQuotesWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getquotes"></a>
## GetQuotes

> GetQuotesResponse GetQuotes(string scope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? maxAge = null, Dictionary<string, QuoteSeriesId>? requestBody = null)

GetQuotes: Get quotes

Get one or more quotes from a single scope.                Each quote can be identified by its time invariant quote series id.                For each quote series id LUSID will return the most recent quote with respect to the provided (or default) effective datetime.                 An optional maximum age range window can be specified which defines how far back to look back for a quote from the specified effective datetime.  LUSID will return the most recent quote within this window.                In the request each quote series id must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each quote in the response.                The response will return three collections. One, the successfully retrieved quotes. Two, those that had a  valid quote series id but could not be found. Three, those that failed because LUSID could not construct a valid quote series id from the request.    For the quotes that failed or could not be found a reason will be provided explaining why the quote could not be retrieved.                It is important to always check the failed and not found sets for any unsuccessful results.  The maximum number of quotes that this method can get per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var maxAge = "maxAge_example";  // string? (optional)
var requestBody = new Dictionary<string, QuoteSeriesId>?(); // Dictionary<string, QuoteSeriesId>? (optional)
GetQuotesResponse result = apiInstance.GetQuotes(scope, effectiveAt, asAt, maxAge, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the quotes to retrieve. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the quotes. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the quotes. Defaults to return the latest version of each quote if not specified. |
| **maxAge** | **string?** | query | optional | The duration of the look back window in an ISO8601 time interval format e.g. P1Y2M3DT4H30M (1 year, 2 months, 3 days, 4 hours and 30 minutes).               This is subtracted from the provided effectiveAt datetime or cut label to generate a effective datetime window inside which a quote must exist to be retrieved. |
| **requestBody** | [Dictionary&lt;string, QuoteSeriesId&gt;?](QuoteSeriesId.md) | body | optional | The time invariant quote series ids of the quotes to retrieve. These need to be               keyed by a unique correlation id allowing the retrieved quote to be identified in the response. |

### Return type

[GetQuotesResponse](GetQuotesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved quotes along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetQuotesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetQuotesResponse> response = apiInstance.GetQuotesWithHttpInfo(scope, effectiveAt, asAt, maxAge, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getquotesaccessmetadatarule"></a>
## GetQuotesAccessMetadataRule

> QuoteAccessMetadataRule GetQuotesAccessMetadataRule(string scope, string? provider = null, string? priceSource = null, string? instrumentIdType = null, string? instrumentId = null, string? quoteType = null, string? field = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetQuotesAccessMetadataRule: Get a quote access metadata rule

Get a specific quote access metadata rule by specifying the corresponding identifier parts                No matching will be performed through this endpoint. To retrieve a rule, it is necessary to specify, exactly, the identifier of the rule

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var provider = "provider_example";  // string? (optional)
var priceSource = "priceSource_example";  // string? (optional)
var instrumentIdType = "instrumentIdType_example";  // string? (optional)
var instrumentId = "instrumentId_example";  // string? (optional)
var quoteType = "quoteType_example";  // string? (optional)
var field = "field_example";  // string? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
QuoteAccessMetadataRule result = apiInstance.GetQuotesAccessMetadataRule(scope, provider, priceSource, instrumentIdType, instrumentId, quoteType, field, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | query | **required** | The scope of the Quote Access Metadata Rule to retrieve. |
| **provider** | **string?** | query | optional | The Provider of the rule |
| **priceSource** | **string?** | query | optional | The PriceSource of the rule |
| **instrumentIdType** | **string?** | query | optional | The InstrumentIdType of the rule |
| **instrumentId** | **string?** | query | optional | The InstrumentId of the rule |
| **quoteType** | **string?** | query | optional | The QuoteType of the rule |
| **field** | **string?** | query | optional | The Field of the rule |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date of the rule |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the access metadata rule. Defaults to return the latest version if not specified. |

### Return type

[QuoteAccessMetadataRule](QuoteAccessMetadataRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Quote Access Metadata Rule or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetQuotesAccessMetadataRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<QuoteAccessMetadataRule> response = apiInstance.GetQuotesAccessMetadataRuleWithHttpInfo(scope, provider, priceSource, instrumentIdType, instrumentId, quoteType, field, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listquotes"></a>
## ListQuotes

> ResourceListOfQuote ListQuotes(string scope, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[DEPRECATED] ListQuotes: List quotes

List all the quotes from a single scope at the specified date/time  Please use ListQuotesForScope - the signature and behaviour of this endpoint will be changing to omit scope

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfQuote result = apiInstance.ListQuotes(scope, asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the quotes to list. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the quotes. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing quotes from a previous call to list quotes.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfQuote](ResourceListOfQuote.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested quotes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListQuotesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfQuote> response = apiInstance.ListQuotesWithHttpInfo(scope, asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listquotesaccessmetadatarules"></a>
## ListQuotesAccessMetadataRules

> ResourceListOfQuoteAccessMetadataRule ListQuotesAccessMetadataRules(string scope, DateTimeOffset? asAt = null)

[EXPERIMENTAL] ListQuotesAccessMetadataRules: List all quote access metadata rules in a scope

Get all the quote access metadata rules in the specified scope

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfQuoteAccessMetadataRule result = apiInstance.ListQuotesAccessMetadataRules(scope, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Quote Access Metadata Rule to retrieve. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the access metadata rule. Defaults to return the latest version if not specified. |

### Return type

[ResourceListOfQuoteAccessMetadataRule](ResourceListOfQuoteAccessMetadataRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The filtered list of results |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListQuotesAccessMetadataRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfQuoteAccessMetadataRule> response = apiInstance.ListQuotesAccessMetadataRulesWithHttpInfo(scope, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listquotesforscope"></a>
## ListQuotesForScope

> ResourceListOfQuote ListQuotesForScope(string scope, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

ListQuotesForScope: List quotes for scope

List all the quotes from a single scope at the specified date/time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfQuote result = apiInstance.ListQuotesForScope(scope, asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the quotes to list. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the quotes. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing quotes from a previous call to list quotes.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfQuote](ResourceListOfQuote.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested quotes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListQuotesForScopeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfQuote> response = apiInstance.ListQuotesForScopeWithHttpInfo(scope, asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertquoteaccessmetadatarule"></a>
## UpsertQuoteAccessMetadataRule

> QuoteAccessMetadataRule UpsertQuoteAccessMetadataRule(string scope, UpsertQuoteAccessMetadataRuleRequest upsertQuoteAccessMetadataRuleRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EXPERIMENTAL] UpsertQuoteAccessMetadataRule: Upsert a Quote Access Metadata Rule. This creates or updates the data in LUSID.

Update or insert one Quote Access Metadata Rule in a single scope. An item will be updated if it already exists  and inserted if it does not.    The response will return the successfully updated or inserted Quote Access Metadata Rule or failure message if unsuccessful    It is important to always check to verify success (or failure).                Multiple rules for a key can exists with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var upsertQuoteAccessMetadataRuleRequest = new UpsertQuoteAccessMetadataRuleRequest(); // UpsertQuoteAccessMetadataRuleRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
QuoteAccessMetadataRule result = apiInstance.UpsertQuoteAccessMetadataRule(scope, upsertQuoteAccessMetadataRuleRequest, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to use when updating or inserting the Quote Access Metadata Rule. |
| **upsertQuoteAccessMetadataRuleRequest** | [UpsertQuoteAccessMetadataRuleRequest](UpsertQuoteAccessMetadataRuleRequest.md) | body | **required** | The Quote Access Metadata Rule to update or insert |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The date this rule will effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[QuoteAccessMetadataRule](QuoteAccessMetadataRule.md)

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
<summary>Using the UpsertQuoteAccessMetadataRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<QuoteAccessMetadataRule> response = apiInstance.UpsertQuoteAccessMetadataRuleWithHttpInfo(scope, upsertQuoteAccessMetadataRuleRequest, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertquotes"></a>
## UpsertQuotes

> UpsertQuotesResponse UpsertQuotes(string scope, Dictionary<string, UpsertQuoteRequest>? requestBody = null)

UpsertQuotes: Upsert quotes

Update or insert one or more quotes in a single scope. A quote will be updated if it already exists  and inserted if it does not.                In the request each quote must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each quote in the response.                The response will return both the collection of successfully updated or inserted quotes, as well as those that failed.  For the failures a reason will be provided explaining why the quote could not be updated or inserted.                It is important to always check the failed set for any unsuccessful results.  The maximum number of quotes that this method can upsert per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<QuotesApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, UpsertQuoteRequest>?(); // Dictionary<string, UpsertQuoteRequest>? (optional)
UpsertQuotesResponse result = apiInstance.UpsertQuotes(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to use when updating or inserting the quotes. |
| **requestBody** | [Dictionary&lt;string, UpsertQuoteRequest&gt;?](UpsertQuoteRequest.md) | body | optional | The quotes to update or insert keyed by a unique correlation id. |

### Return type

[UpsertQuotesResponse](UpsertQuotesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted quotes along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertQuotesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertQuotesResponse> response = apiInstance.UpsertQuotesWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

