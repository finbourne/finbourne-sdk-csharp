# Finbourne.Sdk.Lusid.Api.LegacyComplianceApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteLegacyComplianceRule**](#deletelegacycompliancerule) | **DELETE** `/api/api/legacy/compliance/rules/{scope}/{code}` | [EXPERIMENTAL] DeleteLegacyComplianceRule: Deletes a compliance rule. |
| [**GetLegacyBreachedOrdersInfo**](#getlegacybreachedordersinfo) | **GET** `/api/api/legacy/compliance/runs/breached/{runId}` | [EXPERIMENTAL] GetLegacyBreachedOrdersInfo: Get the Ids of Breached orders in a given compliance run and the corresponding list of rules that could have caused it. |
| [**GetLegacyComplianceRule**](#getlegacycompliancerule) | **GET** `/api/api/legacy/compliance/rules/{scope}/{code}` | [EXPERIMENTAL] GetLegacyComplianceRule: Retrieve the definition of single compliance rule. |
| [**GetLegacyComplianceRunResults**](#getlegacycompliancerunresults) | **GET** `/api/api/legacy/compliance/runs/{runId}` | [EXPERIMENTAL] GetLegacyComplianceRunResults: Get the details of a single compliance run. |
| [**ListLegacyComplianceRules**](#listlegacycompliancerules) | **GET** `/api/api/legacy/compliance/rules` | [EXPERIMENTAL] ListLegacyComplianceRules: List compliance rules, with optional filtering. |
| [**ListLegacyComplianceRunInfo**](#listlegacycomplianceruninfo) | **GET** `/api/api/legacy/compliance/runs` | [EXPERIMENTAL] ListLegacyComplianceRunInfo: List historical compliance run ids. |
| [**RunLegacyCompliance**](#runlegacycompliance) | **POST** `/api/api/legacy/compliance/runs` | [EXPERIMENTAL] RunLegacyCompliance: Kick off the compliance check process |
| [**UpsertLegacyComplianceRules**](#upsertlegacycompliancerules) | **POST** `/api/api/legacy/compliance/rules` | [EXPERIMENTAL] UpsertLegacyComplianceRules: Upsert compliance rules. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<LegacyComplianceApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
```

---

<a id="deletelegacycompliancerule"></a>
## DeleteLegacyComplianceRule

> DeletedEntityResponse DeleteLegacyComplianceRule(string scope, string code)

[EXPERIMENTAL] DeleteLegacyComplianceRule: Deletes a compliance rule.

Deletes the rule for all effective time.                The rule will remain viewable at previous as at times, and as part of the results of compliance runs, but it  will no longer be considered in new compliance runs.                This cannot be undone.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteLegacyComplianceRule(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The compliance rule scope. |
| **code** | **string** | path | **required** | The compliance rule code. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

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
<summary>Using the DeleteLegacyComplianceRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteLegacyComplianceRuleWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegacybreachedordersinfo"></a>
## GetLegacyBreachedOrdersInfo

> ResourceListOfComplianceBreachedOrderInfo GetLegacyBreachedOrdersInfo(string runId, string? orderScope = null, string? orderCode = null, int? limit = null)

[EXPERIMENTAL] GetLegacyBreachedOrdersInfo: Get the Ids of Breached orders in a given compliance run and the corresponding list of rules that could have caused it.

Use this endpoint to get a list or breached orders and the set of rules that may have caused the breach.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var runId = "runId_example";  // string
var orderScope = "orderScope_example";  // string? (optional)
var orderCode = "orderCode_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfComplianceBreachedOrderInfo result = apiInstance.GetLegacyBreachedOrdersInfo(runId, orderScope, orderCode, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The RunId that the results should be checked for |
| **orderScope** | **string?** | query | optional | Optional. Find rules related to a specific order by providing an Order Scope/Code combination |
| **orderCode** | **string?** | query | optional | Optional. Find rules related to a specific order by providing an Order Scope/Code combination |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |

### Return type

[ResourceListOfComplianceBreachedOrderInfo](ResourceListOfComplianceBreachedOrderInfo.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The potentially breached orders and their rules from a specific compliance run |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegacyBreachedOrdersInfoWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfComplianceBreachedOrderInfo> response = apiInstance.GetLegacyBreachedOrdersInfoWithHttpInfo(runId, orderScope, orderCode, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegacycompliancerule"></a>
## GetLegacyComplianceRule

> ComplianceRule GetLegacyComplianceRule(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetLegacyComplianceRule: Retrieve the definition of single compliance rule.

Retrieves the compliance rule definition at the given effective and as at times.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ComplianceRule result = apiInstance.GetLegacyComplianceRule(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The compliance rule scope. |
| **code** | **string** | path | **required** | The compliance rule code. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definition. Defaults to the current LUSID  system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definition. Defaults to returning the latest version if not  specified. |

### Return type

[ComplianceRule](ComplianceRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Details of one compliance rule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegacyComplianceRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRule> response = apiInstance.GetLegacyComplianceRuleWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegacycompliancerunresults"></a>
## GetLegacyComplianceRunResults

> ResourceListOfComplianceRuleResult GetLegacyComplianceRunResults(string runId, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] GetLegacyComplianceRunResults: Get the details of a single compliance run.

Use this endpoint to fetch the detail associated with a specific compliance run, including a breakdown  of the passing state of each rule, portfolio combination.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var runId = "runId_example";  // string
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfComplianceRuleResult result = apiInstance.GetLegacyComplianceRunResults(runId, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The unique identifier of the compliance run requested. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing compliance rule results from a previous call to list compliance rule result.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfComplianceRuleResult](ResourceListOfComplianceRuleResult.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rule results of a specific compliance run |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegacyComplianceRunResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfComplianceRuleResult> response = apiInstance.GetLegacyComplianceRunResultsWithHttpInfo(runId, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listlegacycompliancerules"></a>
## ListLegacyComplianceRules

> ResourceListOfComplianceRule ListLegacyComplianceRules(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListLegacyComplianceRules: List compliance rules, with optional filtering.

For more information about filtering results,  see https://support.lusid.com/knowledgebase/article/KA-01914.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfComplianceRule result = apiInstance.ListLegacyComplianceRules(effectiveAt, asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definitions. Defaults to the current LUSID  system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definitions. Defaults to returning the latest version if not  specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing entities; this value is returned from the previous call. If  a pagination token is provided, the filter, effectiveAt and asAt fields must not have changed since the  original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. |

### Return type

[ResourceListOfComplianceRule](ResourceListOfComplianceRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A filtered list of compliance rules available. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListLegacyComplianceRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfComplianceRule> response = apiInstance.ListLegacyComplianceRulesWithHttpInfo(effectiveAt, asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listlegacycomplianceruninfo"></a>
## ListLegacyComplianceRunInfo

> ResourceListOfComplianceRunInfo ListLegacyComplianceRunInfo(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListLegacyComplianceRunInfo: List historical compliance run ids.

Use this endpoint to fetch a list of all historical compliance runs.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfComplianceRunInfo result = apiInstance.ListLegacyComplianceRunInfo(asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The time at which to get results from. Default : latest |
| **page** | **string?** | query | optional | The pagination token to use to continue listing compliance runs from a previous call to list compliance runs.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfComplianceRunInfo](ResourceListOfComplianceRunInfo.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The List of IDs and information for all compliance runs completed |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListLegacyComplianceRunInfoWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfComplianceRunInfo> response = apiInstance.ListLegacyComplianceRunInfoWithHttpInfo(asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runlegacycompliance"></a>
## RunLegacyCompliance

> ComplianceRunInfo RunLegacyCompliance(bool isPreTrade, string recipeIdScope, string? recipeIdCode = null, bool? byTaxlots = null)

[EXPERIMENTAL] RunLegacyCompliance: Kick off the compliance check process

Use this endpoint to fetch the start a compliance run, based on a pre-set mapping file.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var isPreTrade = true;  // bool
var recipeIdScope = "recipeIdScope_example";  // string
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var byTaxlots = true;  // bool? (optional)
ComplianceRunInfo result = apiInstance.RunLegacyCompliance(isPreTrade, recipeIdScope, recipeIdCode, byTaxlots);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **isPreTrade** | **bool** | query | **required** | Required: Boolean flag indicating if a run should be PreTrade (Including orders). For post-trade only, set to false |
| **recipeIdScope** | **string** | query | **required** | Required: the scope of the recipe to be used |
| **recipeIdCode** | **string?** | query | optional | Optional: The code of the recipe to be used. If left blank, the default recipe will be used. |
| **byTaxlots** | **bool?** | query | optional | Optional. |

### Return type

[ComplianceRunInfo](ComplianceRunInfo.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The identifying information of a compliance run |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunLegacyComplianceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRunInfo> response = apiInstance.RunLegacyComplianceWithHttpInfo(isPreTrade, recipeIdScope, recipeIdCode, byTaxlots);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertlegacycompliancerules"></a>
## UpsertLegacyComplianceRules

> ComplianceRuleUpsertResponse UpsertLegacyComplianceRules(Dictionary<string, ComplianceRuleUpsertRequest> requestBody, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] UpsertLegacyComplianceRules: Upsert compliance rules.

To upsert a new rule, the code field must be left empty, a code will then be assigned and returned as part  of the response. To update an existing rule, include the rule code. It is possible to both create and update  compliance rules in the same request.                The upsert is transactional - either all create/update operations will succeed or none of them will.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegacyComplianceApi>();
var requestBody = new Dictionary<string, ComplianceRuleUpsertRequest>(); // Dictionary<string, ComplianceRuleUpsertRequest>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
ComplianceRuleUpsertResponse result = apiInstance.UpsertLegacyComplianceRules(requestBody, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, ComplianceRuleUpsertRequest&gt;](ComplianceRuleUpsertRequest.md) | body | **required** | A dictionary of upsert request identifiers to rule upsert requests. The request               identifiers are valid for the request only and can be used to link the upserted compliance rule to the code               of a created compliance rule. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the rule will take effect. Defaults to the current LUSID  system datetime if not specified. In the case of an update, the changes will take place from this effective  time until the next effective time that the rule as been upserted at. For example, consider a rule that  already exists, and has previously had an update applied so that the definition will change on the first day  of the coming month. An upsert effective from the current day will only change the definition until the  first day of the coming month. An additional upsert at the same time (first day of the month) is required  if the newly-updated definition is to supersede the future definition. |

### Return type

[ComplianceRuleUpsertResponse](ComplianceRuleUpsertResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Upsert compliance rules. New compliance rules must have an empty code field. Where a codeis given, this rule must already exist and will be updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertLegacyComplianceRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRuleUpsertResponse> response = apiInstance.UpsertLegacyComplianceRulesWithHttpInfo(requestBody, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

