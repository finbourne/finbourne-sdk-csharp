# Finbourne.Sdk.Lusid.Api.ReferenceListsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteReferenceList**](#deletereferencelist) | **DELETE** `/api/api/referencelists/{scope}/{code}` | [EARLY ACCESS] DeleteReferenceList: Delete Reference List |
| [**GetReferenceList**](#getreferencelist) | **GET** `/api/api/referencelists/{scope}/{code}` | GetReferenceList: Get Reference List |
| [**ListReferenceLists**](#listreferencelists) | **GET** `/api/api/referencelists` | [EARLY ACCESS] ListReferenceLists: List Reference Lists |
| [**UpsertReferenceList**](#upsertreferencelist) | **POST** `/api/api/referencelists` | [EARLY ACCESS] UpsertReferenceList: Upsert Reference List |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ReferenceListsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferenceListsApi>();
```

---

<a id="deletereferencelist"></a>
## DeleteReferenceList

> DeletedEntityResponse DeleteReferenceList(string scope, string code)

[EARLY ACCESS] DeleteReferenceList: Delete Reference List

Delete a Reference List instance.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferenceListsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteReferenceList(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the Reference List belongs. |
| **code** | **string** | path | **required** | The Reference List&#39;s unique identifier. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted reference list response. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteReferenceListWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteReferenceListWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreferencelist"></a>
## GetReferenceList

> ReferenceListResponse GetReferenceList(string scope, string code, DateTimeOffset? asAt = null)

GetReferenceList: Get Reference List

Retrieve a Reference List instance at a point in AsAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferenceListsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ReferenceListResponse result = apiInstance.GetReferenceList(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the Reference List belongs. |
| **code** | **string** | path | **required** | The Reference List&#39;s unique identifier. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Reference List. Defaults to return the latest version of the Reference List if not specified. |

### Return type

[ReferenceListResponse](ReferenceListResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Reference List matching the requested identifier. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReferenceListWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReferenceListResponse> response = apiInstance.GetReferenceListWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listreferencelists"></a>
## ListReferenceLists

> PagedResourceListOfReferenceListResponse ListReferenceLists(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EARLY ACCESS] ListReferenceLists: List Reference Lists

List all the Reference Lists matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferenceListsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfReferenceListResponse result = apiInstance.ListReferenceLists(asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list Reference Lists. Defaults to return the latest version of Reference Lists if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Reference Lists from a previous call to list Reference Lists.              This value is returned from the previous call. If a pagination token is provided, the filter, limit and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfReferenceListResponse](PagedResourceListOfReferenceListResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of Reference Lists. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListReferenceListsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfReferenceListResponse> response = apiInstance.ListReferenceListsWithHttpInfo(asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreferencelist"></a>
## UpsertReferenceList

> ReferenceListResponse UpsertReferenceList(ReferenceListRequest? referenceListRequest = null)

[EARLY ACCESS] UpsertReferenceList: Upsert Reference List

Insert the Reference List if it does not exist or update the Reference List with the supplied state if it does exist.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferenceListsApi>();
var referenceListRequest = new ReferenceListRequest?(); // ReferenceListRequest? (optional)
ReferenceListResponse result = apiInstance.UpsertReferenceList(referenceListRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **referenceListRequest** | [ReferenceListRequest?](ReferenceListRequest?.md) | body | optional | The payload describing the Reference List instance. |

### Return type

[ReferenceListResponse](ReferenceListResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted Reference List instance. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReferenceListWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReferenceListResponse> response = apiInstance.UpsertReferenceListWithHttpInfo(referenceListRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

