# Finbourne.Sdk.Lusid.Api.RecsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddRecResultSetApprovalDecision**](#addrecresultsetapprovaldecision) | **POST** `/api/api/recs/resultsets/{entityUniqueId}/$decide` | [EXPERIMENTAL] AddRecResultSetApprovalDecision: AddRecResultSetApprovalDecision |
| [**BatchManageRecResultComments**](#batchmanagerecresultcomments) | **POST** `/api/api/recs/results/$batchManageComments` | [EXPERIMENTAL] BatchManageRecResultComments: BatchManageRecResultComments |
| [**BatchReviewRecResults**](#batchreviewrecresults) | **POST** `/api/api/recs/results/$batchReview` | [EXPERIMENTAL] BatchReviewRecResults: BatchReviewRecResults |
| [**CreateMatchingRuleset**](#creatematchingruleset) | **POST** `/api/api/recs/matchingrulesets` | [EXPERIMENTAL] CreateMatchingRuleset: CreateMatchingRuleset |
| [**CreateRecDefinition**](#createrecdefinition) | **POST** `/api/api/recs/definitions` | [EXPERIMENTAL] CreateRecDefinition: CreateRecDefinition |
| [**DeleteMatchingRuleset**](#deletematchingruleset) | **DELETE** `/api/api/recs/matchingrulesets/{scope}/{code}` | [EXPERIMENTAL] DeleteMatchingRuleset: DeleteMatchingRuleset |
| [**DeleteRecDefinition**](#deleterecdefinition) | **DELETE** `/api/api/recs/definitions/{scope}/{code}` | [EXPERIMENTAL] DeleteRecDefinition: DeleteRecDefinition |
| [**GetMatchingRuleset**](#getmatchingruleset) | **GET** `/api/api/recs/matchingrulesets/{scope}/{code}` | [EXPERIMENTAL] GetMatchingRuleset: GetMatchingRuleset |
| [**GetRecDefinition**](#getrecdefinition) | **GET** `/api/api/recs/definitions/{scope}/{code}` | [EXPERIMENTAL] GetRecDefinition: GetRecDefinition |
| [**GetRecInstance**](#getrecinstance) | **GET** `/api/api/recs/instances/{instanceIdType}/{instanceIdValue}` | [EXPERIMENTAL] GetRecInstance: GetRecInstance |
| [**GetRecResult**](#getrecresult) | **GET** `/api/api/recs/results/{id}` | [EXPERIMENTAL] GetRecResult: GetRecResult |
| [**GetRecResultSet**](#getrecresultset) | **GET** `/api/api/recs/resultsets/{entityUniqueId}` | [EXPERIMENTAL] GetRecResultSet: GetRecResultSet |
| [**InstantiateRec**](#instantiaterec) | **POST** `/api/api/recs/instances` | [EXPERIMENTAL] InstantiateRec: InstantiateRec |
| [**ListMatchingRulesets**](#listmatchingrulesets) | **GET** `/api/api/recs/matchingrulesets` | [EXPERIMENTAL] ListMatchingRulesets: ListMatchingRulesets |
| [**ListRecDefinitions**](#listrecdefinitions) | **GET** `/api/api/recs/definitions` | [EXPERIMENTAL] ListRecDefinitions: ListRecDefinitions |
| [**ListRecInstances**](#listrecinstances) | **GET** `/api/api/recs/instances` | [EXPERIMENTAL] ListRecInstances: ListRecInstances |
| [**ListRecResultSets**](#listrecresultsets) | **GET** `/api/api/recs/resultsets` | [EXPERIMENTAL] ListRecResultSets: ListRecResultSets |
| [**ListRecResults**](#listrecresults) | **GET** `/api/api/recs/results` | [EXPERIMENTAL] ListRecResults: ListRecResults |
| [**SubmitRecResultSetReview**](#submitrecresultsetreview) | **POST** `/api/api/recs/resultsets/{entityUniqueId}/$submit` | [EXPERIMENTAL] SubmitRecResultSetReview: Submit a rec result set review for approval, or resubmit after addressing requested revisions. |
| [**TransitionRecInstance**](#transitionrecinstance) | **POST** `/api/api/recs/instances/{instanceIdType}/{instanceIdValue}/$transition` | [EXPERIMENTAL] TransitionRecInstance: TransitionRecInstance |
| [**UpdateMatchingRuleset**](#updatematchingruleset) | **PUT** `/api/api/recs/matchingrulesets/{scope}/{code}` | [EXPERIMENTAL] UpdateMatchingRuleset: UpdateMatchingRuleset |
| [**UpdateRecDefinition**](#updaterecdefinition) | **PUT** `/api/api/recs/definitions/{scope}/{code}` | [EXPERIMENTAL] UpdateRecDefinition: UpdateRecDefinition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RecsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
```

---

<a id="addrecresultsetapprovaldecision"></a>
## AddRecResultSetApprovalDecision

> RecResultSet AddRecResultSetApprovalDecision(string entityUniqueId, RecResultSetApprovalDecisionRequest recResultSetApprovalDecisionRequest)

[EXPERIMENTAL] AddRecResultSetApprovalDecision: AddRecResultSetApprovalDecision

Add an approver decision (approve or request revisions) to a rec result set.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var recResultSetApprovalDecisionRequest = new RecResultSetApprovalDecisionRequest(); // RecResultSetApprovalDecisionRequest
RecResultSet result = apiInstance.AddRecResultSetApprovalDecision(entityUniqueId, recResultSetApprovalDecisionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The entity unique id of the rec result set (its version.entityUniqueId). |
| **recResultSetApprovalDecisionRequest** | [RecResultSetApprovalDecisionRequest](../Model/RecResultSetApprovalDecisionRequest.md) | body | **required** | The approval decision request. |

### Return type

[RecResultSet](../Model/RecResultSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated rec result set. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddRecResultSetApprovalDecisionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecResultSet> response = apiInstance.AddRecResultSetApprovalDecisionWithHttpInfo(entityUniqueId, recResultSetApprovalDecisionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchmanagerecresultcomments"></a>
## BatchManageRecResultComments

> BatchManageCommentResponse BatchManageRecResultComments(Dictionary<string, BatchManageCommentRequest> requestBody, string? successMode = null)

[EXPERIMENTAL] BatchManageRecResultComments: BatchManageRecResultComments

Add, edit or delete comments on rec results in a batch.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var requestBody = new Dictionary<string, BatchManageCommentRequest>(); // Dictionary<string, BatchManageCommentRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchManageCommentResponse result = apiInstance.BatchManageRecResultComments(requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, BatchManageCommentRequest&gt;](../Model/BatchManageCommentRequest.md) | body | **required** | The batch of comment operations, keyed by a client-supplied correlation key. |
| **successMode** | **string?** | query | optional | Whether the batch fails Atomically or in a Partial fashion. Allowed values: Atomic, Partial. Default: `&quot;Partial&quot;` |

### Return type

[BatchManageCommentResponse](../Model/BatchManageCommentResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated rec results, keyed by batch item key. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchManageRecResultCommentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchManageCommentResponse> response = apiInstance.BatchManageRecResultCommentsWithHttpInfo(requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchreviewrecresults"></a>
## BatchReviewRecResults

> BatchReviewRecResultResponse BatchReviewRecResults(Dictionary<string, BatchReviewRecResultRequest> requestBody, string? successMode = null)

[EXPERIMENTAL] BatchReviewRecResults: BatchReviewRecResults

Apply a batch of review actions (decisions, assignments, comments, properties) to rec results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var requestBody = new Dictionary<string, BatchReviewRecResultRequest>(); // Dictionary<string, BatchReviewRecResultRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchReviewRecResultResponse result = apiInstance.BatchReviewRecResults(requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, BatchReviewRecResultRequest&gt;](../Model/BatchReviewRecResultRequest.md) | body | **required** | The batch of review items, keyed by a client-supplied correlation key. |
| **successMode** | **string?** | query | optional | Whether the batch fails Atomically or in a Partial fashion. Allowed values: Atomic, Partial. Default: `&quot;Partial&quot;` |

### Return type

[BatchReviewRecResultResponse](../Model/BatchReviewRecResultResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The results affected by each batch item. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchReviewRecResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchReviewRecResultResponse> response = apiInstance.BatchReviewRecResultsWithHttpInfo(requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="creatematchingruleset"></a>
## CreateMatchingRuleset

> MatchingRuleset CreateMatchingRuleset(CreateMatchingRulesetRequest createMatchingRulesetRequest)

[EXPERIMENTAL] CreateMatchingRuleset: CreateMatchingRuleset

Create a matching ruleset, describing the core and aggregate rules used to match a reconciliation's two sides.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var createMatchingRulesetRequest = new CreateMatchingRulesetRequest(); // CreateMatchingRulesetRequest
MatchingRuleset result = apiInstance.CreateMatchingRuleset(createMatchingRulesetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createMatchingRulesetRequest** | [CreateMatchingRulesetRequest](../Model/CreateMatchingRulesetRequest.md) | body | **required** | The matching ruleset to create. |

### Return type

[MatchingRuleset](../Model/MatchingRuleset.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created matching ruleset. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateMatchingRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MatchingRuleset> response = apiInstance.CreateMatchingRulesetWithHttpInfo(createMatchingRulesetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createrecdefinition"></a>
## CreateRecDefinition

> RecDefinition CreateRecDefinition(CreateRecDefinitionRequest createRecDefinitionRequest)

[EXPERIMENTAL] CreateRecDefinition: CreateRecDefinition

Create a rec definition, describing the two sides to reconcile and the rules to reconcile them with.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var createRecDefinitionRequest = new CreateRecDefinitionRequest(); // CreateRecDefinitionRequest
RecDefinition result = apiInstance.CreateRecDefinition(createRecDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createRecDefinitionRequest** | [CreateRecDefinitionRequest](../Model/CreateRecDefinitionRequest.md) | body | **required** | The rec definition to create. |

### Return type

[RecDefinition](../Model/RecDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created rec definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRecDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecDefinition> response = apiInstance.CreateRecDefinitionWithHttpInfo(createRecDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletematchingruleset"></a>
## DeleteMatchingRuleset

> DeletedEntityResponse DeleteMatchingRuleset(string scope, string code)

[EXPERIMENTAL] DeleteMatchingRuleset: DeleteMatchingRuleset

Delete a matching ruleset identified by scope and code. The deletion takes effect from the deletion datetime,  i.e. the matching ruleset will no longer exist at any asAt datetime after the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteMatchingRuleset(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the matching ruleset. |
| **code** | **string** | path | **required** | The code of the matching ruleset. Together with the scope this uniquely identifies the matching ruleset. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteMatchingRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteMatchingRulesetWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterecdefinition"></a>
## DeleteRecDefinition

> DeletedEntityResponse DeleteRecDefinition(string scope, string code)

[EXPERIMENTAL] DeleteRecDefinition: DeleteRecDefinition

Delete a rec definition identified by scope and code. The deletion takes effect from the deletion datetime,  i.e. the rec definition will no longer exist at any asAt datetime after the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteRecDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the rec definition. |
| **code** | **string** | path | **required** | The code of the rec definition. Together with the scope this uniquely identifies the rec definition. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRecDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteRecDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmatchingruleset"></a>
## GetMatchingRuleset

> MatchingRuleset GetMatchingRuleset(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetMatchingRuleset: GetMatchingRuleset

Retrieve a single matching ruleset by scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
MatchingRuleset result = apiInstance.GetMatchingRuleset(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the matching ruleset. |
| **code** | **string** | path | **required** | The code of the matching ruleset. Together with the scope this uniquely identifies the matching ruleset. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the matching ruleset. Defaults to latest if not specified. |

### Return type

[MatchingRuleset](../Model/MatchingRuleset.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested matching ruleset. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMatchingRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MatchingRuleset> response = apiInstance.GetMatchingRulesetWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrecdefinition"></a>
## GetRecDefinition

> RecDefinition GetRecDefinition(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetRecDefinition: GetRecDefinition

Retrieve a single rec definition by scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
RecDefinition result = apiInstance.GetRecDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the rec definition. |
| **code** | **string** | path | **required** | The code of the rec definition. Together with the scope this uniquely identifies the rec definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the rec definition. Defaults to latest if not specified. |

### Return type

[RecDefinition](../Model/RecDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested rec definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRecDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecDefinition> response = apiInstance.GetRecDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrecinstance"></a>
## GetRecInstance

> RecInstance GetRecInstance(string instanceIdType, string instanceIdValue, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetRecInstance: GetRecInstance

Retrieve a single rec instance by its identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var instanceIdType = "instanceIdType_example";  // string
var instanceIdValue = "instanceIdValue_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
RecInstance result = apiInstance.GetRecInstance(instanceIdType, instanceIdValue, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceIdType** | **string** | path | **required** | How the instance was created: \&quot;WorkflowServiceTaskId\&quot; or \&quot;Manual\&quot;. Available values: WorkflowServiceTaskId, Manual. |
| **instanceIdValue** | **string** | path | **required** | The instance identifier value (a GUID). |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instance. Defaults to latest if not specified. |

### Return type

[RecInstance](../Model/RecInstance.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested rec instance. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRecInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecInstance> response = apiInstance.GetRecInstanceWithHttpInfo(instanceIdType, instanceIdValue, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrecresult"></a>
## GetRecResult

> RecResult GetRecResult(string id, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetRecResult: GetRecResult

Retrieve a single rec result by its id.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var id = "id_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
RecResult result = apiInstance.GetRecResult(id, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The system-generated id of the rec result. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the result. Defaults to latest if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | The property keys to decorate onto the result. |

### Return type

[RecResult](../Model/RecResult.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested rec result. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRecResultWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecResult> response = apiInstance.GetRecResultWithHttpInfo(id, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrecresultset"></a>
## GetRecResultSet

> RecResultSet GetRecResultSet(string entityUniqueId, DateTimeOffset? asAt = null, bool? includePreviousRuns = null)

[EXPERIMENTAL] GetRecResultSet: GetRecResultSet

Retrieve a single rec result set by its entity unique id.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var includePreviousRuns = false;  // bool? (optional)
RecResultSet result = apiInstance.GetRecResultSet(entityUniqueId, asAt, includePreviousRuns);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The entity unique id of the rec result set (its version.entityUniqueId). |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the result set. Defaults to latest if not specified. |
| **includePreviousRuns** | **bool?** | query | optional | When true, the previousRuns array is populated with prior run snapshots. Defaults to false. Default: `false` |

### Return type

[RecResultSet](../Model/RecResultSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested rec result set. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRecResultSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecResultSet> response = apiInstance.GetRecResultSetWithHttpInfo(entityUniqueId, asAt, includePreviousRuns);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="instantiaterec"></a>
## InstantiateRec

> RecInstance InstantiateRec(InstantiateRecRequest instantiateRecRequest)

[EXPERIMENTAL] InstantiateRec: InstantiateRec

Instantiate a new rec instance from a rec definition and start its first run. The run              executes asynchronously; the response returns once the run has started, with the instance Running.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var instantiateRecRequest = new InstantiateRecRequest(); // InstantiateRecRequest
RecInstance result = apiInstance.InstantiateRec(instantiateRecRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instantiateRecRequest** | [InstantiateRecRequest](../Model/InstantiateRecRequest.md) | body | **required** | The instantiation request. |

### Return type

[RecInstance](../Model/RecInstance.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The instantiated rec instance, in a Running state. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the InstantiateRecWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecInstance> response = apiInstance.InstantiateRecWithHttpInfo(instantiateRecRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmatchingrulesets"></a>
## ListMatchingRulesets

> PagedResourceListOfMatchingRuleset ListMatchingRulesets(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListMatchingRulesets: ListMatchingRulesets

List matching rulesets, optionally filtered and sorted. Supports pagination.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfMatchingRuleset result = apiInstance.ListMatchingRulesets(asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the matching rulesets. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing matching rulesets from a previous call. This value is              returned from the previous call. If a pagination token is provided the sortBy, filter and asAt fields must not have              changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many per page. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfMatchingRuleset](../Model/PagedResourceListOfMatchingRuleset.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested list of matching rulesets. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMatchingRulesetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfMatchingRuleset> response = apiInstance.ListMatchingRulesetsWithHttpInfo(asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrecdefinitions"></a>
## ListRecDefinitions

> PagedResourceListOfRecDefinition ListRecDefinitions(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListRecDefinitions: ListRecDefinitions

List rec definitions, optionally filtered and sorted. Supports pagination.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfRecDefinition result = apiInstance.ListRecDefinitions(asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the rec definitions. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing rec definitions from a previous call. This value is              returned from the previous call. If a pagination token is provided the sortBy, filter and asAt fields must not have              changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many per page. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfRecDefinition](../Model/PagedResourceListOfRecDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested list of rec definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRecDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRecDefinition> response = apiInstance.ListRecDefinitionsWithHttpInfo(asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrecinstances"></a>
## ListRecInstances

> PagedResourceListOfRecInstance ListRecInstances(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListRecInstances: ListRecInstances

List rec instances.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfRecInstance result = apiInstance.ListRecInstances(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list instances. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing instances from a previous call. If a pagination token is provided the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfRecInstance](../Model/PagedResourceListOfRecInstance.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rec instances. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRecInstancesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRecInstance> response = apiInstance.ListRecInstancesWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrecresultsets"></a>
## ListRecResultSets

> PagedResourceListOfRecResultSet ListRecResultSets(DateTimeOffset? asAt = null, bool? includePreviousRuns = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListRecResultSets: ListRecResultSets

List rec result sets.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var includePreviousRuns = false;  // bool? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfRecResultSet result = apiInstance.ListRecResultSets(asAt, includePreviousRuns, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list result sets. Defaults to latest if not specified. |
| **includePreviousRuns** | **bool?** | query | optional | When true, each item&#39;s previousRuns array is populated with prior run snapshots. Defaults to false. Default: `false` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing result sets from a previous call. If a pagination token is provided the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfRecResultSet](../Model/PagedResourceListOfRecResultSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rec result sets. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRecResultSetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRecResultSet> response = apiInstance.ListRecResultSetsWithHttpInfo(asAt, includePreviousRuns, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrecresults"></a>
## ListRecResults

> PagedResourceListOfRecResult ListRecResults(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListRecResults: ListRecResults

List rec results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfRecResult result = apiInstance.ListRecResults(asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list results. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing results from a previous call. If a pagination token is provided the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | The property keys to decorate onto each result. |

### Return type

[PagedResourceListOfRecResult](../Model/PagedResourceListOfRecResult.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rec results. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRecResultsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRecResult> response = apiInstance.ListRecResultsWithHttpInfo(asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="submitrecresultsetreview"></a>
## SubmitRecResultSetReview

> RecResultSet SubmitRecResultSetReview(string entityUniqueId, SubmitRecResultSetReviewRequest submitRecResultSetReviewRequest)

[EXPERIMENTAL] SubmitRecResultSetReview: Submit a rec result set review for approval, or resubmit after addressing requested revisions.

Submit a rec result set review for approval, or resubmit after addressing requested revisions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var submitRecResultSetReviewRequest = new SubmitRecResultSetReviewRequest(); // SubmitRecResultSetReviewRequest
RecResultSet result = apiInstance.SubmitRecResultSetReview(entityUniqueId, submitRecResultSetReviewRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The entity unique id of the rec result set (its version.entityUniqueId). |
| **submitRecResultSetReviewRequest** | [SubmitRecResultSetReviewRequest](../Model/SubmitRecResultSetReviewRequest.md) | body | **required** | The submission request. |

### Return type

[RecResultSet](../Model/RecResultSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated rec result set. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SubmitRecResultSetReviewWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecResultSet> response = apiInstance.SubmitRecResultSetReviewWithHttpInfo(entityUniqueId, submitRecResultSetReviewRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="transitionrecinstance"></a>
## TransitionRecInstance

> RecInstance TransitionRecInstance(string instanceIdType, string instanceIdValue, TransitionRecInstanceRequest transitionRecInstanceRequest)

[EXPERIMENTAL] TransitionRecInstance: TransitionRecInstance

Apply a lifecycle transition (re-run, lock or unlock) to a rec instance.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var instanceIdType = "instanceIdType_example";  // string
var instanceIdValue = "instanceIdValue_example";  // string
var transitionRecInstanceRequest = new TransitionRecInstanceRequest(); // TransitionRecInstanceRequest
RecInstance result = apiInstance.TransitionRecInstance(instanceIdType, instanceIdValue, transitionRecInstanceRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceIdType** | **string** | path | **required** | How the instance was created: \&quot;WorkflowServiceTaskId\&quot; or \&quot;Manual\&quot;. Available values: WorkflowServiceTaskId, Manual. |
| **instanceIdValue** | **string** | path | **required** | The instance identifier value (a GUID). |
| **transitionRecInstanceRequest** | [TransitionRecInstanceRequest](../Model/TransitionRecInstanceRequest.md) | body | **required** | The transition request. |

### Return type

[RecInstance](../Model/RecInstance.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rec instance in its post-transition state. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the TransitionRecInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecInstance> response = apiInstance.TransitionRecInstanceWithHttpInfo(instanceIdType, instanceIdValue, transitionRecInstanceRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatematchingruleset"></a>
## UpdateMatchingRuleset

> MatchingRuleset UpdateMatchingRuleset(string scope, string code, UpdateMatchingRulesetRequest updateMatchingRulesetRequest)

[EXPERIMENTAL] UpdateMatchingRuleset: UpdateMatchingRuleset

Overwrite an existing matching ruleset identified by scope and code.  The update request has the same required fields as create, apart from the identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateMatchingRulesetRequest = new UpdateMatchingRulesetRequest(); // UpdateMatchingRulesetRequest
MatchingRuleset result = apiInstance.UpdateMatchingRuleset(scope, code, updateMatchingRulesetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the matching ruleset. |
| **code** | **string** | path | **required** | The code of the matching ruleset. Together with the scope this uniquely identifies the matching ruleset. |
| **updateMatchingRulesetRequest** | [UpdateMatchingRulesetRequest](../Model/UpdateMatchingRulesetRequest.md) | body | **required** | The updated matching ruleset values. |

### Return type

[MatchingRuleset](../Model/MatchingRuleset.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated matching ruleset. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateMatchingRulesetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MatchingRuleset> response = apiInstance.UpdateMatchingRulesetWithHttpInfo(scope, code, updateMatchingRulesetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterecdefinition"></a>
## UpdateRecDefinition

> RecDefinition UpdateRecDefinition(string scope, string code, UpdateRecDefinitionRequest updateRecDefinitionRequest)

[EXPERIMENTAL] UpdateRecDefinition: UpdateRecDefinition

Overwrite an existing rec definition identified by scope and code.  The update request has the same required fields as create, apart from the identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RecsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateRecDefinitionRequest = new UpdateRecDefinitionRequest(); // UpdateRecDefinitionRequest
RecDefinition result = apiInstance.UpdateRecDefinition(scope, code, updateRecDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the rec definition. |
| **code** | **string** | path | **required** | The code of the rec definition. Together with the scope this uniquely identifies the rec definition. |
| **updateRecDefinitionRequest** | [UpdateRecDefinitionRequest](../Model/UpdateRecDefinitionRequest.md) | body | **required** | The updated rec definition values. |

### Return type

[RecDefinition](../Model/RecDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated rec definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRecDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RecDefinition> response = apiInstance.UpdateRecDefinitionWithHttpInfo(scope, code, updateRecDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

