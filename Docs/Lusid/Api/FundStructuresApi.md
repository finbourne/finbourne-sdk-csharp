# Finbourne.Sdk.Lusid.Api.FundStructuresApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateFundStructure**](#createfundstructure) | **POST** `/api/api/fundstructures/{scope}` | [EXPERIMENTAL] CreateFundStructure: Create a Fund Structure. |
| [**GetFundStructure**](#getfundstructure) | **GET** `/api/api/fundstructures/{scope}/{code}` | [EXPERIMENTAL] GetFundStructure: Get a Fund Structure. |
| [**ListFundStructures**](#listfundstructures) | **GET** `/api/api/fundstructures` | [EXPERIMENTAL] ListFundStructures: List Fund Structures. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FundStructuresApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
```

---

<a id="createfundstructure"></a>
## CreateFundStructure

> FundStructure CreateFundStructure(string scope, FundStructureRequest fundStructureRequest)

[EXPERIMENTAL] CreateFundStructure: Create a Fund Structure.

Create a new Fund Structure Model. The scope and code of the Fund Structure are provided in the request body.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var fundStructureRequest = new FundStructureRequest(); // FundStructureRequest
FundStructure result = apiInstance.CreateFundStructure(scope, fundStructureRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure. |
| **fundStructureRequest** | [FundStructureRequest](FundStructureRequest.md) | body | **required** | The definition of the Fund Structure. |

### Return type

[FundStructure](FundStructure.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Fund Structure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFundStructureWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundStructure> response = apiInstance.CreateFundStructureWithHttpInfo(scope, fundStructureRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfundstructure"></a>
## GetFundStructure

> FundStructure GetFundStructure(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetFundStructure: Get a Fund Structure.

Retrieve the definition of a particular Fund Structure, including its nodes, edges, and any inline fund definitions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
FundStructure result = apiInstance.GetFundStructure(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure. |
| **code** | **string** | path | **required** | The code of the Fund Structure. Together with the scope this uniquely identifies the Fund Structure. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Fund Structure. Defaults to returning the latest version if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;FundStructure&#39; domain to decorate onto the Fund Structure.              These must take the format {domain}/{scope}/{code}, for example &#39;FundStructure/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[FundStructure](FundStructure.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fund Structure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFundStructureWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundStructure> response = apiInstance.GetFundStructureWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfundstructures"></a>
## ListFundStructures

> PagedResourceListOfFundStructure ListFundStructures(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFundStructures: List Fund Structures.

List all the Fund Structures matching the given criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFundStructure result = apiInstance.ListFundStructures(asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list Fund Structures. Defaults to returning the latest version of each Fund Structure if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Fund Structures; this value is returned from the previous call. If a pagination token is provided, the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the Fund Structure code, specify \&quot;id.Code eq &#39;Structure1&#39;\&quot;. For more information about filtering results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;FundStructure&#39; domain to decorate onto each Fund Structure.              These must take the format {domain}/{scope}/{code}, for example &#39;FundStructure/Manager/Id&#39;. |

### Return type

[PagedResourceListOfFundStructure](PagedResourceListOfFundStructure.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fund Structures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFundStructuresWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFundStructure> response = apiInstance.ListFundStructuresWithHttpInfo(asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

