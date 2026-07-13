# Finbourne.Sdk.Lusid.Api.ScenariosApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteScenario**](#deletescenario) | **DELETE** `/api/api/scenarios/{scope}/{code}` | [EARLY ACCESS] DeleteScenario: Delete a Scenario, assuming that it is present. |
| [**GetScenario**](#getscenario) | **GET** `/api/api/scenarios/{scope}/{code}` | [EARLY ACCESS] GetScenario: Get Scenario |
| [**ListScenarios**](#listscenarios) | **GET** `/api/api/scenarios/{scope}` | [EARLY ACCESS] ListScenarios: List the set of Scenario definitions |
| [**UpsertScenario**](#upsertscenario) | **POST** `/api/api/scenarios` | [EARLY ACCESS] UpsertScenario: Upsert a Scenario. This creates or updates the scenario definition in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ScenariosApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
```

---

<a id="deletescenario"></a>
## DeleteScenario

> AnnulSingleStructuredDataResponse DeleteScenario(string scope, string code)

[EARLY ACCESS] DeleteScenario: Delete a Scenario, assuming that it is present.

Delete the specified Scenario definition from a single scope.                The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteScenario(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Scenario to delete. |
| **code** | **string** | path | **required** | The Scenario to delete. |

### Return type

[AnnulSingleStructuredDataResponse](AnnulSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The AsAt of deletion or failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteScenarioWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getscenario"></a>
## GetScenario

> GetScenarioResponse GetScenario(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetScenario: Get Scenario

Get a Scenario definition from a single scope.                The response will return either the scenario that has been stored, or a failure explaining why the request was unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetScenarioResponse result = apiInstance.GetScenario(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Scenario to retrieve. |
| **code** | **string** | path | **required** | The code of the Scenario to retrieve. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Scenario. Defaults to return the latest version if not specified. |

### Return type

[GetScenarioResponse](GetScenarioResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Scenario or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetScenarioResponse> response = apiInstance.GetScenarioWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listscenarios"></a>
## ListScenarios

> PagedResourceListOfGetScenarioResponse ListScenarios(string scope, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EARLY ACCESS] ListScenarios: List the set of Scenario definitions

List the set of scenario definitions at the specified date/time and scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfGetScenarioResponse result = apiInstance.ListScenarios(scope, asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to list scenarios for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the scenarios. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **limit** | **int?** | query | optional | Maximum number of results to return. Defaults to 100. |
| **page** | **string?** | query | optional | Pagination token from a previous result to fetch the next page. |

### Return type

[PagedResourceListOfGetScenarioResponse](PagedResourceListOfGetScenarioResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested scenarios |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListScenariosWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGetScenarioResponse> response = apiInstance.ListScenariosWithHttpInfo(scope, asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertscenario"></a>
## UpsertScenario

> UpsertSingleStructuredDataResponse UpsertScenario(UpsertScenarioRequest upsertScenarioRequest)

[EARLY ACCESS] UpsertScenario: Upsert a Scenario. This creates or updates the scenario definition in LUSID.

Update or insert one Scenario definition. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted scenario or failure message if unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var upsertScenarioRequest = new UpsertScenarioRequest(); // UpsertScenarioRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertScenario(upsertScenarioRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertScenarioRequest** | [UpsertScenarioRequest](UpsertScenarioRequest.md) | body | **required** | The Scenario to update or insert |

### Return type

[UpsertSingleStructuredDataResponse](UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted item or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertScenarioWithHttpInfo(upsertScenarioRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

