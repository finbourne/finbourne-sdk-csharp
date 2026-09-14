# Finbourne.Sdk.Lusid.Api.CurrencyGroupsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteCurrencyGroup**](#deletecurrencygroup) | **DELETE** `/api/api/currencies/groups/{code}` | [EXPERIMENTAL] DeleteCurrencyGroup: Delete a currency group. |
| [**GetCurrencyGroup**](#getcurrencygroup) | **GET** `/api/api/currencies/groups/{code}` | [EXPERIMENTAL] GetCurrencyGroup: Get a currency group. |
| [**ListCurrencyGroups**](#listcurrencygroups) | **GET** `/api/api/currencies/groups` | [EXPERIMENTAL] ListCurrencyGroups: List currency groups. |
| [**UpsertCurrencyGroup**](#upsertcurrencygroup) | **POST** `/api/api/currencies/groups` | [EXPERIMENTAL] UpsertCurrencyGroup: Upsert a currency group. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CurrencyGroupsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrencyGroupsApi>();
```

---

<a id="deletecurrencygroup"></a>
## DeleteCurrencyGroup

> DeletedEntityResponse DeleteCurrencyGroup(string code)

[EXPERIMENTAL] DeleteCurrencyGroup: Delete a currency group.

Delete the currency group with the given code. The group's currencies are freed to be claimed  by other currency groups.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrencyGroupsApi>();
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteCurrencyGroup(code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the currency group to delete. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCurrencyGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCurrencyGroupWithHttpInfo(code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcurrencygroup"></a>
## GetCurrencyGroup

> CurrencyGroupResponse GetCurrencyGroup(string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetCurrencyGroup: Get a currency group.

Get the currency group with the given code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrencyGroupsApi>();
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CurrencyGroupResponse result = apiInstance.GetCurrencyGroup(code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the currency group. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the currency group. Defaults to returning              the latest version if not specified. |

### Return type

[CurrencyGroupResponse](../Model/CurrencyGroupResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested currency group. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCurrencyGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CurrencyGroupResponse> response = apiInstance.GetCurrencyGroupWithHttpInfo(code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcurrencygroups"></a>
## ListCurrencyGroups

> PagedResourceListOfCurrencyGroupResponse ListCurrencyGroups(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListCurrencyGroups: List currency groups.

List the currency groups defined in the tenant that the caller is entitled to read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrencyGroupsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfCurrencyGroupResponse result = apiInstance.ListCurrencyGroups(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the currency groups. Defaults to returning              the latest version of each currency group if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing currency groups from a previous              call to list currency groups. This value is returned from the previous call. If a pagination token              is provided the filter, sortBy and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. |
| **filter** | **string?** | query | optional | Expression to filter the results. Filterable fields are the group&#39;s code,              displayName and majorUnitCurrency. For example, \&quot;majorUnitCurrency eq &#39;GBP&#39;\&quot;. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each prefixed with \&quot;+\&quot; for ascending or              \&quot;-\&quot; for descending. Sortable fields are the group&#39;s code, displayName and majorUnitCurrency. |

### Return type

[PagedResourceListOfCurrencyGroupResponse](../Model/PagedResourceListOfCurrencyGroupResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested currency groups. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCurrencyGroupsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCurrencyGroupResponse> response = apiInstance.ListCurrencyGroupsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcurrencygroup"></a>
## UpsertCurrencyGroup

> CurrencyGroupResponse UpsertCurrencyGroup(UpsertCurrencyGroupRequest upsertCurrencyGroupRequest)

[EXPERIMENTAL] UpsertCurrencyGroup: Upsert a currency group.

Create or update a currency group. If a currency group with the same code already exists it is replaced.  A currency may belong to at most one currency group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrencyGroupsApi>();
var upsertCurrencyGroupRequest = new UpsertCurrencyGroupRequest(); // UpsertCurrencyGroupRequest
CurrencyGroupResponse result = apiInstance.UpsertCurrencyGroup(upsertCurrencyGroupRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertCurrencyGroupRequest** | [UpsertCurrencyGroupRequest](../Model/UpsertCurrencyGroupRequest.md) | body | **required** | The currency group to upsert. |

### Return type

[CurrencyGroupResponse](../Model/CurrencyGroupResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted currency group. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCurrencyGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CurrencyGroupResponse> response = apiInstance.UpsertCurrencyGroupWithHttpInfo(upsertCurrencyGroupRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

