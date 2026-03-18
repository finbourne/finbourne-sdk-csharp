# Finbourne.Sdk.Lusid.Api.TransactionFeesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteTransactionFeeRule**](#deletetransactionfeerule) | **DELETE** `/api/api/transactions/fees/rules/{code}` | DeleteTransactionFeeRule: Deletes a fee rule. |
| [**GetApplicableTransactionFees**](#getapplicabletransactionfees) | **POST** `/api/api/transactions/fees/$GetApplicableFees` | GetApplicableTransactionFees: Get the Fees and Commissions that may be applicable to a transaction. |
| [**GetTransactionFeeRule**](#gettransactionfeerule) | **GET** `/api/api/transactions/fees/rules/{code}` | GetTransactionFeeRule: Retrieve the definition of single fee rule. |
| [**ListTransactionFeeRules**](#listtransactionfeerules) | **GET** `/api/api/transactions/fees/rules` | ListTransactionFeeRules: List fee rules, with optional filtering. |
| [**UpsertTransactionFeeRules**](#upserttransactionfeerules) | **POST** `/api/api/transactions/fees/rules` | UpsertTransactionFeeRules: Upsert fee rules. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransactionFeesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeesApi>();
```

---

<a id="deletetransactionfeerule"></a>
## DeleteTransactionFeeRule

> DeletedEntityResponse DeleteTransactionFeeRule(string code)

DeleteTransactionFeeRule: Deletes a fee rule.

Deletes the rule for all effective time.    The rule will remain viewable at previous as at times, but it will no longer be considered by  GetApplicableFees.    This cannot be undone.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeesApi>();
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTransactionFeeRule(code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The fee rule code. |

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
<summary>Using the DeleteTransactionFeeRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransactionFeeRuleWithHttpInfo(code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getapplicabletransactionfees"></a>
## GetApplicableTransactionFees

> ResourceListOfFeeRule GetApplicableTransactionFees(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? instrumentIdentifierType = null, string? instrumentIdentifier = null, string? portfolioScope = null, string? portfolioCode = null, Dictionary<string, string>? requestBody = null)

GetApplicableTransactionFees: Get the Fees and Commissions that may be applicable to a transaction.

Additionally, matching can be based on the instrument's properties, its portfolio properties, and any additional property keys present in the data file.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeesApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var instrumentIdentifierType = "instrumentIdentifierType_example";  // string? (optional)
var instrumentIdentifier = "instrumentIdentifier_example";  // string? (optional)
var portfolioScope = "portfolioScope_example";  // string? (optional)
var portfolioCode = "portfolioCode_example";  // string? (optional)
var requestBody = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
ResourceListOfFeeRule result = apiInstance.GetApplicableTransactionFees(effectiveAt, asAt, instrumentIdentifierType, instrumentIdentifier, portfolioScope, portfolioCode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to match rule definitions. Defaults to the current LUSID  system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to match rule definitions. Defaults to returning the latest version if not  specified. |
| **instrumentIdentifierType** | **string?** | query | optional | Optional. The unique identifier type to use, eg &#39;Figi&#39; or &#39;LusidInstrumentId&#39;. |
| **instrumentIdentifier** | **string?** | query | optional | Optional. The Instrument Identifier to get properties for. |
| **portfolioScope** | **string?** | query | optional | Optional. The scope of the portfolio to fetch properties from. |
| **portfolioCode** | **string?** | query | optional | Optional. The code of the portfolio to fetch properties from. |
| **requestBody** | [Dictionary&lt;string, string&gt;?](string.md) | body | optional | Any other property keys or fields, including the top-level fields of the              fee rule (e.g. \&quot;ExecutionBroker\&quot; and \&quot;SettlementCurrency\&quot; ) and those defined in AdditionalKeys, along with              their corresponding values that should be matched for fees. Eg. \&quot;Instrument/default/Name&#x3D;exampleValue\&quot; or              \&quot;AdditionalKey2&#x3D;Value2\&quot;. |

### Return type

[ResourceListOfFeeRule](ResourceListOfFeeRule.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The list of applicable fee rules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetApplicableTransactionFeesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfFeeRule> response = apiInstance.GetApplicableTransactionFeesWithHttpInfo(effectiveAt, asAt, instrumentIdentifierType, instrumentIdentifier, portfolioScope, portfolioCode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionfeerule"></a>
## GetTransactionFeeRule

> FeeRule GetTransactionFeeRule(string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

GetTransactionFeeRule: Retrieve the definition of single fee rule.

Retrieves the fee rule definition at the given effective and as at times.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeesApi>();
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
FeeRule result = apiInstance.GetTransactionFeeRule(code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The fee rule code. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definition. Defaults to the current LUSID  system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definition. Defaults to returning the latest version if not  specified. |

### Return type

[FeeRule](FeeRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Details of one fee rule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionFeeRuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeRule> response = apiInstance.GetTransactionFeeRuleWithHttpInfo(code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransactionfeerules"></a>
## ListTransactionFeeRules

> ResourceListOfFeeRule ListTransactionFeeRules(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, int? limit = null, string? filter = null, string? page = null)

ListTransactionFeeRules: List fee rules, with optional filtering.

For more information about filtering results,  see https://support.lusid.com/knowledgebase/article/KA-01914.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeesApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
ResourceListOfFeeRule result = apiInstance.ListTransactionFeeRules(effectiveAt, asAt, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the rule definitions. Defaults to the current LUSID  system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rule definitions. Defaults to returning the latest version if not  specified. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing entities; this value is returned from the previous call. If  a pagination token is provided, the filter, effectiveAt and asAt fields must not have changed since the  original request. |

### Return type

[ResourceListOfFeeRule](ResourceListOfFeeRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A filtered list of fee rules available. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTransactionFeeRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfFeeRule> response = apiInstance.ListTransactionFeeRulesWithHttpInfo(effectiveAt, asAt, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttransactionfeerules"></a>
## UpsertTransactionFeeRules

> FeeRuleUpsertResponse UpsertTransactionFeeRules(Dictionary<string, FeeRuleUpsertRequest> requestBody, DateTimeOrCutLabel? effectiveAt = null)

UpsertTransactionFeeRules: Upsert fee rules.

To upsert a new rule, the code field must be left empty, a code will then be assigned and returned as part  of the response. To update an existing rule, include the fee code. It is possible to both create and update  fee rules in the same request.    The upsert is transactional - either all create/update operations will succeed or none of them will.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionFeesApi>();
var requestBody = new Dictionary<string, FeeRuleUpsertRequest>(); // Dictionary<string, FeeRuleUpsertRequest>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
FeeRuleUpsertResponse result = apiInstance.UpsertTransactionFeeRules(requestBody, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, FeeRuleUpsertRequest&gt;](FeeRuleUpsertRequest.md) | body | **required** | A dictionary of upsert request identifiers to rule upsert requests. The request              identifiers are valid for the request only and can be used to link the upserted fee rule to the code of a              created fee rule. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the rule will take effect. Defaults to the current LUSID  system datetime if not specified. In the case of an update, the changes will take place from this effective  time until the next effective time that the rule as been upserted at. For example, consider a rule that  already exists, and has previously had an update applied so that the definition will change on the first day  of the coming month. An upsert effective from the current day will only change the definition until the  first day of the coming month. An additional upsert at the same time (first day of the month) is required  if the newly-updated definition is to supersede the future definition. |

### Return type

[FeeRuleUpsertResponse](FeeRuleUpsertResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Upsert fee rules. New fee rules must have an empty code field. Where a code is given, this rule must already exist and will be updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTransactionFeeRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeRuleUpsertResponse> response = apiInstance.UpsertTransactionFeeRulesWithHttpInfo(requestBody, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

