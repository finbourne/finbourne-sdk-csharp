# Finbourne.Sdk.Lusid.Api.ReconciliationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateScheduledReconciliation**](#createscheduledreconciliation) | **POST** `/api/api/portfolios/$scheduledReconciliations/{scope}` | [EXPERIMENTAL] CreateScheduledReconciliation: Create a scheduled reconciliation |
| [**DeleteReconciliation**](#deletereconciliation) | **DELETE** `/api/api/portfolios/$scheduledReconciliations/{scope}/{code}` | [EXPERIMENTAL] DeleteReconciliation: Delete scheduled reconciliation |
| [**DeleteReconciliationMapping**](#deletereconciliationmapping) | **DELETE** `/api/api/portfolios/mapping/{scope}/{code}` | [EARLY ACCESS] DeleteReconciliationMapping: Delete a mapping |
| [**GetReconciliation**](#getreconciliation) | **GET** `/api/api/portfolios/$scheduledReconciliations/{scope}/{code}` | [EXPERIMENTAL] GetReconciliation: Get scheduled reconciliation |
| [**GetReconciliationMapping**](#getreconciliationmapping) | **GET** `/api/api/portfolios/mapping/{scope}/{code}` | [EARLY ACCESS] GetReconciliationMapping: Get a mapping |
| [**ListReconciliationMappings**](#listreconciliationmappings) | **GET** `/api/api/portfolios/mapping` | [EARLY ACCESS] ListReconciliationMappings: List the reconciliation mappings |
| [**ListReconciliations**](#listreconciliations) | **GET** `/api/api/portfolios/$scheduledReconciliations` | [EXPERIMENTAL] ListReconciliations: List scheduled reconciliations |
| [**ReconcileGeneric**](#reconcilegeneric) | **POST** `/api/api/portfolios/$reconcileGeneric` | ReconcileGeneric: Reconcile either holdings or valuations performed on one or two sets of holdings using one or two configuration recipes.                The output is configurable for various types of comparisons, to allow tolerances on numerical and date-time data or case-insensitivity on strings,  and elision of resulting differences where they are &#39;empty&#39; or null or zero. |
| [**ReconcileHoldings**](#reconcileholdings) | **POST** `/api/api/portfolios/$reconcileholdings` | [EARLY ACCESS] ReconcileHoldings: Reconcile portfolio holdings |
| [**ReconcileInline**](#reconcileinline) | **POST** `/api/api/portfolios/$reconcileInline` | ReconcileInline: Reconcile valuations performed on one or two sets of inline instruments using one or two configuration recipes. |
| [**ReconcileTransactions**](#reconciletransactions) | **POST** `/api/api/portfolios/$reconcileTransactions` | [EARLY ACCESS] ReconcileTransactions: Perform a Transactions Reconciliation. |
| [**ReconcileTransactionsV2**](#reconciletransactionsv2) | **POST** `/api/api/portfolios/$reconcileTransactionsV2` | [EXPERIMENTAL] ReconcileTransactionsV2: Perform a Transactions Reconciliation. |
| [**ReconcileValuation**](#reconcilevaluation) | **POST** `/api/api/portfolios/$reconcileValuation` | ReconcileValuation: Reconcile valuations performed on one or two sets of holdings using one or two configuration recipes. |
| [**UpdateReconciliation**](#updatereconciliation) | **POST** `/api/api/portfolios/$scheduledReconciliations/{scope}/{code}` | [EXPERIMENTAL] UpdateReconciliation: Update scheduled reconciliation |
| [**UpsertReconciliationMapping**](#upsertreconciliationmapping) | **POST** `/api/api/portfolios/mapping` | [EARLY ACCESS] UpsertReconciliationMapping: Create or update a mapping |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ReconciliationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
```

---

<a id="createscheduledreconciliation"></a>
## CreateScheduledReconciliation

> Reconciliation CreateScheduledReconciliation(string scope, CreateReconciliationRequest? createReconciliationRequest = null)

[EXPERIMENTAL] CreateScheduledReconciliation: Create a scheduled reconciliation

Create a scheduled reconciliation for the given request

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var scope = "scope_example";  // string
var createReconciliationRequest = new CreateReconciliationRequest?(); // CreateReconciliationRequest? (optional)
Reconciliation result = apiInstance.CreateScheduledReconciliation(scope, createReconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the reconciliation |
| **createReconciliationRequest** | [CreateReconciliationRequest?](CreateReconciliationRequest?.md) | body | optional | The definition of the reconciliation |

### Return type

[Reconciliation](Reconciliation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created scheduled reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateScheduledReconciliationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Reconciliation> response = apiInstance.CreateScheduledReconciliationWithHttpInfo(scope, createReconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletereconciliation"></a>
## DeleteReconciliation

> DeletedEntityResponse DeleteReconciliation(string scope, string code)

[EXPERIMENTAL] DeleteReconciliation: Delete scheduled reconciliation

Delete the given scheduled reconciliation

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteReconciliation(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the scheduled reconciliation |
| **code** | **string** | path | **required** | The code of the scheduled reconciliation |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The reconciliation at the requested as at was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteReconciliationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteReconciliationWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletereconciliationmapping"></a>
## DeleteReconciliationMapping

> string DeleteReconciliationMapping(string scope, string code)

[EARLY ACCESS] DeleteReconciliationMapping: Delete a mapping

Deletes the mapping identified by the scope and code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
string result = apiInstance.DeleteReconciliationMapping(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the mapping. |
| **code** | **string** | path | **required** | The code fof the mapping. |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A string specifying the scope and code that were deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteReconciliationMappingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.DeleteReconciliationMappingWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreconciliation"></a>
## GetReconciliation

> Reconciliation GetReconciliation(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetReconciliation: Get scheduled reconciliation

Get the requested scheduled reconciliation

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Reconciliation result = apiInstance.GetReconciliation(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the scheduled reconciliation |
| **code** | **string** | path | **required** | The code of the scheduled reconciliation |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the scheduled reconciliation. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the scheduled reconciliation. Defaults to returning the latest version of the reconciliation if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Reconciliation&#39; property domain to decorate onto the reconciliation.              These must take the form {domain}/{scope}/{code}, for example &#39;Reconciliation/Broker/Id&#39;. |

### Return type

[Reconciliation](Reconciliation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested scheduled reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReconciliationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Reconciliation> response = apiInstance.GetReconciliationWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreconciliationmapping"></a>
## GetReconciliationMapping

> Mapping GetReconciliationMapping(string scope, string code)

[EARLY ACCESS] GetReconciliationMapping: Get a mapping

Gets a mapping identified by the given scope and code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
Mapping result = apiInstance.GetReconciliationMapping(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the mapping. |
| **code** | **string** | path | **required** | The code of the mapping. |

### Return type

[Mapping](Mapping.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The mapping with the specified scope/code. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReconciliationMappingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Mapping> response = apiInstance.GetReconciliationMappingWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listreconciliationmappings"></a>
## ListReconciliationMappings

> ResourceListOfMapping ListReconciliationMappings(string? reconciliationType = null)

[EARLY ACCESS] ListReconciliationMappings: List the reconciliation mappings

Lists all mappings this user is entitled to see

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var reconciliationType = "reconciliationType_example";  // string? (optional)
ResourceListOfMapping result = apiInstance.ListReconciliationMappings(reconciliationType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **reconciliationType** | **string?** | query | optional | Optional parameter to specify which type of mappings should be returned.  Defaults to Transaction if not provided. |

### Return type

[ResourceListOfMapping](ResourceListOfMapping.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The mappings that the caller has access to. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListReconciliationMappingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfMapping> response = apiInstance.ListReconciliationMappingsWithHttpInfo(reconciliationType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listreconciliations"></a>
## ListReconciliations

> PagedResourceListOfReconciliation ListReconciliations(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListReconciliations: List scheduled reconciliations

List all the scheduled reconciliations matching particular criteria

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfReconciliation result = apiInstance.ListReconciliations(effectiveAt, asAt, page, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the reconciliation. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the reconciliation. Defaults to returning the latest version              of each reconciliation if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing reconciliations; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the reconciliation type, specify \&quot;id.Code eq &#39;001&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Reconciliation&#39; domain to decorate onto each reconciliation.              These must take the format {domain}/{scope}/{code}, for example &#39;Reconciliation/Broker/Id&#39;. |

### Return type

[PagedResourceListOfReconciliation](PagedResourceListOfReconciliation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of all scheduled reconciliations |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListReconciliationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfReconciliation> response = apiInstance.ListReconciliationsWithHttpInfo(effectiveAt, asAt, page, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reconcilegeneric"></a>
## ReconcileGeneric

> ReconciliationResponse ReconcileGeneric(ReconciliationRequest? reconciliationRequest = null)

ReconcileGeneric: Reconcile either holdings or valuations performed on one or two sets of holdings using one or two configuration recipes.                The output is configurable for various types of comparisons, to allow tolerances on numerical and date-time data or case-insensitivity on strings,  and elision of resulting differences where they are 'empty' or null or zero.

Perform evaluation of one or two set of holdings (a portfolio of instruments) using one or two (potentially different) configuration recipes.  Produce a breakdown of the resulting differences in evaluation that can be iterated through.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var reconciliationRequest = new ReconciliationRequest?(); // ReconciliationRequest? (optional)
ReconciliationResponse result = apiInstance.ReconcileGeneric(reconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **reconciliationRequest** | [ReconciliationRequest?](ReconciliationRequest?.md) | body | optional | The specifications of the inputs to the reconciliation |

### Return type

[ReconciliationResponse](ReconciliationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReconcileGenericWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReconciliationResponse> response = apiInstance.ReconcileGenericWithHttpInfo(reconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reconcileholdings"></a>
## ReconcileHoldings

> ResourceListOfReconciliationBreak ReconcileHoldings(List<string>? sortBy = null, int? limit = null, string? filter = null, PortfoliosReconciliationRequest? portfoliosReconciliationRequest = null)

[EARLY ACCESS] ReconcileHoldings: Reconcile portfolio holdings

Reconcile the holdings of two portfolios.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var portfoliosReconciliationRequest = new PortfoliosReconciliationRequest?(); // PortfoliosReconciliationRequest? (optional)
ResourceListOfReconciliationBreak result = apiInstance.ReconcileHoldings(sortBy, limit, filter, portfoliosReconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.              For example, to filter on the left portfolio Code, use \&quot;left.portfolioId.code eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **portfoliosReconciliationRequest** | [PortfoliosReconciliationRequest?](PortfoliosReconciliationRequest?.md) | body | optional | The specifications of the inputs to the reconciliation |

### Return type

[ResourceListOfReconciliationBreak](ResourceListOfReconciliationBreak.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReconcileHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfReconciliationBreak> response = apiInstance.ReconcileHoldingsWithHttpInfo(sortBy, limit, filter, portfoliosReconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reconcileinline"></a>
## ReconcileInline

> ListAggregationReconciliation ReconcileInline(InlineValuationsReconciliationRequest? inlineValuationsReconciliationRequest = null)

ReconcileInline: Reconcile valuations performed on one or two sets of inline instruments using one or two configuration recipes.

Perform valuation of one or two set of inline instruments using different one or two configuration recipes. Produce a breakdown of the resulting differences in valuation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var inlineValuationsReconciliationRequest = new InlineValuationsReconciliationRequest?(); // InlineValuationsReconciliationRequest? (optional)
ListAggregationReconciliation result = apiInstance.ReconcileInline(inlineValuationsReconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **inlineValuationsReconciliationRequest** | [InlineValuationsReconciliationRequest?](InlineValuationsReconciliationRequest?.md) | body | optional | The specifications of the inputs to the reconciliation |

### Return type

[ListAggregationReconciliation](ListAggregationReconciliation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReconcileInlineWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ListAggregationReconciliation> response = apiInstance.ReconcileInlineWithHttpInfo(inlineValuationsReconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reconciletransactions"></a>
## ReconcileTransactions

> TransactionsReconciliationsResponse ReconcileTransactions(TransactionReconciliationRequest? transactionReconciliationRequest = null)

[EARLY ACCESS] ReconcileTransactions: Perform a Transactions Reconciliation.

Evaluates two sets of transactions to determine which transactions from each set likely match  using the rules of a specified mapping.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var transactionReconciliationRequest = new TransactionReconciliationRequest?(); // TransactionReconciliationRequest? (optional)
TransactionsReconciliationsResponse result = apiInstance.ReconcileTransactions(transactionReconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **transactionReconciliationRequest** | [TransactionReconciliationRequest?](TransactionReconciliationRequest?.md) | body | optional |  |

### Return type

[TransactionsReconciliationsResponse](TransactionsReconciliationsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The transaction reconciliation data for the supplied portfolios. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReconcileTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionsReconciliationsResponse> response = apiInstance.ReconcileTransactionsWithHttpInfo(transactionReconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reconciletransactionsv2"></a>
## ReconcileTransactionsV2

> ReconciliationResponse ReconcileTransactionsV2(TransactionReconciliationRequestV2? transactionReconciliationRequestV2 = null)

[EXPERIMENTAL] ReconcileTransactionsV2: Perform a Transactions Reconciliation.

Evaluates two sets of transactions to determine which transactions from each set likely match  using the rules of a specified mapping.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var transactionReconciliationRequestV2 = new TransactionReconciliationRequestV2?(); // TransactionReconciliationRequestV2? (optional)
ReconciliationResponse result = apiInstance.ReconcileTransactionsV2(transactionReconciliationRequestV2);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **transactionReconciliationRequestV2** | [TransactionReconciliationRequestV2?](TransactionReconciliationRequestV2?.md) | body | optional |  |

### Return type

[ReconciliationResponse](ReconciliationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReconcileTransactionsV2WithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReconciliationResponse> response = apiInstance.ReconcileTransactionsV2WithHttpInfo(transactionReconciliationRequestV2);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reconcilevaluation"></a>
## ReconcileValuation

> ListAggregationReconciliation ReconcileValuation(ValuationsReconciliationRequest? valuationsReconciliationRequest = null)

ReconcileValuation: Reconcile valuations performed on one or two sets of holdings using one or two configuration recipes.

Perform valuation of one or two set of holdings using different one or two configuration recipes. Produce a breakdown of the resulting differences in valuation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var valuationsReconciliationRequest = new ValuationsReconciliationRequest?(); // ValuationsReconciliationRequest? (optional)
ListAggregationReconciliation result = apiInstance.ReconcileValuation(valuationsReconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **valuationsReconciliationRequest** | [ValuationsReconciliationRequest?](ValuationsReconciliationRequest?.md) | body | optional | The specifications of the inputs to the reconciliation |

### Return type

[ListAggregationReconciliation](ListAggregationReconciliation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReconcileValuationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ListAggregationReconciliation> response = apiInstance.ReconcileValuationWithHttpInfo(valuationsReconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatereconciliation"></a>
## UpdateReconciliation

> Reconciliation UpdateReconciliation(string scope, string code, UpdateReconciliationRequest? updateReconciliationRequest = null)

[EXPERIMENTAL] UpdateReconciliation: Update scheduled reconciliation

Update a given scheduled reconciliation

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateReconciliationRequest = new UpdateReconciliationRequest?(); // UpdateReconciliationRequest? (optional)
Reconciliation result = apiInstance.UpdateReconciliation(scope, code, updateReconciliationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the reconciliation to be updated |
| **code** | **string** | path | **required** | The code of the reconciliation to be updated |
| **updateReconciliationRequest** | [UpdateReconciliationRequest?](UpdateReconciliationRequest?.md) | body | optional | The updated definition of the reconciliation |

### Return type

[Reconciliation](Reconciliation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated scheduled reconciliation |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateReconciliationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Reconciliation> response = apiInstance.UpdateReconciliationWithHttpInfo(scope, code, updateReconciliationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreconciliationmapping"></a>
## UpsertReconciliationMapping

> Mapping UpsertReconciliationMapping(Mapping? mapping = null)

[EARLY ACCESS] UpsertReconciliationMapping: Create or update a mapping

If no mapping exists with the specified scope and code will create a new one.  Else will update the existing mapping

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReconciliationsApi>();
var mapping = new Mapping?(); // Mapping? (optional)
Mapping result = apiInstance.UpsertReconciliationMapping(mapping);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **mapping** | [Mapping?](Mapping?.md) | body | optional | The mapping to be created / updated. |

### Return type

[Mapping](Mapping.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created / updated mapping. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReconciliationMappingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Mapping> response = apiInstance.UpsertReconciliationMappingWithHttpInfo(mapping);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

