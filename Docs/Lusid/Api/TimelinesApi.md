# Finbourne.Sdk.Lusid.Api.TimelinesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ConfirmClosedPeriod**](#confirmclosedperiod) | **POST** `/api/api/timelines/{scope}/{code}/closedperiods/{closedPeriodId}/$confirm` | [EXPERIMENTAL] ConfirmClosedPeriod: Confirm a Closed Period against a Timeline Entity |
| [**CreateClosedPeriod**](#createclosedperiod) | **POST** `/api/api/timelines/{scope}/{code}/closedperiods` | [EXPERIMENTAL] CreateClosedPeriod: Create a new closed period against a timeline entity |
| [**CreateClosedPeriodCandidate**](#createclosedperiodcandidate) | **POST** `/api/api/timelines/{scope}/{code}/closedperiods/candidate` | [EXPERIMENTAL] CreateClosedPeriodCandidate: Create a new closed period candidate against a timeline entity |
| [**CreateTimeline**](#createtimeline) | **POST** `/api/api/timelines` | [EXPERIMENTAL] CreateTimeline: Create a Timeline |
| [**DeleteTimeline**](#deletetimeline) | **DELETE** `/api/api/timelines/{scope}/{code}` | [EXPERIMENTAL] DeleteTimeline: Deletes a particular Timeline |
| [**GetClosedPeriod**](#getclosedperiod) | **GET** `/api/api/timelines/{scope}/{code}/closedperiods/{closedPeriodId}` | [EXPERIMENTAL] GetClosedPeriod: Gets a Closed Period entity. |
| [**GetTimeline**](#gettimeline) | **GET** `/api/api/timelines/{scope}/{code}` | [EXPERIMENTAL] GetTimeline: Get a single Timeline by scope and code. |
| [**ListClosedPeriods**](#listclosedperiods) | **GET** `/api/api/timelines/{scope}/{code}/closedperiods` | [EXPERIMENTAL] ListClosedPeriods: List ClosedPeriods for a specified Timeline. |
| [**ListTimelines**](#listtimelines) | **GET** `/api/api/timelines` | [EXPERIMENTAL] ListTimelines: List Timelines |
| [**SetPostCloseActivity**](#setpostcloseactivity) | **POST** `/api/api/timelines/{scope}/{code}/closedperiods/{closedPeriodId}/postcloseactivity` | [EXPERIMENTAL] SetPostCloseActivity: Sets post-close activities to a Closed Period. |
| [**UnconfirmClosedPeriod**](#unconfirmclosedperiod) | **POST** `/api/api/timelines/{scope}/{code}/closedperiods/{closedPeriodId}/$unconfirm` | [EXPERIMENTAL] UnconfirmClosedPeriod: Unconfirm the last confirmed Closed Period against a Timeline Entity |
| [**UpdateTimeline**](#updatetimeline) | **PUT** `/api/api/timelines/{scope}/{code}` | [EXPERIMENTAL] UpdateTimeline: Update Timeline defined by scope and code |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TimelinesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
```

---

<a id="confirmclosedperiod"></a>
## ConfirmClosedPeriod

> ClosedPeriod ConfirmClosedPeriod(string scope, string code, string closedPeriodId, Object? body = null)

[EXPERIMENTAL] ConfirmClosedPeriod: Confirm a Closed Period against a Timeline Entity

Confirms a Closed Period against a Timeline Entity. Deletes any other unconfirmed Closed Periods on the Timeline.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var closedPeriodId = "closedPeriodId_example";  // string
var body = {};  // Object? (optional)
ClosedPeriod result = apiInstance.ConfirmClosedPeriod(scope, code, closedPeriodId, body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the scope this uniquely identifies the Timeline. |
| **closedPeriodId** | **string** | path | **required** | The id of the Closed Period. Together with the scope and code of the Timeline,              this uniquely identifies the ClosedPeriod |
| **body** | **Object?** | body | optional | Not in use at the moment |

### Return type

[ClosedPeriod](ClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The confirmed closed period |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ConfirmClosedPeriodWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClosedPeriod> response = apiInstance.ConfirmClosedPeriodWithHttpInfo(scope, code, closedPeriodId, body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createclosedperiod"></a>
## CreateClosedPeriod

> ClosedPeriod CreateClosedPeriod(string scope, string code, CreateClosedPeriodRequest? createClosedPeriodRequest = null)

[EXPERIMENTAL] CreateClosedPeriod: Create a new closed period against a timeline entity

Creates a new closed period against a timeline entity  Returns the newly created closed period entity with properties

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createClosedPeriodRequest = new CreateClosedPeriodRequest?(); // CreateClosedPeriodRequest? (optional)
ClosedPeriod result = apiInstance.CreateClosedPeriod(scope, code, createClosedPeriodRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the domain and scope this uniquely identifies the Timeline. |
| **createClosedPeriodRequest** | [CreateClosedPeriodRequest?](CreateClosedPeriodRequest?.md) | body | optional | The request containing the details of the Closed Period |

### Return type

[ClosedPeriod](ClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created closed period |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateClosedPeriodWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClosedPeriod> response = apiInstance.CreateClosedPeriodWithHttpInfo(scope, code, createClosedPeriodRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createclosedperiodcandidate"></a>
## CreateClosedPeriodCandidate

> ClosedPeriod CreateClosedPeriodCandidate(string scope, string code, CreateClosedPeriodRequest? createClosedPeriodRequest = null)

[EXPERIMENTAL] CreateClosedPeriodCandidate: Create a new closed period candidate against a timeline entity

Creates a new closed period candidate against a timeline entity  Returns the newly created closed period candidate entity with properties

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createClosedPeriodRequest = new CreateClosedPeriodRequest?(); // CreateClosedPeriodRequest? (optional)
ClosedPeriod result = apiInstance.CreateClosedPeriodCandidate(scope, code, createClosedPeriodRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the scope this uniquely identifies the Timeline. |
| **createClosedPeriodRequest** | [CreateClosedPeriodRequest?](CreateClosedPeriodRequest?.md) | body | optional | The request containing the details of the Closed Period |

### Return type

[ClosedPeriod](ClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created closed period |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateClosedPeriodCandidateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClosedPeriod> response = apiInstance.CreateClosedPeriodCandidateWithHttpInfo(scope, code, createClosedPeriodRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createtimeline"></a>
## CreateTimeline

> Timeline CreateTimeline(CreateTimelineRequest? createTimelineRequest = null)

[EXPERIMENTAL] CreateTimeline: Create a Timeline

Creates a Timeline. Returns the created Timeline at the current effectiveAt.  Note that Timelines are mono-temporal, however they can have Time-Variant Properties.  Upserted Properties will be returned at the latest AsAt and EffectiveAt

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var createTimelineRequest = new CreateTimelineRequest?(); // CreateTimelineRequest? (optional)
Timeline result = apiInstance.CreateTimeline(createTimelineRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createTimelineRequest** | [CreateTimelineRequest?](CreateTimelineRequest?.md) | body | optional | The request containing the details of the Timeline |

### Return type

[Timeline](Timeline.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created Timeline |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTimelineWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Timeline> response = apiInstance.CreateTimelineWithHttpInfo(createTimelineRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetimeline"></a>
## DeleteTimeline

> DeletedEntityResponse DeleteTimeline(string scope, string code)

[EXPERIMENTAL] DeleteTimeline: Deletes a particular Timeline

The deletion will take effect from the Timeline deletion datetime.  i.e. will no longer exist at any asAt datetime after the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTimeline(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the domain and scope this uniquely              identifies the Timeline. |

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
<summary>Using the DeleteTimelineWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTimelineWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getclosedperiod"></a>
## GetClosedPeriod

> ClosedPeriod GetClosedPeriod(string scope, string code, string closedPeriodId, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetClosedPeriod: Gets a Closed Period entity.

Retrieves one ClosedPeriod uniquely defined by the Timelines Scope/Code and a ClosedPeriodId.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var closedPeriodId = "closedPeriodId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ClosedPeriod result = apiInstance.GetClosedPeriod(scope, code, closedPeriodId, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Timeline. |
| **code** | **string** | path | **required** | The code of the Timeline. Together with the scope this uniquely              identifies the Timeline. |
| **closedPeriodId** | **string** | path | **required** | The id of the Closed Period. Together with the scope and code of the Timeline,              this uniquely identifies the ClosedPeriod |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the ClosedPeriod definition. Defaults to return              the latest version of the definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;ClosedPeriod&#39; domain to decorate onto              the ClosedPeriod.              These must have the format {domain}/{scope}/{code}, for example &#39;ClosedPeriod/system/Name&#39;. |

### Return type

[ClosedPeriod](ClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested closed period |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetClosedPeriodWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClosedPeriod> response = apiInstance.GetClosedPeriodWithHttpInfo(scope, code, closedPeriodId, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettimeline"></a>
## GetTimeline

> Timeline GetTimeline(string scope, string code, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetTimeline: Get a single Timeline by scope and code.

Retrieves one Timeline by scope and code.  Timelines are mono-temporal. The EffectiveAt is only applied to Time-Variant Properties.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Timeline result = apiInstance.GetTimeline(scope, code, asAt, effectiveAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the scope this uniquely              identifies the Timeline. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Timeline definition. Defaults to return              the latest version of the definition if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the timeline properties.              Defaults to the current LUSID system datetime if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Timeline&#39; domain to decorate onto              the Timeline.              These must have the format {domain}/{scope}/{code}, for example &#39;Timeline/system/Name&#39;. |

### Return type

[Timeline](Timeline.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Timeline |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTimelineWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Timeline> response = apiInstance.GetTimelineWithHttpInfo(scope, code, asAt, effectiveAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listclosedperiods"></a>
## ListClosedPeriods

> PagedResourceListOfClosedPeriod ListClosedPeriods(string scope, string code, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListClosedPeriods: List ClosedPeriods for a specified Timeline.

List all the ClosedPeriods matching a particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfClosedPeriod result = apiInstance.ListClosedPeriods(scope, code, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Timeline. |
| **code** | **string** | path | **required** | The code of the Timeline. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the ClosedPeriods. Defaults to returning the latest version of each ClosedPeriod if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing ClosedPeriods; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the effectiveEnd, specify \&quot;effectiveEnd gt 2019-01-15T10:00:00\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;ClosedPeriod&#39; domain to decorate onto each ClosedPeriod.              These must take the format {domain}/{scope}/{code}, for example &#39;ClosedPeriod/Account/id&#39;. |

### Return type

[PagedResourceListOfClosedPeriod](PagedResourceListOfClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested ClosedPeriods. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListClosedPeriodsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfClosedPeriod> response = apiInstance.ListClosedPeriodsWithHttpInfo(scope, code, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtimelines"></a>
## ListTimelines

> PagedResourceListOfTimeline ListTimelines(DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListTimelines: List Timelines

List all the Timelines matching a particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfTimeline result = apiInstance.ListTimelines(asAt, effectiveAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Timelines. Defaults to returning the latest version of each Timeline if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Timelines.              Note that Timelines are monotemporal, the effectiveAt is for Timevariant Properties on the Timeline only.              Defaults to the current LUSID system datetime if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Timelines; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the displayName, specify \&quot;displayName eq &#39;AccountingTimeline&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Timeline&#39; domain to decorate onto each Timeline.              These must take the format {domain}/{scope}/{code}, for example &#39;Timeline/Account/id&#39;. |

### Return type

[PagedResourceListOfTimeline](PagedResourceListOfTimeline.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Timelines. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTimelinesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTimeline> response = apiInstance.ListTimelinesWithHttpInfo(asAt, effectiveAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setpostcloseactivity"></a>
## SetPostCloseActivity

> ClosedPeriod SetPostCloseActivity(string scope, string code, string closedPeriodId, PostCloseActivitiesRequest? postCloseActivitiesRequest = null)

[EXPERIMENTAL] SetPostCloseActivity: Sets post-close activities to a Closed Period.

This sets the given post-close activities to the given Closed Period.                **This is an overwriting action!**                The possible types of entity are:  * `PortfolioTransaction`,  * `Instrument`,  * `InstrumentEvent`,  * `InstrumentEventInstruction`,  * `PortfolioSettlementInstruction`, and,  * `Quote`.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var closedPeriodId = "closedPeriodId_example";  // string
var postCloseActivitiesRequest = new PostCloseActivitiesRequest?(); // PostCloseActivitiesRequest? (optional)
ClosedPeriod result = apiInstance.SetPostCloseActivity(scope, code, closedPeriodId, postCloseActivitiesRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Timeline. |
| **code** | **string** | path | **required** | The code of the Timeline. |
| **closedPeriodId** | **string** | path | **required** | The ID of the Closed Period.               This ID together with the scope and code of the Timeline uniquely defines the Closed Period. |
| **postCloseActivitiesRequest** | [PostCloseActivitiesRequest?](PostCloseActivitiesRequest?.md) | body | optional | This specifies a collection of post-close activities. |

### Return type

[ClosedPeriod](ClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Closed Period. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPostCloseActivityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClosedPeriod> response = apiInstance.SetPostCloseActivityWithHttpInfo(scope, code, closedPeriodId, postCloseActivitiesRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="unconfirmclosedperiod"></a>
## UnconfirmClosedPeriod

> ClosedPeriod UnconfirmClosedPeriod(string scope, string code, string closedPeriodId, Object? body = null)

[EXPERIMENTAL] UnconfirmClosedPeriod: Unconfirm the last confirmed Closed Period against a Timeline Entity

Unconfirm the last confirmed Closed Period against a Timeline Entity

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var closedPeriodId = "closedPeriodId_example";  // string
var body = {};  // Object? (optional)
ClosedPeriod result = apiInstance.UnconfirmClosedPeriod(scope, code, closedPeriodId, body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the scope this uniquely identifies the Timeline. |
| **closedPeriodId** | **string** | path | **required** | The id of the Closed Period. Together with the scope and code of the Timeline,              this uniquely identifies the ClosedPeriod. The closed period must be the last closed period on the Timeline. |
| **body** | **Object?** | body | optional | Not in use at the moment |

### Return type

[ClosedPeriod](ClosedPeriod.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The unconfirmed closed period |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UnconfirmClosedPeriodWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ClosedPeriod> response = apiInstance.UnconfirmClosedPeriodWithHttpInfo(scope, code, closedPeriodId, body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatetimeline"></a>
## UpdateTimeline

> Timeline UpdateTimeline(string scope, string code, UpdateTimelineRequest? updateTimelineRequest = null)

[EXPERIMENTAL] UpdateTimeline: Update Timeline defined by scope and code

Overwrites an existing Timeline  Update request has the same required fields as Create apart from the id.  Returns the updated Timeline at the current effectiveAt.  Note that Timelines are mono-temporal, however they can have Time-Variant Properties.  Updated Properties will be returned at the latest AsAt and EffectiveAt

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TimelinesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateTimelineRequest = new UpdateTimelineRequest?(); // UpdateTimelineRequest? (optional)
Timeline result = apiInstance.UpdateTimeline(scope, code, updateTimelineRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Timeline. |
| **code** | **string** | path | **required** | The code of the specified Timeline. Together with the domain and scope this uniquely identifies the Timeline. |
| **updateTimelineRequest** | [UpdateTimelineRequest?](UpdateTimelineRequest?.md) | body | optional | The request containing the updated details of the Timeline |

### Return type

[Timeline](Timeline.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated version of the requested Timeline |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateTimelineWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Timeline> response = apiInstance.UpdateTimelineWithHttpInfo(scope, code, updateTimelineRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

