# Finbourne.Sdk.Lusid.Api.ComplianceApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateComplianceTemplate**](#createcompliancetemplate) | **POST** `/api/api/compliance/templates/{scope}` | [EARLY ACCESS] CreateComplianceTemplate: Create a Compliance Rule Template |
| [**DeleteComplianceRule**](#deletecompliancerule) | **DELETE** `/api/api/compliance/rules/{scope}/{code}` | [EARLY ACCESS] DeleteComplianceRule: Delete compliance rule. |
| [**DeleteComplianceTemplate**](#deletecompliancetemplate) | **DELETE** `/api/api/compliance/templates/{scope}/{code}` | [EARLY ACCESS] DeleteComplianceTemplate: Delete a ComplianceRuleTemplate |
| [**GetComplianceRule**](#getcompliancerule) | **GET** `/api/api/compliance/rules/{scope}/{code}` | [EARLY ACCESS] GetComplianceRule: Get compliance rule. |
| [**GetComplianceRuleResult**](#getcomplianceruleresult) | **GET** `/api/api/compliance/runs/summary/{runScope}/{runCode}/{ruleScope}/{ruleCode}` | [EARLY ACCESS] GetComplianceRuleResult: Get detailed results for a specific rule within a compliance run. |
| [**GetComplianceTemplate**](#getcompliancetemplate) | **GET** `/api/api/compliance/templates/{scope}/{code}` | [EARLY ACCESS] GetComplianceTemplate: Get the requested compliance template. |
| [**GetDecoratedComplianceRunSummary**](#getdecoratedcompliancerunsummary) | **GET** `/api/api/compliance/runs/summary/{scope}/{code}/$decorate` | [EARLY ACCESS] GetDecoratedComplianceRunSummary: Get decorated summary results for a specific compliance run. |
| [**ListComplianceRules**](#listcompliancerules) | **GET** `/api/api/compliance/rules` | [EARLY ACCESS] ListComplianceRules: List compliance rules. |
| [**ListComplianceRuns**](#listcomplianceruns) | **GET** `/api/api/compliance/runs` | [EARLY ACCESS] ListComplianceRuns: List historical compliance run identifiers. |
| [**ListComplianceTemplates**](#listcompliancetemplates) | **GET** `/api/api/compliance/templates` | [EARLY ACCESS] ListComplianceTemplates: List compliance templates. |
| [**ListOrderBreachHistory**](#listorderbreachhistory) | **GET** `/api/api/compliance/runs/breaches` | [EXPERIMENTAL] ListOrderBreachHistory: List Historical Order Breaches. |
| [**RunCompliance**](#runcompliance) | **POST** `/api/api/compliance/runs` | [EARLY ACCESS] RunCompliance: Run a compliance check. |
| [**RunCompliancePreview**](#runcompliancepreview) | **POST** `/api/api/compliance/preview/runs` | [EARLY ACCESS] RunCompliancePreview: Run a compliance check. |
| [**UpdateComplianceTemplate**](#updatecompliancetemplate) | **PUT** `/api/api/compliance/templates/{scope}/{code}` | [EARLY ACCESS] UpdateComplianceTemplate: Update a ComplianceRuleTemplate |
| [**UpsertComplianceRule**](#upsertcompliancerule) | **POST** `/api/api/compliance/rules` | [EARLY ACCESS] UpsertComplianceRule: Upsert a compliance rule. |
| [**UpsertComplianceRunSummary**](#upsertcompliancerunsummary) | **POST** `/api/api/compliance/runs/summary` | [EARLY ACCESS] UpsertComplianceRunSummary: Upsert a compliance run summary. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ComplianceApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
```

---

<a id="createcompliancetemplate"></a>
## CreateComplianceTemplate

> ComplianceRuleTemplate CreateComplianceTemplate(string scope, CreateComplianceTemplateRequest createComplianceTemplateRequest)

[EARLY ACCESS] CreateComplianceTemplate: Create a Compliance Rule Template

Use this endpoint to create a compliance template.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var createComplianceTemplateRequest = new CreateComplianceTemplateRequest(); // CreateComplianceTemplateRequest
ComplianceRuleTemplate result = apiInstance.CreateComplianceTemplate(scope, createComplianceTemplateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Compliance Rule Template. |
| **createComplianceTemplateRequest** | [CreateComplianceTemplateRequest](CreateComplianceTemplateRequest.md) | body | **required** | Request to create a compliance rule template. |

### Return type

[ComplianceRuleTemplate](ComplianceRuleTemplate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created compliance rule template |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateComplianceTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRuleTemplate> response = apiInstance.CreateComplianceTemplateWithHttpInfo(scope, createComplianceTemplateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecompliancerule"></a>
## DeleteComplianceRule

> DeletedEntityResponse DeleteComplianceRule(string scope, string code)

[EARLY ACCESS] DeleteComplianceRule: Delete compliance rule.

Use this endpoint to delete a compliance rule. The rule will be recoverable for asat times earlier than the  delete time, but will otherwise appear to have never existed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteComplianceRule(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The compliance rule&#39;s scope. |
| **code** | **string** | path | **required** | The compliance rule&#39;s code. |

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
<summary>Using the DeleteComplianceRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteComplianceRuleWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecompliancetemplate"></a>
## DeleteComplianceTemplate

> DeletedEntityResponse DeleteComplianceTemplate(string scope, string code)

[EARLY ACCESS] DeleteComplianceTemplate: Delete a ComplianceRuleTemplate

Delete the compliance rule template uniquely defined by the scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteComplianceTemplate(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the template to be deleted. |
| **code** | **string** | path | **required** | The code of the template to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting a compliance rule template. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteComplianceTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteComplianceTemplateWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcompliancerule"></a>
## GetComplianceRule

> ComplianceRuleResponse GetComplianceRule(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] GetComplianceRule: Get compliance rule.

Use this endpoint to retrieve a single compliance rule.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ComplianceRuleResponse result = apiInstance.GetComplianceRule(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The compliance rule&#39;s scope. |
| **code** | **string** | path | **required** | The compliance rule&#39;s code. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. Asat time for query. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Compliance&#39; domain to decorate onto the rule.              These must take the format {domain}/{scope}/{code}, for example &#39;Compliance/live/UCITS&#39;. |

### Return type

[ComplianceRuleResponse](ComplianceRuleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested compliance rule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetComplianceRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRuleResponse> response = apiInstance.GetComplianceRuleWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcomplianceruleresult"></a>
## GetComplianceRuleResult

> ComplianceRuleResultV2 GetComplianceRuleResult(string runScope, string runCode, string ruleScope, string ruleCode)

[EARLY ACCESS] GetComplianceRuleResult: Get detailed results for a specific rule within a compliance run.

Specify a run scope and code from a previously run compliance check, and the scope and code of a rule within that run, to get detailed results for that rule.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var runScope = "runScope_example";  // string
var runCode = "runCode_example";  // string
var ruleScope = "ruleScope_example";  // string
var ruleCode = "ruleCode_example";  // string
ComplianceRuleResultV2 result = apiInstance.GetComplianceRuleResult(runScope, runCode, ruleScope, ruleCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runScope** | **string** | path | **required** | Required: Run Scope. |
| **runCode** | **string** | path | **required** | Required: Run Code. |
| **ruleScope** | **string** | path | **required** | Required: Rule Scope. |
| **ruleCode** | **string** | path | **required** | Required: Rule Code. |

### Return type

[ComplianceRuleResultV2](ComplianceRuleResultV2.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested compliance run summary details for a specific rule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetComplianceRuleResultWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRuleResultV2> response = apiInstance.GetComplianceRuleResultWithHttpInfo(runScope, runCode, ruleScope, ruleCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcompliancetemplate"></a>
## GetComplianceTemplate

> ComplianceTemplate GetComplianceTemplate(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetComplianceTemplate: Get the requested compliance template.

Use this endpoint to fetch a specific compliance template.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ComplianceTemplate result = apiInstance.GetComplianceTemplate(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of TemplateID |
| **code** | **string** | path | **required** | Code of TemplateID |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The time at which to get results from. Default : latest |

### Return type

[ComplianceTemplate](ComplianceTemplate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested compliance template. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetComplianceTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceTemplate> response = apiInstance.GetComplianceTemplateWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdecoratedcompliancerunsummary"></a>
## GetDecoratedComplianceRunSummary

> DecoratedComplianceRunSummary GetDecoratedComplianceRunSummary(string scope, string code)

[EARLY ACCESS] GetDecoratedComplianceRunSummary: Get decorated summary results for a specific compliance run.

Specify a run scope and code from a previously run compliance check to get an overview of result details.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DecoratedComplianceRunSummary result = apiInstance.GetDecoratedComplianceRunSummary(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Required: Run Scope. |
| **code** | **string** | path | **required** | Required: Run Code. |

### Return type

[DecoratedComplianceRunSummary](DecoratedComplianceRunSummary.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested compliance run details. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDecoratedComplianceRunSummaryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DecoratedComplianceRunSummary> response = apiInstance.GetDecoratedComplianceRunSummaryWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcompliancerules"></a>
## ListComplianceRules

> PagedResourceListOfComplianceRuleResponse ListComplianceRules(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

[EARLY ACCESS] ListComplianceRules: List compliance rules.

Use this endpoint to retrieve all compliance rules, or a subset defined by an optional filter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfComplianceRuleResponse result = apiInstance.ListComplianceRules(asAt, page, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. Asat time. |
| **page** | **string?** | query | optional | Optional. Pagination token. |
| **limit** | **int?** | query | optional | Optional. Entries per page. |
| **filter** | **string?** | query | optional | Optional. Filter. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Compliance&#39; domain to decorate onto each rule.              These must take the format {domain}/{scope}/{code}, for example &#39;Compliance/live/UCITS&#39;. If not provided will return all the entitled properties for each rule. |

### Return type

[PagedResourceListOfComplianceRuleResponse](PagedResourceListOfComplianceRuleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The list of compliance rules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListComplianceRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfComplianceRuleResponse> response = apiInstance.ListComplianceRulesWithHttpInfo(asAt, page, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcomplianceruns"></a>
## ListComplianceRuns

> PagedResourceListOfComplianceRunInfoV2 ListComplianceRuns(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EARLY ACCESS] ListComplianceRuns: List historical compliance run identifiers.

Lists RunIds of prior compliance runs, or a subset with a filter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfComplianceRunInfoV2 result = apiInstance.ListComplianceRuns(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The time at which to get results from. Default : latest |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing compliance runs from a previous call to list compliance runs.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. A list of field names to sort by, each suffixed by \&quot;ASC\&quot; or \&quot;DESC\&quot; |

### Return type

[PagedResourceListOfComplianceRunInfoV2](PagedResourceListOfComplianceRunInfoV2.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of previous compliance RunIds |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListComplianceRunsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfComplianceRunInfoV2> response = apiInstance.ListComplianceRunsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcompliancetemplates"></a>
## ListComplianceTemplates

> PagedResourceListOfComplianceTemplate ListComplianceTemplates(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EARLY ACCESS] ListComplianceTemplates: List compliance templates.

Use this endpoint to fetch a list of all available compliance template ids, or a subset using a filter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfComplianceTemplate result = apiInstance.ListComplianceTemplates(asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The time at which to get results from. Default : latest |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing compliance runs from a previous call to list compliance runs.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfComplianceTemplate](PagedResourceListOfComplianceTemplate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The list of compliance templates available. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListComplianceTemplatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfComplianceTemplate> response = apiInstance.ListComplianceTemplatesWithHttpInfo(asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listorderbreachhistory"></a>
## ListOrderBreachHistory

> PagedResourceListOfOrderBreachHistory ListOrderBreachHistory(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListOrderBreachHistory: List Historical Order Breaches.

Lists Order Ids and Run Ids of prior compliance runs, with the breached Rules Ids specified, or a subset with a filter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfOrderBreachHistory result = apiInstance.ListOrderBreachHistory(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The time at which to get results from. Default : latest |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing historical order breaches from a previous call to list historical order breaches.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. A list of field names to sort by, each suffixed by \&quot;ASC\&quot; or \&quot;DESC\&quot; |

### Return type

[PagedResourceListOfOrderBreachHistory](PagedResourceListOfOrderBreachHistory.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of previous order breaches |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListOrderBreachHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfOrderBreachHistory> response = apiInstance.ListOrderBreachHistoryWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runcompliance"></a>
## RunCompliance

> ComplianceRunInfoV2 RunCompliance(string runScope, string ruleScope, bool isPreTrade, string recipeIdScope, string recipeIdCode)

[EARLY ACCESS] RunCompliance: Run a compliance check.

Use this endpoint to run a compliance check using rules from a specific scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var runScope = "runScope_example";  // string
var ruleScope = "ruleScope_example";  // string
var isPreTrade = true;  // bool
var recipeIdScope = "recipeIdScope_example";  // string
var recipeIdCode = "recipeIdCode_example";  // string
ComplianceRunInfoV2 result = apiInstance.RunCompliance(runScope, ruleScope, isPreTrade, recipeIdScope, recipeIdCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runScope** | **string** | query | **required** | Required: Scope to save the run results in. |
| **ruleScope** | **string** | query | **required** | Required: Scope from which to select rules to be run. |
| **isPreTrade** | **bool** | query | **required** | Required: Boolean flag indicating if a run should be PreTrade (Including orders). For post-trade only, set to false |
| **recipeIdScope** | **string** | query | **required** | Required: the scope of the recipe to be used |
| **recipeIdCode** | **string** | query | **required** | Required: The code of the recipe to be used. If left blank, the default recipe will be used. |

### Return type

[ComplianceRunInfoV2](ComplianceRunInfoV2.md)

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
<summary>Using the RunComplianceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRunInfoV2> response = apiInstance.RunComplianceWithHttpInfo(runScope, ruleScope, isPreTrade, recipeIdScope, recipeIdCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runcompliancepreview"></a>
## RunCompliancePreview

> ComplianceRunInfoV2 RunCompliancePreview(string runScope, string ruleScope, string recipeIdScope, string recipeIdCode, ComplianceRunConfiguration? complianceRunConfiguration = null)

[EARLY ACCESS] RunCompliancePreview: Run a compliance check.

Use this endpoint to run a compliance check using rules from a specific scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var runScope = "runScope_example";  // string
var ruleScope = "ruleScope_example";  // string
var recipeIdScope = "recipeIdScope_example";  // string
var recipeIdCode = "recipeIdCode_example";  // string
var complianceRunConfiguration = new ComplianceRunConfiguration?(); // ComplianceRunConfiguration? (optional)
ComplianceRunInfoV2 result = apiInstance.RunCompliancePreview(runScope, ruleScope, recipeIdScope, recipeIdCode, complianceRunConfiguration);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runScope** | **string** | query | **required** | Required: Scope to save the run results in. |
| **ruleScope** | **string** | query | **required** | Required: Scope from which to select rules to be run. |
| **recipeIdScope** | **string** | query | **required** | Required: the scope of the recipe to be used |
| **recipeIdCode** | **string** | query | **required** | Required: The code of the recipe to be used. If left blank, the default recipe will be used. |
| **complianceRunConfiguration** | [ComplianceRunConfiguration?](ComplianceRunConfiguration?.md) | body | optional | Configuration options for the compliance run. |

### Return type

[ComplianceRunInfoV2](ComplianceRunInfoV2.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The identifying information of a compliance run |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunCompliancePreviewWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRunInfoV2> response = apiInstance.RunCompliancePreviewWithHttpInfo(runScope, ruleScope, recipeIdScope, recipeIdCode, complianceRunConfiguration);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecompliancetemplate"></a>
## UpdateComplianceTemplate

> ComplianceRuleTemplate UpdateComplianceTemplate(string scope, string code, UpdateComplianceTemplateRequest updateComplianceTemplateRequest)

[EARLY ACCESS] UpdateComplianceTemplate: Update a ComplianceRuleTemplate

Use this endpoint to update a specified compliance template.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateComplianceTemplateRequest = new UpdateComplianceTemplateRequest(); // UpdateComplianceTemplateRequest
ComplianceRuleTemplate result = apiInstance.UpdateComplianceTemplate(scope, code, updateComplianceTemplateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Compliance Rule Template. |
| **code** | **string** | path | **required** | The code of the Compliance Rule Template. |
| **updateComplianceTemplateRequest** | [UpdateComplianceTemplateRequest](UpdateComplianceTemplateRequest.md) | body | **required** | Request to update a compliance rule template. |

### Return type

[ComplianceRuleTemplate](ComplianceRuleTemplate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated compliance rule template |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateComplianceTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRuleTemplate> response = apiInstance.UpdateComplianceTemplateWithHttpInfo(scope, code, updateComplianceTemplateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcompliancerule"></a>
## UpsertComplianceRule

> ComplianceRuleResponse UpsertComplianceRule(UpsertComplianceRuleRequest? upsertComplianceRuleRequest = null)

[EARLY ACCESS] UpsertComplianceRule: Upsert a compliance rule.

Use this endpoint to upsert a single compliance rule. The template and variation specified must already  exist, as must the portfolio group. The parameters passed must match those required by the template variation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var upsertComplianceRuleRequest = new UpsertComplianceRuleRequest?(); // UpsertComplianceRuleRequest? (optional)
ComplianceRuleResponse result = apiInstance.UpsertComplianceRule(upsertComplianceRuleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertComplianceRuleRequest** | [UpsertComplianceRuleRequest?](UpsertComplianceRuleRequest?.md) | body | optional |  |

### Return type

[ComplianceRuleResponse](ComplianceRuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted compliance rule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertComplianceRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ComplianceRuleResponse> response = apiInstance.UpsertComplianceRuleWithHttpInfo(upsertComplianceRuleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcompliancerunsummary"></a>
## UpsertComplianceRunSummary

> UpsertComplianceRunSummaryResult UpsertComplianceRunSummary(UpsertComplianceRunSummaryRequest? upsertComplianceRunSummaryRequest = null)

[EARLY ACCESS] UpsertComplianceRunSummary: Upsert a compliance run summary.

Use this endpoint to upsert a compliance run result summary.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplianceApi>();
var upsertComplianceRunSummaryRequest = new UpsertComplianceRunSummaryRequest?(); // UpsertComplianceRunSummaryRequest? (optional)
UpsertComplianceRunSummaryResult result = apiInstance.UpsertComplianceRunSummary(upsertComplianceRunSummaryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertComplianceRunSummaryRequest** | [UpsertComplianceRunSummaryRequest?](UpsertComplianceRunSummaryRequest?.md) | body | optional |  |

### Return type

[UpsertComplianceRunSummaryResult](UpsertComplianceRunSummaryResult.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted compliance run summary. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertComplianceRunSummaryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertComplianceRunSummaryResult> response = apiInstance.UpsertComplianceRunSummaryWithHttpInfo(upsertComplianceRunSummaryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

