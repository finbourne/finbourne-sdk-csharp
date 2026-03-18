# Finbourne.Sdk.Insights.Api.AuditingApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateEntry**](#createentry) | **POST** `/insights/api/auditing/entries` | [EARLY ACCESS] CreateEntry: Create (persist) and audit entry.. |
| [**GetProcesses**](#getprocesses) | **GET** `/insights/api/auditing/processes` | [EARLY ACCESS] GetProcesses: Get the latest audit entry for each process. |
| [**ListEntries**](#listentries) | **GET** `/insights/api/auditing/entries` | [EARLY ACCESS] ListEntries: Get the audit entries. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Insights.Api;
using Finbourne.Sdk.Insights.Client;
using Finbourne.Sdk.Insights.Extensions;
using Finbourne.Sdk.Services.Insights.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AuditingApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuditingApi>();
```

---

<a id="createentry"></a>
## CreateEntry

> AuditEntry CreateEntry(CreateAuditEntry? createAuditEntry = null)

[EARLY ACCESS] CreateEntry: Create (persist) and audit entry..

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuditingApi>();
var createAuditEntry = new CreateAuditEntry?(); // CreateAuditEntry? (optional)
AuditEntry result = apiInstance.CreateEntry(createAuditEntry);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createAuditEntry** | [CreateAuditEntry?](CreateAuditEntry?.md) | body | optional | Information about the entry to be created. |

### Return type

[AuditEntry](AuditEntry.md)

### HTTP request headers

 - **Content-Type**: `application/json`, `application/json-patch+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **429** | There have been too many recent requests, retry later (using the RETRY-AFTER header value as the delay). |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateEntryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AuditEntry> response = apiInstance.CreateEntryWithHttpInfo(createAuditEntry);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprocesses"></a>
## GetProcesses

> ResourceListOfAuditProcessSummary GetProcesses()

[EARLY ACCESS] GetProcesses: Get the latest audit entry for each process.

This will never be `null`, though it may be empty.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuditingApi>();
ResourceListOfAuditProcessSummary result = apiInstance.GetProcesses();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfAuditProcessSummary](ResourceListOfAuditProcessSummary.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetProcessesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAuditProcessSummary> response = apiInstance.GetProcessesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listentries"></a>
## ListEntries

> ScrollableCollectionOfAuditEntry ListEntries(string? filter = null, string? sortBy = null, int? size = null, string? state = null)

[EARLY ACCESS] ListEntries: Get the audit entries.

This will never be `null`, though it may be empty.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuditingApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var size = 1000;  // int? (optional)
var state = "state_example";  // string? (optional)
ScrollableCollectionOfAuditEntry result = apiInstance.ListEntries(filter, sortBy, size, state);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | The filter to be applied to the results. |
| **sortBy** | **string?** | query | optional | The order to return the entries in. |
| **size** | **int?** | query | optional | The maximum number of entries to return. Default: `1000` |
| **state** | **string?** | query | optional | The scrolling state, used to iterate through the data set. |

### Return type

[ScrollableCollectionOfAuditEntry](ScrollableCollectionOfAuditEntry.md)

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
<summary>Using the ListEntriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ScrollableCollectionOfAuditEntry> response = apiInstance.ListEntriesWithHttpInfo(filter, sortBy, size, state);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

