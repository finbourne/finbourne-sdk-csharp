# Finbourne.Sdk.Workflow.Api.LaunchersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateLauncher**](#createlauncher) | **POST** `/workflow/api/workflows/{scope}/{code}/launchers` | [EXPERIMENTAL] CreateLauncher: Create a new Launcher on a Workflow |
| [**DeleteLauncher**](#deletelauncher) | **DELETE** `/workflow/api/workflows/{scope}/{code}/launchers/{launcherId}` | [EXPERIMENTAL] DeleteLauncher: Delete a Launcher of a Workflow |
| [**GetLauncher**](#getlauncher) | **GET** `/workflow/api/workflows/{scope}/{code}/launchers/{launcherId}` | [EXPERIMENTAL] GetLauncher: Get a Launcher of a Workflow |
| [**ListLaunchers**](#listlaunchers) | **GET** `/workflow/api/workflows/{scope}/{code}/launchers` | [EXPERIMENTAL] ListLaunchers: List the Launchers of a Workflow |
| [**UpdateLauncher**](#updatelauncher) | **PUT** `/workflow/api/workflows/{scope}/{code}/launchers/{launcherId}` | [EXPERIMENTAL] UpdateLauncher: Update an existing Launcher of a Workflow |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Workflow.Api;
using Finbourne.Sdk.Workflow.Client;
using Finbourne.Sdk.Workflow.Extensions;
using Finbourne.Sdk.Services.Workflow.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<LaunchersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LaunchersApi>();
```

---

<a id="createlauncher"></a>
## CreateLauncher

> LauncherResponse CreateLauncher(string scope, string code, CreateLauncherRequest createLauncherRequest)

[EXPERIMENTAL] CreateLauncher: Create a new Launcher on a Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LaunchersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createLauncherRequest = new CreateLauncherRequest(); // CreateLauncherRequest
LauncherResponse result = apiInstance.CreateLauncher(scope, code, createLauncherRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies the Workflow that owns the Launcher |
| **code** | **string** | path | **required** | The code that identifies the Workflow that owns the Launcher |
| **createLauncherRequest** | [CreateLauncherRequest](../Model/CreateLauncherRequest.md) | body | **required** | The data to create a Launcher |

### Return type

[LauncherResponse](../Model/LauncherResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Workflow not found. |  -  |
| **409** | Launcher already exists. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateLauncherWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LauncherResponse> response = apiInstance.CreateLauncherWithHttpInfo(scope, code, createLauncherRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletelauncher"></a>
## DeleteLauncher

> DeletedEntityResponse DeleteLauncher(string scope, string code, string launcherId)

[EXPERIMENTAL] DeleteLauncher: Delete a Launcher of a Workflow

If the Launcher does not exist a failure will be returned

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LaunchersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var launcherId = "launcherId_example";  // string
DeletedEntityResponse result = apiInstance.DeleteLauncher(scope, code, launcherId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies the Workflow that owns the Launcher |
| **code** | **string** | path | **required** | The code that identifies the Workflow that owns the Launcher |
| **launcherId** | **string** | path | **required** | The identifier of the Launcher inside its Workflow |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Launcher not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteLauncherWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteLauncherWithHttpInfo(scope, code, launcherId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlauncher"></a>
## GetLauncher

> LauncherResponse GetLauncher(string scope, string code, string launcherId, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetLauncher: Get a Launcher of a Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LaunchersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var launcherId = "launcherId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
LauncherResponse result = apiInstance.GetLauncher(scope, code, launcherId, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies the Workflow that owns the Launcher |
| **code** | **string** | path | **required** | The code that identifies the Workflow that owns the Launcher |
| **launcherId** | **string** | path | **required** | The identifier of the Launcher inside its Workflow |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Launcher. Defaults to returning the latest             version if not specified. |

### Return type

[LauncherResponse](../Model/LauncherResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Launcher not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLauncherWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LauncherResponse> response = apiInstance.GetLauncherWithHttpInfo(scope, code, launcherId, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listlaunchers"></a>
## ListLaunchers

> PagedResourceListOfLauncherResponse ListLaunchers(string scope, string code, DateTimeOffset? asAt = null, string? filter = null, List<string>? sortBy = null, int? limit = null, string? page = null)

[EXPERIMENTAL] ListLaunchers: List the Launchers of a Workflow

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LaunchersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 10;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfLauncherResponse result = apiInstance.ListLaunchers(scope, code, asAt, filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies the Workflow that owns the Launchers |
| **code** | **string** | path | **required** | The code that identifies the Workflow that owns the Launchers |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Launchers. Defaults to return the latest version             of each Launcher if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:             https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. Defaults to             \&quot;launcherId ASC\&quot; if not specified. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Default: `10` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Launchers from a previous call to list             Launchers. This value is returned from the previous call. If a pagination token is provided the sortBy,             filter, and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfLauncherResponse](../Model/PagedResourceListOfLauncherResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Workflow not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListLaunchersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfLauncherResponse> response = apiInstance.ListLaunchersWithHttpInfo(scope, code, asAt, filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatelauncher"></a>
## UpdateLauncher

> LauncherResponse UpdateLauncher(string scope, string code, string launcherId, UpdateLauncherRequest updateLauncherRequest)

[EXPERIMENTAL] UpdateLauncher: Update an existing Launcher of a Workflow

The type of a Launcher cannot be changed

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LaunchersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var launcherId = "launcherId_example";  // string
var updateLauncherRequest = new UpdateLauncherRequest(); // UpdateLauncherRequest
LauncherResponse result = apiInstance.UpdateLauncher(scope, code, launcherId, updateLauncherRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies the Workflow that owns the Launcher |
| **code** | **string** | path | **required** | The code that identifies the Workflow that owns the Launcher |
| **launcherId** | **string** | path | **required** | The identifier of the Launcher inside its Workflow |
| **updateLauncherRequest** | [UpdateLauncherRequest](../Model/UpdateLauncherRequest.md) | body | **required** | The data to update a Launcher |

### Return type

[LauncherResponse](../Model/LauncherResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Launcher not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateLauncherWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LauncherResponse> response = apiInstance.UpdateLauncherWithHttpInfo(scope, code, launcherId, updateLauncherRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

