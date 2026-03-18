# Finbourne.Sdk.Horizon.Api.ProcessHistoryApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCompleteEvent**](#createcompleteevent) | **POST** `/horizon/api/process-history/event/complete` | [EARLY ACCESS] CreateCompleteEvent: Write a completed event to the Horizon Dashboard |
| [**CreateUpdateEvent**](#createupdateevent) | **POST** `/horizon/api/process-history/event/update` | [EARLY ACCESS] CreateUpdateEvent: Write an update event to the Horizon Dashboard |
| [**GetLatestRuns**](#getlatestruns) | **GET** `/horizon/api/process-history/$latestRuns` | [EARLY ACCESS] GetLatestRuns: Get latest run for each process |
| [**ProcessEntryUpdates**](#processentryupdates) | **POST** `/horizon/api/process-history/entries/$query` | [EARLY ACCESS] ProcessEntryUpdates: Get process entry updates for a query |
| [**ProcessHistoryEntries**](#processhistoryentries) | **POST** `/horizon/api/process-history/$query` | [EARLY ACCESS] ProcessHistoryEntries: Get process history entries |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ProcessHistoryApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessHistoryApi>();
```

---

<a id="createcompleteevent"></a>
## CreateCompleteEvent

> AuditCompleteResponse CreateCompleteEvent(AuditCompleteRequest auditCompleteRequest)

[EARLY ACCESS] CreateCompleteEvent: Write a completed event to the Horizon Dashboard

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessHistoryApi>();
var auditCompleteRequest = new AuditCompleteRequest(); // AuditCompleteRequest
AuditCompleteResponse result = apiInstance.CreateCompleteEvent(auditCompleteRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **auditCompleteRequest** | [AuditCompleteRequest](AuditCompleteRequest.md) | body | **required** |  |

### Return type

[AuditCompleteResponse](AuditCompleteResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCompleteEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AuditCompleteResponse> response = apiInstance.CreateCompleteEventWithHttpInfo(auditCompleteRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createupdateevent"></a>
## CreateUpdateEvent

> AuditUpdateResponse CreateUpdateEvent(AuditUpdateRequest auditUpdateRequest)

[EARLY ACCESS] CreateUpdateEvent: Write an update event to the Horizon Dashboard

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessHistoryApi>();
var auditUpdateRequest = new AuditUpdateRequest(); // AuditUpdateRequest
AuditUpdateResponse result = apiInstance.CreateUpdateEvent(auditUpdateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **auditUpdateRequest** | [AuditUpdateRequest](AuditUpdateRequest.md) | body | **required** |  |

### Return type

[AuditUpdateResponse](AuditUpdateResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateUpdateEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AuditUpdateResponse> response = apiInstance.CreateUpdateEventWithHttpInfo(auditUpdateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlatestruns"></a>
## GetLatestRuns

> List&lt;ProcessInformation&gt; GetLatestRuns()

[EARLY ACCESS] GetLatestRuns: Get latest run for each process

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessHistoryApi>();
List<ProcessInformation> result = apiInstance.GetLatestRuns();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;ProcessInformation&gt;](ProcessInformation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLatestRunsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<ProcessInformation>> response = apiInstance.GetLatestRunsWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="processentryupdates"></a>
## ProcessEntryUpdates

> PagedResourceListOfProcessUpdateResult ProcessEntryUpdates(string runId, QueryRequest queryRequest)

[EARLY ACCESS] ProcessEntryUpdates: Get process entry updates for a query

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessHistoryApi>();
var runId = "runId_example";  // string
var queryRequest = new QueryRequest(); // QueryRequest
PagedResourceListOfProcessUpdateResult result = apiInstance.ProcessEntryUpdates(runId, queryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | query | **required** |  |
| **queryRequest** | [QueryRequest](QueryRequest.md) | body | **required** |  |

### Return type

[PagedResourceListOfProcessUpdateResult](PagedResourceListOfProcessUpdateResult.md)

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
<summary>Using the ProcessEntryUpdatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfProcessUpdateResult> response = apiInstance.ProcessEntryUpdatesWithHttpInfo(runId, queryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="processhistoryentries"></a>
## ProcessHistoryEntries

> PagedResourceListOfProcessInformation ProcessHistoryEntries(QueryRequest queryRequest, string? processName = null)

[EARLY ACCESS] ProcessHistoryEntries: Get process history entries

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ProcessHistoryApi>();
var queryRequest = new QueryRequest(); // QueryRequest
var processName = "processName_example";  // string? (optional)
PagedResourceListOfProcessInformation result = apiInstance.ProcessHistoryEntries(queryRequest, processName);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **queryRequest** | [QueryRequest](QueryRequest.md) | body | **required** |  |
| **processName** | **string?** | query | optional |  |

### Return type

[PagedResourceListOfProcessInformation](PagedResourceListOfProcessInformation.md)

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
<summary>Using the ProcessHistoryEntriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfProcessInformation> response = apiInstance.ProcessHistoryEntriesWithHttpInfo(queryRequest, processName);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

