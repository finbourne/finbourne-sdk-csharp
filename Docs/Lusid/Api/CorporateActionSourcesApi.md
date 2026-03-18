# Finbourne.Sdk.Lusid.Api.CorporateActionSourcesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchUpsertCorporateActions**](#batchupsertcorporateactions) | **POST** `/api/api/corporateactionsources/{scope}/{code}/corporateactions` | [EARLY ACCESS] BatchUpsertCorporateActions: Batch upsert corporate actions (instrument transition events) to corporate action source. |
| [**CreateCorporateActionSource**](#createcorporateactionsource) | **POST** `/api/api/corporateactionsources` | [EARLY ACCESS] CreateCorporateActionSource: Create corporate action source |
| [**DeleteCorporateActionSource**](#deletecorporateactionsource) | **DELETE** `/api/api/corporateactionsources/{scope}/{code}` | [EARLY ACCESS] DeleteCorporateActionSource: Delete a corporate action source |
| [**DeleteCorporateActions**](#deletecorporateactions) | **DELETE** `/api/api/corporateactionsources/{scope}/{code}/corporateactions` | [EARLY ACCESS] DeleteCorporateActions: Delete corporate actions (instrument transition events) from a corporate action source |
| [**DeleteInstrumentEvents**](#deleteinstrumentevents) | **DELETE** `/api/api/corporateactionsources/{scope}/{code}/instrumentevents` | [EARLY ACCESS] DeleteInstrumentEvents: Delete instrument events from a corporate action source |
| [**GetCorporateActions**](#getcorporateactions) | **GET** `/api/api/corporateactionsources/{scope}/{code}/corporateactions` | [EARLY ACCESS] GetCorporateActions: List corporate actions (instrument transition events) from the corporate action source. |
| [**GetInstrumentEvents**](#getinstrumentevents) | **GET** `/api/api/corporateactionsources/{scope}/{code}/instrumentevents` | [EARLY ACCESS] GetInstrumentEvents: Get extrinsic instrument events out of a given corporate actions source. |
| [**ListCorporateActionSources**](#listcorporateactionsources) | **GET** `/api/api/corporateactionsources` | [EARLY ACCESS] ListCorporateActionSources: List corporate action sources |
| [**UpsertInstrumentEvents**](#upsertinstrumentevents) | **POST** `/api/api/corporateactionsources/{scope}/{code}/instrumentevents` | [EARLY ACCESS] UpsertInstrumentEvents: Upsert instrument events to the provided corporate actions source. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CorporateActionSourcesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
```

---

<a id="batchupsertcorporateactions"></a>
## BatchUpsertCorporateActions

> UpsertCorporateActionsResponse BatchUpsertCorporateActions(string scope, string code, List<UpsertCorporateActionRequest>? upsertCorporateActionRequest = null)

[EARLY ACCESS] BatchUpsertCorporateActions: Batch upsert corporate actions (instrument transition events) to corporate action source.

Create or update one or more corporate actions in a particular corporate action source. Failures are identified in the body of the response.                If a corporate action is upserted at exactly the same effective datetime as a transaction for the same instrument, the corporate action takes precedence. Depending on the nature of the corporate action, this may mean it affects the transaction.                The maximum number of corporate actions that this method can upsert per request is 10,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertCorporateActionRequest = new List<UpsertCorporateActionRequest>?(); // List<UpsertCorporateActionRequest>? (optional)
UpsertCorporateActionsResponse result = apiInstance.BatchUpsertCorporateActions(scope, code, upsertCorporateActionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of corporate action source |
| **code** | **string** | path | **required** | The code of the corporate action source |
| **upsertCorporateActionRequest** | [List&lt;UpsertCorporateActionRequest&gt;?](UpsertCorporateActionRequest.md) | body | optional | The corporate action definitions |

### Return type

[UpsertCorporateActionsResponse](UpsertCorporateActionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created corporate actions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertCorporateActionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertCorporateActionsResponse> response = apiInstance.BatchUpsertCorporateActionsWithHttpInfo(scope, code, upsertCorporateActionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createcorporateactionsource"></a>
## CreateCorporateActionSource

> CorporateActionSource CreateCorporateActionSource(CreateCorporateActionSourceRequest createCorporateActionSourceRequest)

[EARLY ACCESS] CreateCorporateActionSource: Create corporate action source

Create a corporate action source.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var createCorporateActionSourceRequest = new CreateCorporateActionSourceRequest(); // CreateCorporateActionSourceRequest
CorporateActionSource result = apiInstance.CreateCorporateActionSource(createCorporateActionSourceRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createCorporateActionSourceRequest** | [CreateCorporateActionSourceRequest](CreateCorporateActionSourceRequest.md) | body | **required** | The corporate action source definition |

### Return type

[CorporateActionSource](CorporateActionSource.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created corporate action source |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCorporateActionSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CorporateActionSource> response = apiInstance.CreateCorporateActionSourceWithHttpInfo(createCorporateActionSourceRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecorporateactionsource"></a>
## DeleteCorporateActionSource

> DeletedEntityResponse DeleteCorporateActionSource(string scope, string code)

[EARLY ACCESS] DeleteCorporateActionSource: Delete a corporate action source

Deletes a single corporate action source

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteCorporateActionSource(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the corporate action source to be deleted |
| **code** | **string** | path | **required** | The code of the corporate action source to be deleted |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Corporate Action Source Deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCorporateActionSourceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCorporateActionSourceWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecorporateactions"></a>
## DeleteCorporateActions

> DeletedEntityResponse DeleteCorporateActions(string scope, string code, List<string> corporateActionIds)

[EARLY ACCESS] DeleteCorporateActions: Delete corporate actions (instrument transition events) from a corporate action source

Delete one or more corporate actions from a particular corporate action source.                The maximum number of corporate actions that this method can delete per request is 1,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var corporateActionIds = new List<string>(); // List<string>
DeletedEntityResponse result = apiInstance.DeleteCorporateActions(scope, code, corporateActionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the corporate action source |
| **code** | **string** | path | **required** | The code of the corporate action source |
| **corporateActionIds** | [List&lt;string&gt;](string.md) | query | **required** | The IDs of the corporate actions to delete |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Corporate Actions Deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCorporateActionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCorporateActionsWithHttpInfo(scope, code, corporateActionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinstrumentevents"></a>
## DeleteInstrumentEvents

> DeletedEntityResponse DeleteInstrumentEvents(string scope, string code, List<string> instrumentEventIds)

[EARLY ACCESS] DeleteInstrumentEvents: Delete instrument events from a corporate action source

Delete one or more corporate actions from a particular corporate action source.                The maximum number of instrument events that this method can delete per request is 1,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var instrumentEventIds = new List<string>(); // List<string>
DeletedEntityResponse result = apiInstance.DeleteInstrumentEvents(scope, code, instrumentEventIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the corporate action source |
| **code** | **string** | path | **required** | The code of the corporate action source |
| **instrumentEventIds** | [List&lt;string&gt;](string.md) | query | **required** | The IDs of the instrument events to delete |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instrument Events Deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInstrumentEventsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteInstrumentEventsWithHttpInfo(scope, code, instrumentEventIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcorporateactions"></a>
## GetCorporateActions

> ResourceListOfCorporateAction GetCorporateActions(string scope, string code, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, DateTimeOffset? asAt = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EARLY ACCESS] GetCorporateActions: List corporate actions (instrument transition events) from the corporate action source.

Get corporate actions from a particular corporate action source.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfCorporateAction result = apiInstance.GetCorporateActions(scope, code, fromEffectiveAt, toEffectiveAt, asAt, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the corporate action source. |
| **code** | **string** | path | **required** | The code of the corporate action source. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | Optional. The start effective date of the data range. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | Optional. The end effective date of the data range. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date of the data. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the results to this number. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.              For example, to filter on the Announcement Date, use \&quot;announcementDate eq &#39;2020-03-06&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfCorporateAction](ResourceListOfCorporateAction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Corporate Actions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCorporateActionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfCorporateAction> response = apiInstance.GetCorporateActionsWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentevents"></a>
## GetInstrumentEvents

> PagedResourceListOfInstrumentEventHolder GetInstrumentEvents(string scope, string code, DateTimeOffset? asAt = null, int? limit = null, string? page = null, string? filter = null, string? timelineScope = null, string? timelineCode = null, string? closedPeriodId = null)

[EARLY ACCESS] GetInstrumentEvents: Get extrinsic instrument events out of a given corporate actions source.

Retrieves extrinsic corporate actions out of a corporate actions source

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 1000;  // int? (optional)
var page = "page_example";  // string? (optional)
var filter = "filter_example";  // string? (optional)
var timelineScope = "timelineScope_example";  // string? (optional)
var timelineCode = "timelineCode_example";  // string? (optional)
var closedPeriodId = "closedPeriodId_example";  // string? (optional)
PagedResourceListOfInstrumentEventHolder result = apiInstance.GetInstrumentEvents(scope, code, asAt, limit, page, filter, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the corporate action source. |
| **code** | **string** | path | **required** | The code of the corporate action source. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date of the data. |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. If not specified, a default  of 1000 is used. Default: `1000` |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing items from a previous call. Page values are  return from list calls, and must be supplied exactly as returned. Additionally, when specifying this  value, asAt, filter and limit must not  be modified. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set. |
| **timelineScope** | **string?** | query | optional | The scope of the Timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineCode and closedPeriodId must also be provided. |
| **timelineCode** | **string?** | query | optional | The code of the Timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineScope and closedPeriodId must also be provided. |
| **closedPeriodId** | **string?** | query | optional | The code of the ClosedPeriod attached to the timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineScope and timelineCode must also be provided. |

### Return type

[PagedResourceListOfInstrumentEventHolder](PagedResourceListOfInstrumentEventHolder.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instrument Events |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentEventsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfInstrumentEventHolder> response = apiInstance.GetInstrumentEventsWithHttpInfo(scope, code, asAt, limit, page, filter, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcorporateactionsources"></a>
## ListCorporateActionSources

> PagedResourceListOfCorporateActionSource ListCorporateActionSources(DateTimeOffset? asAt = null, List<string>? sortBy = null, int? limit = null, string? filter = null, string? page = null)

[EARLY ACCESS] ListCorporateActionSources: List corporate action sources

Gets a list of all corporate action sources

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 100;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfCorporateActionSource result = apiInstance.ListCorporateActionSources(asAt, sortBy, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date of the data |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. If not specified, a default  of 100 is used. Default: `100` |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set. For example, to  filter on the Display Name, use \&quot;displayName eq &#39;string&#39;\&quot;  Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing items from a previous call. Page values are  return from list calls, and must be supplied exactly as returned. Additionally, when specifying this  value, the filter, asAt, and limit must not  be modified. |

### Return type

[PagedResourceListOfCorporateActionSource](PagedResourceListOfCorporateActionSource.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | All Existing Corporate Action Sources |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCorporateActionSourcesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCorporateActionSource> response = apiInstance.ListCorporateActionSourcesWithHttpInfo(asAt, sortBy, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertinstrumentevents"></a>
## UpsertInstrumentEvents

> UpsertInstrumentEventsResponse UpsertInstrumentEvents(string scope, string code, List<UpsertInstrumentEventRequest>? upsertInstrumentEventRequest = null)

[EARLY ACCESS] UpsertInstrumentEvents: Upsert instrument events to the provided corporate actions source.

Batch upsert instrument events to corporate action sources.                The maximum number of instrument events that this method can upsert per request is 10,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CorporateActionSourcesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertInstrumentEventRequest = new List<UpsertInstrumentEventRequest>?(); // List<UpsertInstrumentEventRequest>? (optional)
UpsertInstrumentEventsResponse result = apiInstance.UpsertInstrumentEvents(scope, code, upsertInstrumentEventRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the corporate action source. |
| **code** | **string** | path | **required** | The code of the corporate action source. |
| **upsertInstrumentEventRequest** | [List&lt;UpsertInstrumentEventRequest&gt;?](UpsertInstrumentEventRequest.md) | body | optional | The instrument event definitions. |

### Return type

[UpsertInstrumentEventsResponse](UpsertInstrumentEventsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Instrument Events Upserted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertInstrumentEventsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertInstrumentEventsResponse> response = apiInstance.UpsertInstrumentEventsWithHttpInfo(scope, code, upsertInstrumentEventRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

