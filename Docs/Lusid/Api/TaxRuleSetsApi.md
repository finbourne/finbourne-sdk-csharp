# Finbourne.Sdk.Lusid.Api.TaxRuleSetsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTaxRuleSet**](#createtaxruleset) | **POST** `/api/api/tax/rulesets` | [EXPERIMENTAL] CreateTaxRuleSet: Create a tax rule set. |
| [**DeleteTaxRuleSet**](#deletetaxruleset) | **DELETE** `/api/api/tax/rulesets/{scope}/{code}` | [EXPERIMENTAL] DeleteTaxRuleSet: Delete a tax rule set. |
| [**GetTaxRuleSet**](#gettaxruleset) | **GET** `/api/api/tax/rulesets/{scope}/{code}` | [EXPERIMENTAL] GetTaxRuleSet: Retrieve the definition of single tax rule set. |
| [**ListTaxRuleSets**](#listtaxrulesets) | **GET** `/api/api/tax/rulesets` | [EXPERIMENTAL] ListTaxRuleSets: List tax rule sets. |
| [**UpdateTaxRuleSet**](#updatetaxruleset) | **PUT** `/api/api/tax/rulesets/{scope}/{code}` | [EXPERIMENTAL] UpdateTaxRuleSet: Update a tax rule set. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TaxRuleSetsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxRuleSetsApi>();
```

---

<a id="createtaxruleset"></a>
## CreateTaxRuleSet

> TaxRuleSet CreateTaxRuleSet(CreateTaxRuleSetRequest createTaxRuleSetRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] CreateTaxRuleSet: Create a tax rule set.

Creates a tax rule set definition at the given effective time.  The user must be entitled to read any properties specified in each rule.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxRuleSetsApi>();
var createTaxRuleSetRequest = new CreateTaxRuleSetRequest(); // CreateTaxRuleSetRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
TaxRuleSet result = apiInstance.CreateTaxRuleSet(createTaxRuleSetRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createTaxRuleSetRequest** | [CreateTaxRuleSetRequest](CreateTaxRuleSetRequest.md) | body | **required** | The contents of the rule set. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the rule set will take effect.  Defaults to the current LUSID system datetime if not specified. |

### Return type

[TaxRuleSet](TaxRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Create a rule set for tax calculations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTaxRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaxRuleSet> response = apiInstance.CreateTaxRuleSetWithHttpInfo(createTaxRuleSetRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetaxruleset"></a>
## DeleteTaxRuleSet

> DeletedEntityResponse DeleteTaxRuleSet(string scope, string code)

[EXPERIMENTAL] DeleteTaxRuleSet: Delete a tax rule set.

Deletes the rule set for all effective time.    The rule set will remain viewable at previous as at times, but it will no longer be considered applicable.    This cannot be undone.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTaxRuleSet(scope, code);
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
<summary>Using the DeleteTaxRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTaxRuleSetWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettaxruleset"></a>
## GetTaxRuleSet

> TaxRuleSet GetTaxRuleSet(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetTaxRuleSet: Retrieve the definition of single tax rule set.

Retrieves the tax rule set definition at the given effective and as at times.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TaxRuleSet result = apiInstance.GetTaxRuleSet(scope, code, effectiveAt, asAt);
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

[TaxRuleSet](TaxRuleSet.md)

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
<summary>Using the GetTaxRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaxRuleSet> response = apiInstance.GetTaxRuleSetWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtaxrulesets"></a>
## ListTaxRuleSets

> ResourceListOfTaxRuleSet ListTaxRuleSets(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] ListTaxRuleSets: List tax rule sets.

Retrieves all tax rule set definitions at the given effective and as at times

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxRuleSetsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfTaxRuleSet result = apiInstance.ListTaxRuleSets(effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definitions.  Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definitions. Defaults to returning the latest version if not  specified. |

### Return type

[ResourceListOfTaxRuleSet](ResourceListOfTaxRuleSet.md)

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
<summary>Using the ListTaxRuleSetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTaxRuleSet> response = apiInstance.ListTaxRuleSetsWithHttpInfo(effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetaxruleset"></a>
## UpdateTaxRuleSet

> TaxRuleSet UpdateTaxRuleSet(string scope, string code, UpdateTaxRuleSetRequest updateTaxRuleSetRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] UpdateTaxRuleSet: Update a tax rule set.

Updates the tax rule set definition at the given effective time.  The changes will take place from this effective time until the next effective time that the rule has been updated at.  For example, consider a rule that has been created or updated effective at the first day of the coming month.  An upsert effective from the current day will only change the definition until that day.  An additional upsert at the same time (first day of the month) is required if the newly-updated definition is to supersede the future definition.  The user must be entitled to read any properties specified in each rule.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxRuleSetsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateTaxRuleSetRequest = new UpdateTaxRuleSetRequest(); // UpdateTaxRuleSetRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
TaxRuleSet result = apiInstance.UpdateTaxRuleSet(scope, code, updateTaxRuleSetRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The rule set scope. |
| **code** | **string** | path | **required** | The rule set code. |
| **updateTaxRuleSetRequest** | [UpdateTaxRuleSetRequest](UpdateTaxRuleSetRequest.md) | body | **required** | The contents of the rule set. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the rule set will take effect.  Defaults to the current LUSID system datetime if not specified. |

### Return type

[TaxRuleSet](TaxRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update rules for tax calculations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTaxRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaxRuleSet> response = apiInstance.UpdateTaxRuleSetWithHttpInfo(scope, code, updateTaxRuleSetRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

