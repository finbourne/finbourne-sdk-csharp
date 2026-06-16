# Finbourne.Sdk.Lusid.Api.AddressKeyAliasApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteAddressKeyAlias**](#deleteaddresskeyalias) | **DELETE** `/api/api/addresskeyaliases/{scope}/{code}` | [EXPERIMENTAL] DeleteAddressKeyAlias: Delete an Address Key Alias, assuming that it is present. |
| [**GetAddressKeyAlias**](#getaddresskeyalias) | **GET** `/api/api/addresskeyaliases/{scope}/{code}` | [EXPERIMENTAL] GetAddressKeyAlias: Get Address Key Alias |
| [**ListAddressKeyAliases**](#listaddresskeyaliases) | **GET** `/api/api/addresskeyaliases/{scope}` | [EXPERIMENTAL] ListAddressKeyAliases: List the set of Address Key Aliases |
| [**UpsertAddressKeyAlias**](#upsertaddresskeyalias) | **POST** `/api/api/addresskeyaliases` | [EXPERIMENTAL] UpsertAddressKeyAlias: Upsert an Address Key Alias. This creates or updates the alias in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AddressKeyAliasApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyAliasApi>();
```

---

<a id="deleteaddresskeyalias"></a>
## DeleteAddressKeyAlias

> AnnulSingleStructuredDataResponse DeleteAddressKeyAlias(string scope, string code)

[EXPERIMENTAL] DeleteAddressKeyAlias: Delete an Address Key Alias, assuming that it is present.

Delete the specified Address Key Alias from a single scope.                The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyAliasApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteAddressKeyAlias(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Address Key Alias to delete. |
| **code** | **string** | path | **required** | The Address Key Alias to delete. |

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
<summary>Using the DeleteAddressKeyAliasWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteAddressKeyAliasWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaddresskeyalias"></a>
## GetAddressKeyAlias

> GetAddressKeyAliasResponse GetAddressKeyAlias(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAddressKeyAlias: Get Address Key Alias

Get an Address Key Alias from a single scope.                The response will return either the alias that has been stored, or a failure explaining why the request was unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyAliasApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetAddressKeyAliasResponse result = apiInstance.GetAddressKeyAlias(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Address Key Alias to retrieve. |
| **code** | **string** | path | **required** | The code of the alias to retrieve. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the alias. Defaults to return the latest version if not specified. |

### Return type

[GetAddressKeyAliasResponse](GetAddressKeyAliasResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Address Key Alias or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAddressKeyAliasWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetAddressKeyAliasResponse> response = apiInstance.GetAddressKeyAliasWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listaddresskeyaliases"></a>
## ListAddressKeyAliases

> PagedResourceListOfGetAddressKeyAliasResponse ListAddressKeyAliases(string scope, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EXPERIMENTAL] ListAddressKeyAliases: List the set of Address Key Aliases

List the set of address key aliases at the specified date/time and scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyAliasApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfGetAddressKeyAliasResponse result = apiInstance.ListAddressKeyAliases(scope, asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to list aliases for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the aliases. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **limit** | **int?** | query | optional | Maximum number of results to return. Defaults to 100. |
| **page** | **string?** | query | optional | Pagination token from a previous result to fetch the next page. |

### Return type

[PagedResourceListOfGetAddressKeyAliasResponse](PagedResourceListOfGetAddressKeyAliasResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested address key aliases |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAddressKeyAliasesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGetAddressKeyAliasResponse> response = apiInstance.ListAddressKeyAliasesWithHttpInfo(scope, asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertaddresskeyalias"></a>
## UpsertAddressKeyAlias

> UpsertSingleStructuredDataResponse UpsertAddressKeyAlias(UpsertAddressKeyAliasRequest upsertAddressKeyAliasRequest)

[EXPERIMENTAL] UpsertAddressKeyAlias: Upsert an Address Key Alias. This creates or updates the alias in LUSID.

Update or insert one Address Key Alias. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted alias or failure message if unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyAliasApi>();
var upsertAddressKeyAliasRequest = new UpsertAddressKeyAliasRequest(); // UpsertAddressKeyAliasRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertAddressKeyAlias(upsertAddressKeyAliasRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertAddressKeyAliasRequest** | [UpsertAddressKeyAliasRequest](UpsertAddressKeyAliasRequest.md) | body | **required** | The Address Key Alias to update or insert |

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
<summary>Using the UpsertAddressKeyAliasWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertAddressKeyAliasWithHttpInfo(upsertAddressKeyAliasRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

