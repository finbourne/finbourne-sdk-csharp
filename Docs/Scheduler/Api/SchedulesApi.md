# Finbourne.Sdk.Scheduler.Api.SchedulesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateSchedule**](#createschedule) | **POST** `/scheduler2/api/schedules` | CreateSchedule: Create a Schedule for a job |
| [**DeleteSchedule**](#deleteschedule) | **DELETE** `/scheduler2/api/schedules/{scope}/{code}` | DeleteSchedule: Delete a schedule |
| [**EnabledSchedule**](#enabledschedule) | **PUT** `/scheduler2/api/schedules/{scope}/{code}/enabled` | EnabledSchedule: Enable/disable a schedule |
| [**GetSchedule**](#getschedule) | **GET** `/scheduler2/api/schedules/{scope}/{code}` | GetSchedule: Get a single Schedule |
| [**GetValidTimezones**](#getvalidtimezones) | **GET** `/scheduler2/api/schedules/timezones` | GetValidTimezones: Get a list of valid timezones |
| [**ListSchedules**](#listschedules) | **GET** `/scheduler2/api/schedules` | ListSchedules: List the available Schedules |
| [**RunSchedule**](#runschedule) | **POST** `/scheduler2/api/schedules/{scope}/{code}/$run` | RunSchedule: Run a schedule immediately |
| [**UpdateSchedule**](#updateschedule) | **PUT** `/scheduler2/api/schedules/{scope}/{code}` | UpdateSchedule: Update a schedule. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Scheduler.Api;
using Finbourne.Sdk.Scheduler.Client;
using Finbourne.Sdk.Scheduler.Extensions;
using Finbourne.Sdk.Services.Scheduler.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SchedulesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
```

---

<a id="createschedule"></a>
## CreateSchedule

> ScheduleDefinition CreateSchedule(CreateScheduleRequest createScheduleRequest)

CreateSchedule: Create a Schedule for a job

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var createScheduleRequest = new CreateScheduleRequest(); // CreateScheduleRequest
ScheduleDefinition result = apiInstance.CreateSchedule(createScheduleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createScheduleRequest** | [CreateScheduleRequest](CreateScheduleRequest.md) | body | **required** |  |

### Return type

[ScheduleDefinition](ScheduleDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created schedule |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ScheduleDefinition> response = apiInstance.CreateScheduleWithHttpInfo(createScheduleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteschedule"></a>
## DeleteSchedule

> void DeleteSchedule(string scope, string code)

DeleteSchedule: Delete a schedule

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
apiInstance.DeleteSchedule(scope, code);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the schedule to be deleted |
| **code** | **string** | path | **required** | Code of the schedule to be deleted |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteScheduleWithHttpInfo(scope, code);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="enabledschedule"></a>
## EnabledSchedule

> ScheduleDefinition EnabledSchedule(string scope, string code, bool enable)

EnabledSchedule: Enable/disable a schedule

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var enable = true;  // bool
ScheduleDefinition result = apiInstance.EnabledSchedule(scope, code, enable);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the schedule to be enabled/disabled |
| **code** | **string** | path | **required** | Code of the schedule to be enabled/disabled |
| **enable** | **bool** | query | **required** | Specify whether to enable or disable the schedule |

### Return type

[ScheduleDefinition](ScheduleDefinition.md)

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
<summary>Using the EnabledScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ScheduleDefinition> response = apiInstance.EnabledScheduleWithHttpInfo(scope, code, enable);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getschedule"></a>
## GetSchedule

> ScheduleDefinition GetSchedule(string scope, string code)

GetSchedule: Get a single Schedule

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
ScheduleDefinition result = apiInstance.GetSchedule(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of Schedule |
| **code** | **string** | path | **required** | The code of the Schedule |

### Return type

[ScheduleDefinition](ScheduleDefinition.md)

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
<summary>Using the GetScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ScheduleDefinition> response = apiInstance.GetScheduleWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvalidtimezones"></a>
## GetValidTimezones

> ResourceListOfString GetValidTimezones()

GetValidTimezones: Get a list of valid timezones

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
ResourceListOfString result = apiInstance.GetValidTimezones();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfString](ResourceListOfString.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValidTimezonesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfString> response = apiInstance.GetValidTimezonesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listschedules"></a>
## ListSchedules

> ResourceListOfScheduleDefinition ListSchedules(string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

ListSchedules: List the available Schedules

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 2000;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfScheduleDefinition result = apiInstance.ListSchedules(page, sortBy, start, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing instruments from a previous call to list instruments.             This value is returned from the previous call. If a pagination token is provided the sortBy and filter fields             must not have changed since the original request. Also, if set, a start value cannot be provided. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. |
| **start** | **int?** | query | optional | When paginating, skip this number of results. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 2000 if not specified. Maximum is 5000. Default: `2000` |
| **filter** | **string?** | query | optional | Expression to filter the result set. |

### Return type

[ResourceListOfScheduleDefinition](ResourceListOfScheduleDefinition.md)

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
<summary>Using the ListSchedulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScheduleDefinition> response = apiInstance.ListSchedulesWithHttpInfo(page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runschedule"></a>
## RunSchedule

> StartScheduleResponse RunSchedule(string scope, string code)

RunSchedule: Run a schedule immediately

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
StartScheduleResponse result = apiInstance.RunSchedule(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The schedule scope |
| **code** | **string** | path | **required** | The schedule cde |

### Return type

[StartScheduleResponse](StartScheduleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Accepted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StartScheduleResponse> response = apiInstance.RunScheduleWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateschedule"></a>
## UpdateSchedule

> ScheduleDefinition UpdateSchedule(string scope, string code, UpdateScheduleRequest updateScheduleRequest)

UpdateSchedule: Update a schedule.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateScheduleRequest = new UpdateScheduleRequest(); // UpdateScheduleRequest
ScheduleDefinition result = apiInstance.UpdateSchedule(scope, code, updateScheduleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the schedule to be updated |
| **code** | **string** | path | **required** | Code of the schedule to be updated |
| **updateScheduleRequest** | [UpdateScheduleRequest](UpdateScheduleRequest.md) | body | **required** | The updated schedule |

### Return type

[ScheduleDefinition](ScheduleDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ScheduleDefinition> response = apiInstance.UpdateScheduleWithHttpInfo(scope, code, updateScheduleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

