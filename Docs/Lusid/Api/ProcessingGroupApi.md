# Finbourne.Sdk.Lusid.Api.ProcessingGroupApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateProcessingGroup**](#createprocessinggroup) | **POST** `/api/api/processinggroups/{scope}` | [EXPERIMENTAL] CreateProcessingGroup: Create a Processing Group. |
| [**DeleteProcessingGroup**](#deleteprocessinggroup) | **DELETE** `/api/api/processinggroups/{scope}/{code}` | [EXPERIMENTAL] DeleteProcessingGroup: Delete a Processing Group. |
| [**GetProcessingGroup**](#getprocessinggroup) | **GET** `/api/api/processinggroups/{scope}/{code}` | [EXPERIMENTAL] GetProcessingGroup: Get a Processing Group. |
| [**GetProcessingGroupNextScheduledDetails**](#getprocessinggroupnextscheduleddetails) | **GET** `/api/api/processinggroups/{scope}/{code}/schedule/$next` | [EXPERIMENTAL] GetProcessingGroupNextScheduledDetails: Get the next scheduled date of a Processing Group. |
| [**GetResolvedProcessingGroupSchedule**](#getresolvedprocessinggroupschedule) | **GET** `/api/api/processinggroups/{scope}/{code}/schedule/$dates` | [EXPERIMENTAL] GetResolvedProcessingGroupSchedule: Get the resolved schedule of a Processing Group. |
| [**ListProcessingGroups**](#listprocessinggroups) | **GET** `/api/api/processinggroups` | [EXPERIMENTAL] ListProcessingGroups: List Processing Groups. |
| [**PatchProcessingGroup**](#patchprocessinggroup) | **PATCH** `/api/api/processinggroups/{scope}/{code}` | [EXPERIMENTAL] PatchProcessingGroup: Patch a Processing Group. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ProcessingGroupApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
```

---

<a id="createprocessinggroup"></a>
## CreateProcessingGroup

> ProcessingGroup CreateProcessingGroup(string scope, ProcessingGroupRequest processingGroupRequest)

[EXPERIMENTAL] CreateProcessingGroup: Create a Processing Group.

Create the given Processing Group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var scope = "scope_example";  // string
var processingGroupRequest = new ProcessingGroupRequest(); // ProcessingGroupRequest
ProcessingGroup result = apiInstance.CreateProcessingGroup(scope, processingGroupRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Processing Group. |
| **processingGroupRequest** | [ProcessingGroupRequest](../Model/ProcessingGroupRequest.md) | body | **required** | The definition of the Processing Group. |

### Return type

[ProcessingGroup](../Model/ProcessingGroup.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Processing Group. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateProcessingGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ProcessingGroup> response = apiInstance.CreateProcessingGroupWithHttpInfo(scope, processingGroupRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteprocessinggroup"></a>
## DeleteProcessingGroup

> DeletedEntityResponse DeleteProcessingGroup(string scope, string code)

[EXPERIMENTAL] DeleteProcessingGroup: Delete a Processing Group.

Delete the given Processing Group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteProcessingGroup(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Processing Group to be deleted. |
| **code** | **string** | path | **required** | The code of the Processing Group to be deleted. Together with the scope this uniquely identifies the Processing Group. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Processing Group was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteProcessingGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteProcessingGroupWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprocessinggroup"></a>
## GetProcessingGroup

> ProcessingGroup GetProcessingGroup(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetProcessingGroup: Get a Processing Group.

Retrieve the definition of a particular Processing Group, including the resolved (executed) contents  of its referenced reference list.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ProcessingGroup result = apiInstance.GetProcessingGroup(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Processing Group. |
| **code** | **string** | path | **required** | The code of the Processing Group. Together with the scope this uniquely identifies the Processing Group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Processing Group. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Processing Group. Defaults to returning the latest version if not specified. |

### Return type

[ProcessingGroup](../Model/ProcessingGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Processing Group definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetProcessingGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ProcessingGroup> response = apiInstance.GetProcessingGroupWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprocessinggroupnextscheduleddetails"></a>
## GetProcessingGroupNextScheduledDetails

> ProcessingGroupNextScheduledDetails GetProcessingGroupNextScheduledDetails(string scope, string code, DateTimeOrCutLabel effectiveAt, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetProcessingGroupNextScheduledDetails: Get the next scheduled date of a Processing Group.

Return the first execution date strictly after the given date, bounded by the schedule's end,  together with the reference list resolved at that date.  Returns 404 if the schedule has no further dates or the referenced reference list no longer exists,  and fails rather than returning a date without a list if the list cannot be resolved.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ProcessingGroupNextScheduledDetails result = apiInstance.GetProcessingGroupNextScheduledDetails(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Processing Group. |
| **code** | **string** | path | **required** | The code of the Processing Group. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The date after which to find the next scheduled date. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to read the Processing Group and its holiday calendars. |

### Return type

[ProcessingGroupNextScheduledDetails](../Model/ProcessingGroupNextScheduledDetails.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The next scheduled date and the resolved reference list. |  -  |
| **404** | The schedule has no date after the given date, or the referenced reference list does not exist. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetProcessingGroupNextScheduledDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ProcessingGroupNextScheduledDetails> response = apiInstance.GetProcessingGroupNextScheduledDetailsWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getresolvedprocessinggroupschedule"></a>
## GetResolvedProcessingGroupSchedule

> List&lt;DateTimeOffset&gt; GetResolvedProcessingGroupSchedule(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetResolvedProcessingGroupSchedule: Get the resolved schedule of a Processing Group.

Resolve the Processing Group's schedule into the concrete set of execution dates that fall within the  given range, applying its tenor, roll convention, business-day convention and holiday calendars.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<DateTimeOffset> result = apiInstance.GetResolvedProcessingGroupSchedule(scope, code, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Processing Group. |
| **code** | **string** | path | **required** | The code of the Processing Group. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The inclusive start of the date range over which to resolve the schedule. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The inclusive end of the date range over which to resolve the schedule. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to read the Processing Group and its holiday calendars. |

### Return type

**List<DateTimeOffset>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The resolved schedule dates within the range. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetResolvedProcessingGroupScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<DateTimeOffset>> response = apiInstance.GetResolvedProcessingGroupScheduleWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listprocessinggroups"></a>
## ListProcessingGroups

> PagedResourceListOfProcessingGroup ListProcessingGroups(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListProcessingGroups: List Processing Groups.

List all the Processing Groups matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfProcessingGroup result = apiInstance.ListProcessingGroups(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Processing Groups. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Processing Groups. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Processing Groups. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfProcessingGroup](../Model/PagedResourceListOfProcessingGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Processing Groups. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListProcessingGroupsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfProcessingGroup> response = apiInstance.ListProcessingGroupsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchprocessinggroup"></a>
## PatchProcessingGroup

> ProcessingGroup PatchProcessingGroup(string scope, string code, List<Operation> operation)

[EXPERIMENTAL] PatchProcessingGroup: Patch a Processing Group.

Create or update certain fields (display name, description, schedule) for a particular Processing Group.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description, Schedule, WorkflowId, ListExceptionFilter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessingGroupApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
ProcessingGroup result = apiInstance.PatchProcessingGroup(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Processing Group. |
| **code** | **string** | path | **required** | The code of the Processing Group. Together with the scope this uniquely identifies the Processing Group. |
| **operation** | [List&lt;Operation&gt;](../Model/Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[ProcessingGroup](../Model/ProcessingGroup.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched Processing Group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchProcessingGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ProcessingGroup> response = apiInstance.PatchProcessingGroupWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

