# Finbourne.Sdk.Lusid.Api.RecsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddRecResultSetApprovalDecision**](#addrecresultsetapprovaldecision) | **POST** `/api/api/recs/resultsets/{entityUniqueId}/$decide` | [EXPERIMENTAL] AddRecResultSetApprovalDecision: AddRecResultSetApprovalDecision |
| [**GetRecInstance**](#getrecinstance) | **GET** `/api/api/recs/instances/{instanceIdType}/{instanceIdValue}` | [EXPERIMENTAL] GetRecInstance: GetRecInstance |
| [**GetRecResultSet**](#getrecresultset) | **GET** `/api/api/recs/resultsets/{entityUniqueId}` | [EXPERIMENTAL] GetRecResultSet: GetRecResultSet |
| [**InstantiateRec**](#instantiaterec) | **POST** `/api/api/recs/instances` | [EXPERIMENTAL] InstantiateRec: InstantiateRec |
| [**ListRecInstances**](#listrecinstances) | **GET** `/api/api/recs/instances` | [EXPERIMENTAL] ListRecInstances: ListRecInstances |
| [**ListRecResultSets**](#listrecresultsets) | **GET** `/api/api/recs/resultsets` | [EXPERIMENTAL] ListRecResultSets: ListRecResultSets |
| [**SubmitRecResultSetReview**](#submitrecresultsetreview) | **POST** `/api/api/recs/resultsets/{entityUniqueId}/$submit` | [EXPERIMENTAL] SubmitRecResultSetReview: Submit a rec result set review for approval, or resubmit after addressing requested revisions. |
| [**TransitionRecInstance**](#transitionrecinstance) | **POST** `/api/api/recs/instances/{instanceIdType}/{instanceIdValue}/$transition` | [EXPERIMENTAL] TransitionRecInstance: TransitionRecInstance |

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
| **recResultSetApprovalDecisionRequest** | [RecResultSetApprovalDecisionRequest](RecResultSetApprovalDecisionRequest.md) | body | **required** | The approval decision request. |

### Return type

[RecResultSet](RecResultSet.md)

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

[RecInstance](RecInstance.md)

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

[RecResultSet](RecResultSet.md)

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
| **instantiateRecRequest** | [InstantiateRecRequest](InstantiateRecRequest.md) | body | **required** | The instantiation request. |

### Return type

[RecInstance](RecInstance.md)

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
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfRecInstance](PagedResourceListOfRecInstance.md)

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
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfRecResultSet](PagedResourceListOfRecResultSet.md)

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
| **submitRecResultSetReviewRequest** | [SubmitRecResultSetReviewRequest](SubmitRecResultSetReviewRequest.md) | body | **required** | The submission request. |

### Return type

[RecResultSet](RecResultSet.md)

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
| **transitionRecInstanceRequest** | [TransitionRecInstanceRequest](TransitionRecInstanceRequest.md) | body | **required** | The transition request. |

### Return type

[RecInstance](RecInstance.md)

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

