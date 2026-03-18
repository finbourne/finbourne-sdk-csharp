# Finbourne.Sdk.Lusid.Api.ResourceRecordApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteResourceRecord**](#deleteresourcerecord) | **DELETE** `/api/api/resourcerecords/{scope}/{code}/{resourceId}` | [EARLY ACCESS] DeleteResourceRecord: Delete a Resource Record |
| [**GetResourceRecord**](#getresourcerecord) | **GET** `/api/api/resourcerecords/{scope}/{code}/{resourceId}` | [EARLY ACCESS] GetResourceRecord: Get a Resource Record |
| [**ListResourceRecordCodes**](#listresourcerecordcodes) | **GET** `/api/api/resourcerecords/{scope}` | [EARLY ACCESS] ListResourceRecordCodes: List Resource Records Codes for Scope |
| [**ListResourceRecordScopes**](#listresourcerecordscopes) | **GET** `/api/api/resourcerecords` | [EARLY ACCESS] ListResourceRecordScopes: List Resource Record Scopes |
| [**ListResourceRecords**](#listresourcerecords) | **GET** `/api/api/resourcerecords/{scope}/{code}` | [EARLY ACCESS] ListResourceRecords: List Resource Records |
| [**UpsertResourceRecord**](#upsertresourcerecord) | **POST** `/api/api/resourcerecords` | [EARLY ACCESS] UpsertResourceRecord: Upsert a Resource Record |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ResourceRecordApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
```

---

<a id="deleteresourcerecord"></a>
## DeleteResourceRecord

> DeletedEntityResponse DeleteResourceRecord(string scope, string code, string resourceId)

[EARLY ACCESS] DeleteResourceRecord: Delete a Resource Record

Delete a resource record.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var resourceId = "resourceId_example";  // string
DeletedEntityResponse result = apiInstance.DeleteResourceRecord(scope, code, resourceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the resource record. |
| **code** | **string** | path | **required** | The code of the resource record. |
| **resourceId** | **string** | path | **required** | The resource identifier of the resource record. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteResourceRecordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteResourceRecordWithHttpInfo(scope, code, resourceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getresourcerecord"></a>
## GetResourceRecord

> ResourceRecord GetResourceRecord(string scope, string code, string resourceId, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetResourceRecord: Get a Resource Record

Retrieve a resource record by its identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var resourceId = "resourceId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceRecord result = apiInstance.GetResourceRecord(scope, code, resourceId, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the resource record. |
| **code** | **string** | path | **required** | The code of the resource record. |
| **resourceId** | **string** | path | **required** | The resource identifier of the resource record. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the resource record. Defaults to return the latest version if not specified. |

### Return type

[ResourceRecord](ResourceRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested resource record. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetResourceRecordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceRecord> response = apiInstance.GetResourceRecordWithHttpInfo(scope, code, resourceId, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listresourcerecordcodes"></a>
## ListResourceRecordCodes

> ResourceListOfString ListResourceRecordCodes(string scope, DateTimeOffset? asAt = null, string? sortOrder = null)

[EARLY ACCESS] ListResourceRecordCodes: List Resource Records Codes for Scope

List all resource records matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var sortOrder = "sortOrder_example";  // string? (optional)
ResourceListOfString result = apiInstance.ListResourceRecordCodes(scope, asAt, sortOrder);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the resource record. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the resource record. Defaults to return the latest version if not specified. |
| **sortOrder** | **string?** | query | optional | Order of the sort - either \&quot;ASC\&quot; or \&quot;DESC\&quot; |

### Return type

[ResourceListOfString](ResourceListOfString.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of resource record codes. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListResourceRecordCodesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfString> response = apiInstance.ListResourceRecordCodesWithHttpInfo(scope, asAt, sortOrder);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listresourcerecordscopes"></a>
## ListResourceRecordScopes

> ResourceListOfScopeDefinition ListResourceRecordScopes(DateTimeOffset? asAt = null, string? page = null, int? limit = null)

[EARLY ACCESS] ListResourceRecordScopes: List Resource Record Scopes

List all resource records matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfScopeDefinition result = apiInstance.ListResourceRecordScopes(asAt, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the resource record. Defaults to return the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing resource records from a previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |

### Return type

[ResourceListOfScopeDefinition](ResourceListOfScopeDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of resource records. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListResourceRecordScopesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScopeDefinition> response = apiInstance.ListResourceRecordScopesWithHttpInfo(asAt, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listresourcerecords"></a>
## ListResourceRecords

> PagedResourceListOfResourceRecord ListResourceRecords(string scope, string code, DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EARLY ACCESS] ListResourceRecords: List Resource Records

List all resource records matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfResourceRecord result = apiInstance.ListResourceRecords(scope, code, asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the resource record. |
| **code** | **string** | path | **required** | The code of the resource record. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the resource record. Defaults to return the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing resource records from a previous call. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |

### Return type

[PagedResourceListOfResourceRecord](PagedResourceListOfResourceRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of resource records. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListResourceRecordsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfResourceRecord> response = apiInstance.ListResourceRecordsWithHttpInfo(scope, code, asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertresourcerecord"></a>
## UpsertResourceRecord

> ResourceRecord UpsertResourceRecord(UpsertResourceRecordRequest upsertResourceRecordRequest)

[EARLY ACCESS] UpsertResourceRecord: Upsert a Resource Record

Create or update a resource record.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ResourceRecordApi>();
var upsertResourceRecordRequest = new UpsertResourceRecordRequest(); // UpsertResourceRecordRequest
ResourceRecord result = apiInstance.UpsertResourceRecord(upsertResourceRecordRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertResourceRecordRequest** | [UpsertResourceRecordRequest](UpsertResourceRecordRequest.md) | body | **required** | The resource record to upsert. |

### Return type

[ResourceRecord](ResourceRecord.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The upserted resource record. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertResourceRecordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceRecord> response = apiInstance.UpsertResourceRecordWithHttpInfo(upsertResourceRecordRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

