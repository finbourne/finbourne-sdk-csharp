# Finbourne.Sdk.Scheduler.Api.JobsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateJob**](#createjob) | **POST** `/scheduler2/api/jobs` | CreateJob: Create a new job |
| [**DeleteJob**](#deletejob) | **DELETE** `/scheduler2/api/jobs/{scope}/{code}` | DeleteJob: Delete a job |
| [**GetHistory**](#gethistory) | **GET** `/scheduler2/api/jobs/history` | GetHistory: Get the history of job runs |
| [**GetJobConsoleOutput**](#getjobconsoleoutput) | **GET** `/scheduler2/api/jobs/history/{runId}/console` | GetJobConsoleOutput: Gets the console output of a specific job run |
| [**GetRunHistory**](#getrunhistory) | **GET** `/scheduler2/api/jobs/history/{runId}` | GetRunHistory: Get the history for a single job run |
| [**GetSchedulesForAJob**](#getschedulesforajob) | **GET** `/scheduler2/api/jobs/{scope}/{code}/schedules` | GetSchedulesForAJob: Get all the schedules for a single job |
| [**ListJobs**](#listjobs) | **GET** `/scheduler2/api/jobs` | ListJobs: List the available jobs |
| [**RunJob**](#runjob) | **POST** `/scheduler2/api/jobs/{scope}/{code}/$run` | RunJob: Run a job immediately |
| [**UpdateJob**](#updatejob) | **PUT** `/scheduler2/api/jobs/{scope}/{code}` | UpdateJob: Update a JobDefinition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<JobsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
```

---

<a id="createjob"></a>
## CreateJob

> JobDefinition CreateJob(CreateJobRequest createJobRequest)

CreateJob: Create a new job

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var createJobRequest = new CreateJobRequest(); // CreateJobRequest
JobDefinition result = apiInstance.CreateJob(createJobRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createJobRequest** | [CreateJobRequest](CreateJobRequest.md) | body | **required** | The request to create a new job |

### Return type

[JobDefinition](JobDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateJobWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<JobDefinition> response = apiInstance.CreateJobWithHttpInfo(createJobRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletejob"></a>
## DeleteJob

> ResourceListOfScheduleDefinition DeleteJob(string scope, string code)

DeleteJob: Delete a job

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
ResourceListOfScheduleDefinition result = apiInstance.DeleteJob(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the job |
| **code** | **string** | path | **required** | The code of the job |

### Return type

[ResourceListOfScheduleDefinition](ResourceListOfScheduleDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteJobWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScheduleDefinition> response = apiInstance.DeleteJobWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gethistory"></a>
## GetHistory

> ResourceListOfJobHistory GetHistory(string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

GetHistory: Get the history of job runs

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfJobHistory result = apiInstance.GetHistory(page, sortBy, start, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing instruments from a previous call to list instruments.             This value is returned from the previous call. If a pagination token is provided the sortBy and filter fields             must not have changed since the original request. Also, if set, a start value cannot be provided. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. |
| **start** | **int?** | query | optional | This field is obsolete, the value of this field would not be considered. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 2000 if not specified. Maximum is 5000. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |

### Return type

[ResourceListOfJobHistory](ResourceListOfJobHistory.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfJobHistory> response = apiInstance.GetHistoryWithHttpInfo(page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getjobconsoleoutput"></a>
## GetJobConsoleOutput

> string GetJobConsoleOutput(string runId)

GetJobConsoleOutput: Gets the console output of a specific job run

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var runId = "runId_example";  // string
string result = apiInstance.GetJobConsoleOutput(runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The RunId of the job run |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetJobConsoleOutputWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetJobConsoleOutputWithHttpInfo(runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrunhistory"></a>
## GetRunHistory

> JobRunResult GetRunHistory(string runId)

GetRunHistory: Get the history for a single job run

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var runId = "runId_example";  // string
JobRunResult result = apiInstance.GetRunHistory(runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The unique ID of the run |

### Return type

[JobRunResult](JobRunResult.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRunHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<JobRunResult> response = apiInstance.GetRunHistoryWithHttpInfo(runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getschedulesforajob"></a>
## GetSchedulesForAJob

> ResourceListOfScheduleDefinition GetSchedulesForAJob(string scope, string code)

GetSchedulesForAJob: Get all the schedules for a single job

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
ResourceListOfScheduleDefinition result = apiInstance.GetSchedulesForAJob(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the job |
| **code** | **string** | path | **required** | The code of the job |

### Return type

[ResourceListOfScheduleDefinition](ResourceListOfScheduleDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSchedulesForAJobWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScheduleDefinition> response = apiInstance.GetSchedulesForAJobWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listjobs"></a>
## ListJobs

> ResourceListOfJobDefinition ListJobs(string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

ListJobs: List the available jobs

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 2000;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfJobDefinition result = apiInstance.ListJobs(page, sortBy, start, limit, filter);
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

[ResourceListOfJobDefinition](ResourceListOfJobDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListJobsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfJobDefinition> response = apiInstance.ListJobsWithHttpInfo(page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runjob"></a>
## RunJob

> StartJobResponse RunJob(string scope, string code, StartJobRequest startJobRequest)

RunJob: Run a job immediately

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var startJobRequest = new StartJobRequest(); // StartJobRequest
StartJobResponse result = apiInstance.RunJob(scope, code, startJobRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the job |
| **code** | **string** | path | **required** | The code of the job |
| **startJobRequest** | [StartJobRequest](StartJobRequest.md) | body | **required** | The request for starting job |

### Return type

[StartJobResponse](StartJobResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunJobWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StartJobResponse> response = apiInstance.RunJobWithHttpInfo(scope, code, startJobRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatejob"></a>
## UpdateJob

> JobDefinition UpdateJob(string scope, string code, UpdateJobRequest updateJobRequest)

UpdateJob: Update a JobDefinition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<JobsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateJobRequest = new UpdateJobRequest(); // UpdateJobRequest
JobDefinition result = apiInstance.UpdateJob(scope, code, updateJobRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** |  |
| **code** | **string** | path | **required** |  |
| **updateJobRequest** | [UpdateJobRequest](UpdateJobRequest.md) | body | **required** |  |

### Return type

[JobDefinition](JobDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateJobWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<JobDefinition> response = apiInstance.UpdateJobWithHttpInfo(scope, code, updateJobRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

