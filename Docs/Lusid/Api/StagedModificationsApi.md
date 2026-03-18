# Finbourne.Sdk.Lusid.Api.StagedModificationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddDecision**](#adddecision) | **POST** `/api/api/stagedmodifications/{id}/decision` | AddDecision: AddDecision |
| [**GetStagedModification**](#getstagedmodification) | **GET** `/api/api/stagedmodifications/{id}` | GetStagedModification: GetStagedModification |
| [**ListRequestedChanges**](#listrequestedchanges) | **GET** `/api/api/stagedmodifications/{id}/requestedChanges` | ListRequestedChanges: ListRequestedChanges |
| [**ListStagedModifications**](#liststagedmodifications) | **GET** `/api/api/stagedmodifications` | ListStagedModifications: ListStagedModifications |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<StagedModificationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagedModificationsApi>();
```

---

<a id="adddecision"></a>
## AddDecision

> StagedModification AddDecision(string id, StagedModificationDecisionRequest stagedModificationDecisionRequest)

AddDecision: AddDecision

Add decision to staged modification, Approve or Reject.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagedModificationsApi>();
var id = "id_example";  // string
var stagedModificationDecisionRequest = new StagedModificationDecisionRequest(); // StagedModificationDecisionRequest
StagedModification result = apiInstance.AddDecision(id, stagedModificationDecisionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique Id for a staged modification.. |
| **stagedModificationDecisionRequest** | [StagedModificationDecisionRequest](StagedModificationDecisionRequest.md) | body | **required** | The decision on the requested staged modification, \&quot;Approve\&quot; or \&quot;Reject\&quot;. |

### Return type

[StagedModification](StagedModification.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The staged modification. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddDecisionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StagedModification> response = apiInstance.AddDecisionWithHttpInfo(id, stagedModificationDecisionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getstagedmodification"></a>
## GetStagedModification

> StagedModification GetStagedModification(string id, DateTimeOffset? asAt = null)

GetStagedModification: GetStagedModification

Retrieve the details of a staged modification.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagedModificationsApi>();
var id = "id_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
StagedModification result = apiInstance.GetStagedModification(id, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for a staged modification. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the staged modification. Defaults to latest if not specified. |

### Return type

[StagedModification](StagedModification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested staged modification. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetStagedModificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StagedModification> response = apiInstance.GetStagedModificationWithHttpInfo(id, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrequestedchanges"></a>
## ListRequestedChanges

> PagedResourceListOfStagedModificationsRequestedChangeInterval ListRequestedChanges(string id, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

ListRequestedChanges: ListRequestedChanges

List the requested changes for a staged modification.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagedModificationsApi>();
var id = "id_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfStagedModificationsRequestedChangeInterval result = apiInstance.ListRequestedChanges(id, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique Id for a staged modification.. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list changes. Defaults to return the latest version              of each staged change if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing requested staged modification changes from a previous call to list requested              staged modifications. This value is returned from the previous call. If a pagination token is provided the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfStagedModificationsRequestedChangeInterval](PagedResourceListOfStagedModificationsRequestedChangeInterval.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested changes in staged modification. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRequestedChangesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStagedModificationsRequestedChangeInterval> response = apiInstance.ListRequestedChangesWithHttpInfo(id, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="liststagedmodifications"></a>
## ListStagedModifications

> PagedResourceListOfStagedModification ListStagedModifications(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

ListStagedModifications: ListStagedModifications

List summaries of the staged modifications.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagedModificationsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfStagedModification result = apiInstance.ListStagedModifications(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list staged modifications. Defaults to return the latest version              of each staged modification if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing staged modifications from a previous call to list staged modifications. This              value is returned from the previous call. If a pagination token is provided the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfStagedModification](PagedResourceListOfStagedModification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List summary of staged modifications. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListStagedModificationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStagedModification> response = apiInstance.ListStagedModificationsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

