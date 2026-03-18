# Finbourne.Sdk.Lusid.Api.AmortisationRuleSetsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateAmortisationRuleSet**](#createamortisationruleset) | **POST** `/api/api/amortisation/rulesets/{scope}` | [EXPERIMENTAL] CreateAmortisationRuleSet: Create an amortisation rule set. |
| [**DeleteAmortisationRuleset**](#deleteamortisationruleset) | **DELETE** `/api/api/amortisation/rulesets/{scope}/{code}` | [EXPERIMENTAL] DeleteAmortisationRuleset: Delete an amortisation rule set. |
| [**GetAmortisationRuleSet**](#getamortisationruleset) | **GET** `/api/api/amortisation/rulesets/{scope}/{code}` | [EXPERIMENTAL] GetAmortisationRuleSet: Retrieve the definition of a single amortisation rule set |
| [**ListAmortisationRuleSets**](#listamortisationrulesets) | **GET** `/api/api/amortisation/rulesets` | [EXPERIMENTAL] ListAmortisationRuleSets: List amortisation rule sets. |
| [**SetAmortisationRules**](#setamortisationrules) | **PUT** `/api/api/amortisation/rulesets/{scope}/{code}/rules` | [EXPERIMENTAL] SetAmortisationRules: Set Amortisation Rules on an existing Amortisation Rule Set. |
| [**UpdateAmortisationRuleSetDetails**](#updateamortisationrulesetdetails) | **PUT** `/api/api/amortisation/rulesets/{scope}/{code}/details` | [EXPERIMENTAL] UpdateAmortisationRuleSetDetails: Update an amortisation rule set. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AmortisationRuleSetsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
```

---

<a id="createamortisationruleset"></a>
## CreateAmortisationRuleSet

> AmortisationRuleSet CreateAmortisationRuleSet(string scope, CreateAmortisationRuleSetRequest createAmortisationRuleSetRequest)

[EXPERIMENTAL] CreateAmortisationRuleSet: Create an amortisation rule set.

Creates an amortisation rule set definition at the given effective time.  The user must be entitled to read any properties specified in each rule.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
var scope = "scope_example";  // string
var createAmortisationRuleSetRequest = new CreateAmortisationRuleSetRequest(); // CreateAmortisationRuleSetRequest
AmortisationRuleSet result = apiInstance.CreateAmortisationRuleSet(scope, createAmortisationRuleSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the rule set. |
| **createAmortisationRuleSetRequest** | [CreateAmortisationRuleSetRequest](CreateAmortisationRuleSetRequest.md) | body | **required** | The contents of the rule set. |

### Return type

[AmortisationRuleSet](AmortisationRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Create a rule set for amortisation. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateAmortisationRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AmortisationRuleSet> response = apiInstance.CreateAmortisationRuleSetWithHttpInfo(scope, createAmortisationRuleSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteamortisationruleset"></a>
## DeleteAmortisationRuleset

> DeletedEntityResponse DeleteAmortisationRuleset(string scope, string code)

[EXPERIMENTAL] DeleteAmortisationRuleset: Delete an amortisation rule set.

Deletes the rule set perpetually, including its rules.    The rule set will remain viewable at previous as at times, but it will no longer be considered applicable.    This cannot be undone.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteAmortisationRuleset(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The rule set scope. |
| **code** | **string** | path | **required** | The rule set code. |

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
<summary>Using the DeleteAmortisationRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteAmortisationRulesetWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getamortisationruleset"></a>
## GetAmortisationRuleSet

> AmortisationRuleSet GetAmortisationRuleSet(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAmortisationRuleSet: Retrieve the definition of a single amortisation rule set

Retrieves the amortisation rule set definition at the given effective and as at times.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AmortisationRuleSet result = apiInstance.GetAmortisationRuleSet(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The rule set scope. |
| **code** | **string** | path | **required** | The rule set code. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definition.  Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definition. Defaults to returning the latest version if not  specified. |

### Return type

[AmortisationRuleSet](AmortisationRuleSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Details of one rule set. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAmortisationRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AmortisationRuleSet> response = apiInstance.GetAmortisationRuleSetWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listamortisationrulesets"></a>
## ListAmortisationRuleSets

> PagedResourceListOfAmortisationRuleSet ListAmortisationRuleSets(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListAmortisationRuleSets: List amortisation rule sets.

Retrieves all amortisation rule sets at the given effective and as at times

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfAmortisationRuleSet result = apiInstance.ListAmortisationRuleSets(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definitions.  Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definitions. Defaults to returning the latest version if not  specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing AmortisationRuleSets; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For more information about filtering results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfAmortisationRuleSet](PagedResourceListOfAmortisationRuleSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of rule sets available. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAmortisationRuleSetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAmortisationRuleSet> response = apiInstance.ListAmortisationRuleSetsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setamortisationrules"></a>
## SetAmortisationRules

> AmortisationRuleSet SetAmortisationRules(string scope, string code, SetAmortisationRulesRequest setAmortisationRulesRequest)

[EXPERIMENTAL] SetAmortisationRules: Set Amortisation Rules on an existing Amortisation Rule Set.

Sets the rules on the Amortisation Rule Set, replacing the existing rules with the set provided.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var setAmortisationRulesRequest = new SetAmortisationRulesRequest(); // SetAmortisationRulesRequest
AmortisationRuleSet result = apiInstance.SetAmortisationRules(scope, code, setAmortisationRulesRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The rule set scope. |
| **code** | **string** | path | **required** | The rule set code. |
| **setAmortisationRulesRequest** | [SetAmortisationRulesRequest](SetAmortisationRulesRequest.md) | body | **required** | The contents of the rules. |

### Return type

[AmortisationRuleSet](AmortisationRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update the rules for an amortisation rule set. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetAmortisationRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AmortisationRuleSet> response = apiInstance.SetAmortisationRulesWithHttpInfo(scope, code, setAmortisationRulesRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateamortisationrulesetdetails"></a>
## UpdateAmortisationRuleSetDetails

> AmortisationRuleSet UpdateAmortisationRuleSetDetails(string scope, string code, UpdateAmortisationRuleSetDetailsRequest updateAmortisationRuleSetDetailsRequest)

[EXPERIMENTAL] UpdateAmortisationRuleSetDetails: Update an amortisation rule set.

Updates the amortisation rule set definition for all effective time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AmortisationRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateAmortisationRuleSetDetailsRequest = new UpdateAmortisationRuleSetDetailsRequest(); // UpdateAmortisationRuleSetDetailsRequest
AmortisationRuleSet result = apiInstance.UpdateAmortisationRuleSetDetails(scope, code, updateAmortisationRuleSetDetailsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The rule set scope. |
| **code** | **string** | path | **required** | The rule set code. |
| **updateAmortisationRuleSetDetailsRequest** | [UpdateAmortisationRuleSetDetailsRequest](UpdateAmortisationRuleSetDetailsRequest.md) | body | **required** | The contents of the rule set. |

### Return type

[AmortisationRuleSet](AmortisationRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update the details of an Amortisation Rule Set. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateAmortisationRuleSetDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AmortisationRuleSet> response = apiInstance.UpdateAmortisationRuleSetDetailsWithHttpInfo(scope, code, updateAmortisationRuleSetDetailsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

