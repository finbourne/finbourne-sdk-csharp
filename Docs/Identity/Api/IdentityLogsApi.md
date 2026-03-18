# Finbourne.Sdk.Identity.Api.IdentityLogsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListLogs**](#listlogs) | **GET** `/identity/api/logs` | [BETA] ListLogs: Lists system logs for a domain |
| [**ListUserLogs**](#listuserlogs) | **GET** `/identity/api/logs/me` | ListUserLogs: Lists user logs |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Identity.Api;
using Finbourne.Sdk.Identity.Client;
using Finbourne.Sdk.Identity.Extensions;
using Finbourne.Sdk.Services.Identity.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<IdentityLogsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentityLogsApi>();
```

---

<a id="listlogs"></a>
## ListLogs

> ResourceListOfSystemLog ListLogs(DateTimeOffset? oktaSince = null, DateTimeOffset? oktaUntil = null, string? oktaFilter = null, string? oktaQuery = null, int? oktaLimit = null, string? oktaSortOrder = null, string? oktaAfter = null)

[BETA] ListLogs: Lists system logs for a domain

Lists system logs for a domain

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentityLogsApi>();
var oktaSince = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var oktaUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var oktaFilter = "oktaFilter_example";  // string? (optional)
var oktaQuery = "oktaQuery_example";  // string? (optional)
var oktaLimit = 56;  // int? (optional)
var oktaSortOrder = "oktaSortOrder_example";  // string? (optional)
var oktaAfter = "oktaAfter_example";  // string? (optional)
ResourceListOfSystemLog result = apiInstance.ListLogs(oktaSince, oktaUntil, oktaFilter, oktaQuery, oktaLimit, oktaSortOrder, oktaAfter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **oktaSince** | **DateTimeOffset?** | query | optional | Lower bound of log events published property |
| **oktaUntil** | **DateTimeOffset?** | query | optional | Upper bound of log events published property |
| **oktaFilter** | **string?** | query | optional | Okta filter expression |
| **oktaQuery** | **string?** | query | optional | Filters log events results by one or more case insensitive keywords |
| **oktaLimit** | **int?** | query | optional | Max number of results returned |
| **oktaSortOrder** | **string?** | query | optional | Order of events by published property. Either ASCENDING or DESCENDING |
| **oktaAfter** | **string?** | query | optional | Okta Page token |

### Return type

[ResourceListOfSystemLog](ResourceListOfSystemLog.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Logs |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfSystemLog> response = apiInstance.ListLogsWithHttpInfo(oktaSince, oktaUntil, oktaFilter, oktaQuery, oktaLimit, oktaSortOrder, oktaAfter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listuserlogs"></a>
## ListUserLogs

> ResourceListOfSystemLog ListUserLogs(DateTimeOffset? oktaSince = null, DateTimeOffset? oktaUntil = null, int? oktaLimit = null, string? oktaSortOrder = null, string? oktaAfter = null)

ListUserLogs: Lists user logs

Lists account related system logs for the calling user

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentityLogsApi>();
var oktaSince = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var oktaUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var oktaLimit = 56;  // int? (optional)
var oktaSortOrder = "oktaSortOrder_example";  // string? (optional)
var oktaAfter = "oktaAfter_example";  // string? (optional)
ResourceListOfSystemLog result = apiInstance.ListUserLogs(oktaSince, oktaUntil, oktaLimit, oktaSortOrder, oktaAfter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **oktaSince** | **DateTimeOffset?** | query | optional | Lower bound of log events published property |
| **oktaUntil** | **DateTimeOffset?** | query | optional | Upper bound of log events published property |
| **oktaLimit** | **int?** | query | optional | Max number of results returned |
| **oktaSortOrder** | **string?** | query | optional | Order of events by published property. Either ASCENDING or DESCENDING |
| **oktaAfter** | **string?** | query | optional | Okta Page token |

### Return type

[ResourceListOfSystemLog](ResourceListOfSystemLog.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List User Logs |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListUserLogsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfSystemLog> response = apiInstance.ListUserLogsWithHttpInfo(oktaSince, oktaUntil, oktaLimit, oktaSortOrder, oktaAfter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

