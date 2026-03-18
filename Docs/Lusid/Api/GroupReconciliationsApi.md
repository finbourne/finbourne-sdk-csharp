# Finbourne.Sdk.Lusid.Api.GroupReconciliationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchUpdateComparisonResults**](#batchupdatecomparisonresults) | **POST** `/api/api/reconciliations/groupreconciliationdefinitions/{scope}/{code}/comparisonresults/$batchReview` | [EXPERIMENTAL] BatchUpdateComparisonResults: Add User Review entries for a range of comparison results related to a specific GroupReconciliationDefinition. |
| [**CreateComparisonRuleset**](#createcomparisonruleset) | **POST** `/api/api/reconciliations/comparisonrulesets` | [EXPERIMENTAL] CreateComparisonRuleset: Create a Group Reconciliation Comparison Ruleset |
| [**CreateGroupReconciliationDefinition**](#creategroupreconciliationdefinition) | **POST** `/api/api/reconciliations/groupreconciliationdefinitions` | [EXPERIMENTAL] CreateGroupReconciliationDefinition: Create Group Reconciliation Definition |
| [**DeleteComparisonRuleset**](#deletecomparisonruleset) | **DELETE** `/api/api/reconciliations/comparisonrulesets/{scope}/{code}` | [EXPERIMENTAL] DeleteComparisonRuleset: Deletes a particular Group Reconciliation Comparison Ruleset |
| [**DeleteGroupReconciliationDefinition**](#deletegroupreconciliationdefinition) | **DELETE** `/api/api/reconciliations/groupreconciliationdefinitions/{scope}/{code}` | [EXPERIMENTAL] DeleteGroupReconciliationDefinition: Delete Group Reconciliation Definition |
| [**GetComparisonResult**](#getcomparisonresult) | **GET** `/api/api/reconciliations/groupreconciliationdefinitions/{scope}/{code}/{resultId}` | [EXPERIMENTAL] GetComparisonResult: Get a single Group Reconciliation Comparison Result by scope and code. |
| [**GetComparisonRuleset**](#getcomparisonruleset) | **GET** `/api/api/reconciliations/comparisonrulesets/{scope}/{code}` | [EXPERIMENTAL] GetComparisonRuleset: Get a single Group Reconciliation Comparison Ruleset by scope and code. |
| [**GetGroupReconciliationDefinition**](#getgroupreconciliationdefinition) | **GET** `/api/api/reconciliations/groupreconciliationdefinitions/{scope}/{code}` | [EXPERIMENTAL] GetGroupReconciliationDefinition: Get group reconciliation definition |
| [**ListComparisonResults**](#listcomparisonresults) | **GET** `/api/api/reconciliations/comparisonresults` | [EXPERIMENTAL] ListComparisonResults: Get a set of Group Reconciliation Comparison Results. |
| [**ListComparisonRulesets**](#listcomparisonrulesets) | **GET** `/api/api/reconciliations/comparisonrulesets` | [EXPERIMENTAL] ListComparisonRulesets: Get a set of Group Reconciliation Comparison Rulesets |
| [**ListGroupReconciliationDefinitions**](#listgroupreconciliationdefinitions) | **GET** `/api/api/reconciliations/groupreconciliationdefinitions` | [EXPERIMENTAL] ListGroupReconciliationDefinitions: List group reconciliation definitions |
| [**RunReconciliation**](#runreconciliation) | **POST** `/api/api/reconciliations/groupreconciliationdefinitions/{scope}/{code}/$run` | [EXPERIMENTAL] RunReconciliation: Runs a Group Reconciliation |
| [**UpdateComparisonRuleset**](#updatecomparisonruleset) | **PUT** `/api/api/reconciliations/comparisonrulesets/{scope}/{code}` | [EXPERIMENTAL] UpdateComparisonRuleset: Update Group Reconciliation Comparison Ruleset defined by scope and code |
| [**UpdateGroupReconciliationDefinition**](#updategroupreconciliationdefinition) | **PUT** `/api/api/reconciliations/groupreconciliationdefinitions/{scope}/{code}` | [EXPERIMENTAL] UpdateGroupReconciliationDefinition: Update group reconciliation definition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<GroupReconciliationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
```

---

<a id="batchupdatecomparisonresults"></a>
## BatchUpdateComparisonResults

> BatchUpdateUserReviewForComparisonResultResponse BatchUpdateComparisonResults(string scope, string code, List<BatchUpdateUserReviewForComparisonResultRequest> batchUpdateUserReviewForComparisonResultRequest, string? successMode = null)

[EXPERIMENTAL] BatchUpdateComparisonResults: Add User Review entries for a range of comparison results related to a specific GroupReconciliationDefinition.

Allows to update multiple Group Reconciliation Comparison Results related to the same definition specified by the Scope and Code.  Updates User Review with new entries and sets the relevant Review Status.  Supports partial success when all the entries that haven't passed validation or are not related to the definition will be returned with respectful error details.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var batchUpdateUserReviewForComparisonResultRequest = new List<BatchUpdateUserReviewForComparisonResultRequest>(); // List<BatchUpdateUserReviewForComparisonResultRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchUpdateUserReviewForComparisonResultResponse result = apiInstance.BatchUpdateComparisonResults(scope, code, batchUpdateUserReviewForComparisonResultRequest, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Shared Scope of the GroupReconciliationDefinition and GroupReconciliationComparisonResults. |
| **code** | **string** | path | **required** | GroupReconciliationDefinitionId code. |
| **batchUpdateUserReviewForComparisonResultRequest** | [List&lt;BatchUpdateUserReviewForComparisonResultRequest&gt;](BatchUpdateUserReviewForComparisonResultRequest.md) | body | **required** | A collection of the comparison result Ids and their user review entries to be added or removed.                  Single request contains resultId, break code/match key/comment to add and break code/match key/comment to remove by added timestamp. |
| **successMode** | **string?** | query | optional | Defines whether the request should fail if at least one of the entries is failed to update                  or process all the entries regardless and return collections of successful and failed updates. \&quot;Partial\&quot; (default) | \&quot;Atomic\&quot;. Default: `&quot;Partial&quot;` |

### Return type

[BatchUpdateUserReviewForComparisonResultResponse](BatchUpdateUserReviewForComparisonResultResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The collections of comparison result Ids that succeeded or failed to update along with the updated entities or error details. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpdateComparisonResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpdateUserReviewForComparisonResultResponse> response = apiInstance.BatchUpdateComparisonResultsWithHttpInfo(scope, code, batchUpdateUserReviewForComparisonResultRequest, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createcomparisonruleset"></a>
## CreateComparisonRuleset

> GroupReconciliationComparisonRuleset CreateComparisonRuleset(CreateGroupReconciliationComparisonRulesetRequest? createGroupReconciliationComparisonRulesetRequest = null)

[EXPERIMENTAL] CreateComparisonRuleset: Create a Group Reconciliation Comparison Ruleset

Creates a set of core and aggregate rules to be run for a group reconciliation

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var createGroupReconciliationComparisonRulesetRequest = new CreateGroupReconciliationComparisonRulesetRequest?(); // CreateGroupReconciliationComparisonRulesetRequest? (optional)
GroupReconciliationComparisonRuleset result = apiInstance.CreateComparisonRuleset(createGroupReconciliationComparisonRulesetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createGroupReconciliationComparisonRulesetRequest** | [CreateGroupReconciliationComparisonRulesetRequest?](CreateGroupReconciliationComparisonRulesetRequest?.md) | body | optional | The request containing the details of the ruleset |

### Return type

[GroupReconciliationComparisonRuleset](GroupReconciliationComparisonRuleset.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created comparison ruleset |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateComparisonRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationComparisonRuleset> response = apiInstance.CreateComparisonRulesetWithHttpInfo(createGroupReconciliationComparisonRulesetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="creategroupreconciliationdefinition"></a>
## CreateGroupReconciliationDefinition

> GroupReconciliationDefinition CreateGroupReconciliationDefinition(CreateGroupReconciliationDefinitionRequest? createGroupReconciliationDefinitionRequest = null)

[EXPERIMENTAL] CreateGroupReconciliationDefinition: Create Group Reconciliation Definition

Creates a Group Reconciliation Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var createGroupReconciliationDefinitionRequest = new CreateGroupReconciliationDefinitionRequest?(); // CreateGroupReconciliationDefinitionRequest? (optional)
GroupReconciliationDefinition result = apiInstance.CreateGroupReconciliationDefinition(createGroupReconciliationDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createGroupReconciliationDefinitionRequest** | [CreateGroupReconciliationDefinitionRequest?](CreateGroupReconciliationDefinitionRequest?.md) | body | optional | The definition Group Reconciliation Definition details |

### Return type

[GroupReconciliationDefinition](GroupReconciliationDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Group Reconciliation Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateGroupReconciliationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationDefinition> response = apiInstance.CreateGroupReconciliationDefinitionWithHttpInfo(createGroupReconciliationDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecomparisonruleset"></a>
## DeleteComparisonRuleset

> DeletedEntityResponse DeleteComparisonRuleset(string scope, string code)

[EXPERIMENTAL] DeleteComparisonRuleset: Deletes a particular Group Reconciliation Comparison Ruleset

The deletion will take effect from the reconciliation comparison ruleset deletion datetime.  i.e. will no longer exist at any asAt datetime after the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteComparisonRuleset(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified comparison ruleset. |
| **code** | **string** | path | **required** | The code of the specified comparison ruleset. Together with the domain and scope this uniquely              identifies the reconciliation comparison ruleset. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteComparisonRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteComparisonRulesetWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletegroupreconciliationdefinition"></a>
## DeleteGroupReconciliationDefinition

> DeletedEntityResponse DeleteGroupReconciliationDefinition(string scope, string code)

[EXPERIMENTAL] DeleteGroupReconciliationDefinition: Delete Group Reconciliation Definition

Delete the group reconciliation definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteGroupReconciliationDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group reconciliation definition to delete. |
| **code** | **string** | path | **required** | The code of the group reconciliation definition to delete. Together with the scope this uniquely identifies the group reconciliation definition to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the group reconciliation definition was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteGroupReconciliationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteGroupReconciliationDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcomparisonresult"></a>
## GetComparisonResult

> GroupReconciliationComparisonResult GetComparisonResult(string scope, string code, string resultId, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetComparisonResult: Get a single Group Reconciliation Comparison Result by scope and code.

Retrieves one Group Reconciliation Comparison Result by scope and code  with the prior validation that its related reconciliation definition exists.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var resultId = "resultId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GroupReconciliationComparisonResult result = apiInstance.GetComparisonResult(scope, code, resultId, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified comparison result and its related reconciliation definition. |
| **code** | **string** | path | **required** | The code of the reconciliation definition that was used to produce the reconciliation result. |
| **resultId** | **string** | path | **required** | The code of the specified reconciliation result. Together with the domain and scope this uniquely              identifies the reconciliation comparison result. This value is also the same as the computed result hash based on property values. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the comparison result definition. Defaults to return              the latest version if not specified. |

### Return type

[GroupReconciliationComparisonResult](GroupReconciliationComparisonResult.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested comparison result |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetComparisonResultWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationComparisonResult> response = apiInstance.GetComparisonResultWithHttpInfo(scope, code, resultId, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcomparisonruleset"></a>
## GetComparisonRuleset

> GroupReconciliationComparisonRuleset GetComparisonRuleset(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetComparisonRuleset: Get a single Group Reconciliation Comparison Ruleset by scope and code.

Retrieves one Group Reconciliation Comparison Ruleset by scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GroupReconciliationComparisonRuleset result = apiInstance.GetComparisonRuleset(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified comparison ruleset. |
| **code** | **string** | path | **required** | The code of the specified comparison ruleset. Together with the domain and scope this uniquely              identifies the reconciliation comparison ruleset. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the comparison ruleset definition. Defaults to return              the latest version of the definition if not specified. |

### Return type

[GroupReconciliationComparisonRuleset](GroupReconciliationComparisonRuleset.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested comparison ruleset |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetComparisonRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationComparisonRuleset> response = apiInstance.GetComparisonRulesetWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getgroupreconciliationdefinition"></a>
## GetGroupReconciliationDefinition

> GroupReconciliationDefinition GetGroupReconciliationDefinition(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetGroupReconciliationDefinition: Get group reconciliation definition

Retrieves a Group Reconciliation Definition by scope and code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GroupReconciliationDefinition result = apiInstance.GetGroupReconciliationDefinition(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group reconciliation definition to retrieve. |
| **code** | **string** | path | **required** | The code of the group reconciliation definition to retrieve. Together with the scope              this uniquely identifies the group reconciliation definition. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the group reconciliation definition. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the group reconciliation definition. Defaults to return the latest version of the portfolio group definition if not specified. |

### Return type

[GroupReconciliationDefinition](GroupReconciliationDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested group reconciliation definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetGroupReconciliationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationDefinition> response = apiInstance.GetGroupReconciliationDefinitionWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcomparisonresults"></a>
## ListComparisonResults

> PagedResourceListOfGroupReconciliationComparisonResult ListComparisonResults(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListComparisonResults: Get a set of Group Reconciliation Comparison Results.

Retrieves all Group Reconciliation Comparison Results that fit the filter, in a specific order if sortBy is provided.  Supports pagination.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfGroupReconciliationComparisonResult result = apiInstance.ListComparisonResults(asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the comparison results. Defaults to return the latest              version of the comparison results if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing comparison results from a previous call to list              comparison results. This value is returned from the previous call. If a pagination token is provided the sortBy,              filter, effectiveAt, and asAt fields must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many per page. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfGroupReconciliationComparisonResult](PagedResourceListOfGroupReconciliationComparisonResult.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested list of comparison results |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListComparisonResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGroupReconciliationComparisonResult> response = apiInstance.ListComparisonResultsWithHttpInfo(asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcomparisonrulesets"></a>
## ListComparisonRulesets

> PagedResourceListOfGroupReconciliationComparisonRuleset ListComparisonRulesets(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListComparisonRulesets: Get a set of Group Reconciliation Comparison Rulesets

Retrieves all Group Reconciliation Comparison Ruleset that fit the filter, in a specific order if sortBy is provided  Supports pagination

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfGroupReconciliationComparisonRuleset result = apiInstance.ListComparisonRulesets(asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the comparison rulesets. Defaults to return the latest              version of the comparison rulesets if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing comparison rulesets from a previous call to list              comparison rulesets. This value is returned from the previous call. If a pagination token is provided the sortBy,              filter, effectiveAt, and asAt fields must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many per page. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfGroupReconciliationComparisonRuleset](PagedResourceListOfGroupReconciliationComparisonRuleset.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested list of comparison rulesets |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListComparisonRulesetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGroupReconciliationComparisonRuleset> response = apiInstance.ListComparisonRulesetsWithHttpInfo(asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listgroupreconciliationdefinitions"></a>
## ListGroupReconciliationDefinitions

> PagedResourceListOfGroupReconciliationDefinition ListGroupReconciliationDefinitions(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListGroupReconciliationDefinitions: List group reconciliation definitions

Lists Group Reconciliation Definitions matching any provided filter, limit and sorting rules

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfGroupReconciliationDefinition result = apiInstance.ListGroupReconciliationDefinitions(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the group reconciliation definitions. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the group reconciliation definitions. Defaults to return the latest version of each group reconciliation definition if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing group reconciliation definitions from a previous call to list group reconciliation definitions. This  value is returned from the previous call. If a pagination token is provided the filter, effectiveAt, sortBy  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to no limit if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Display Name, use \&quot;displayName eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfGroupReconciliationDefinition](PagedResourceListOfGroupReconciliationDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The group reconciliation definition in the specified scope |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListGroupReconciliationDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGroupReconciliationDefinition> response = apiInstance.ListGroupReconciliationDefinitionsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runreconciliation"></a>
## RunReconciliation

> GroupReconciliationRunResponse RunReconciliation(string scope, string code, GroupReconciliationRunRequest? groupReconciliationRunRequest = null)

[EXPERIMENTAL] RunReconciliation: Runs a Group Reconciliation

Runs a Group Reconciliation using the definition specified by the Scope and Code  Supports pagination.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var groupReconciliationRunRequest = new GroupReconciliationRunRequest?(); // GroupReconciliationRunRequest? (optional)
GroupReconciliationRunResponse result = apiInstance.RunReconciliation(scope, code, groupReconciliationRunRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group reconciliation definition to use for the reconciliation. |
| **code** | **string** | path | **required** | The code of the group reconciliation definition to use for the reconciliation. |
| **groupReconciliationRunRequest** | [GroupReconciliationRunRequest?](GroupReconciliationRunRequest?.md) | body | optional |  |

### Return type

[GroupReconciliationRunResponse](GroupReconciliationRunResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The results of the reconciliation run |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunReconciliationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationRunResponse> response = apiInstance.RunReconciliationWithHttpInfo(scope, code, groupReconciliationRunRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecomparisonruleset"></a>
## UpdateComparisonRuleset

> GroupReconciliationComparisonRuleset UpdateComparisonRuleset(string scope, string code, UpdateGroupReconciliationComparisonRulesetRequest? updateGroupReconciliationComparisonRulesetRequest = null)

[EXPERIMENTAL] UpdateComparisonRuleset: Update Group Reconciliation Comparison Ruleset defined by scope and code

Overwrites an existing Group Reconciliation Comparison Ruleset  Update request has the same required fields as Create apart from the Id

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateGroupReconciliationComparisonRulesetRequest = new UpdateGroupReconciliationComparisonRulesetRequest?(); // UpdateGroupReconciliationComparisonRulesetRequest? (optional)
GroupReconciliationComparisonRuleset result = apiInstance.UpdateComparisonRuleset(scope, code, updateGroupReconciliationComparisonRulesetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified comparison ruleset. |
| **code** | **string** | path | **required** | The code of the specified comparison ruleset. Together with the domain and scope this uniquely                  identifies the reconciliation comparison ruleset. |
| **updateGroupReconciliationComparisonRulesetRequest** | [UpdateGroupReconciliationComparisonRulesetRequest?](UpdateGroupReconciliationComparisonRulesetRequest?.md) | body | optional | The request containing the updated details of the ruleset |

### Return type

[GroupReconciliationComparisonRuleset](GroupReconciliationComparisonRuleset.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated version of the requested comparison ruleset |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateComparisonRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationComparisonRuleset> response = apiInstance.UpdateComparisonRulesetWithHttpInfo(scope, code, updateGroupReconciliationComparisonRulesetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updategroupreconciliationdefinition"></a>
## UpdateGroupReconciliationDefinition

> GroupReconciliationDefinition UpdateGroupReconciliationDefinition(string scope, string code, UpdateGroupReconciliationDefinitionRequest? updateGroupReconciliationDefinitionRequest = null)

[EXPERIMENTAL] UpdateGroupReconciliationDefinition: Update group reconciliation definition

Update the group reconciliation definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<GroupReconciliationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateGroupReconciliationDefinitionRequest = new UpdateGroupReconciliationDefinitionRequest?(); // UpdateGroupReconciliationDefinitionRequest? (optional)
GroupReconciliationDefinition result = apiInstance.UpdateGroupReconciliationDefinition(scope, code, updateGroupReconciliationDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group reconciliation definition to update the details for. |
| **code** | **string** | path | **required** | The code of the group reconciliation definition to update the details for. Together with the scope this uniquely identifies the group reconciliation definition. |
| **updateGroupReconciliationDefinitionRequest** | [UpdateGroupReconciliationDefinitionRequest?](UpdateGroupReconciliationDefinitionRequest?.md) | body | optional | The updated group reconciliation definition. |

### Return type

[GroupReconciliationDefinition](GroupReconciliationDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated details of the group reconciliation definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateGroupReconciliationDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GroupReconciliationDefinition> response = apiInstance.UpdateGroupReconciliationDefinitionWithHttpInfo(scope, code, updateGroupReconciliationDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

