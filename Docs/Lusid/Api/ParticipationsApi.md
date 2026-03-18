# Finbourne.Sdk.Lusid.Api.ParticipationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteParticipation**](#deleteparticipation) | **DELETE** `/api/api/participations/{scope}/{code}` | [EARLY ACCESS] DeleteParticipation: Delete participation |
| [**GetParticipation**](#getparticipation) | **GET** `/api/api/participations/{scope}/{code}` | [EARLY ACCESS] GetParticipation: Get Participation |
| [**ListParticipations**](#listparticipations) | **GET** `/api/api/participations` | [EARLY ACCESS] ListParticipations: List Participations |
| [**UpsertParticipations**](#upsertparticipations) | **POST** `/api/api/participations` | [EARLY ACCESS] UpsertParticipations: Upsert Participation |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ParticipationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ParticipationsApi>();
```

---

<a id="deleteparticipation"></a>
## DeleteParticipation

> DeletedEntityResponse DeleteParticipation(string scope, string code)

[EARLY ACCESS] DeleteParticipation: Delete participation

Delete an participation. Deletion will be valid from the participation's creation datetime.  This means that the participation will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ParticipationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteParticipation(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The participation scope. |
| **code** | **string** | path | **required** | The participation&#39;s code. This, together with the scope uniquely identifies the participation to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting an participation. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteParticipationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteParticipationWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getparticipation"></a>
## GetParticipation

> Participation GetParticipation(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] GetParticipation: Get Participation

Fetch a Participation that matches the specified identifier

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ParticipationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Participation result = apiInstance.GetParticipation(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the participation belongs. |
| **code** | **string** | path | **required** | The participation&#39;s unique identifier. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the participation. Defaults to return the latest version of the participation if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Participation\&quot; domain to decorate onto the participation.              These take the format {domain}/{scope}/{code} e.g. \&quot;Participation/system/Name\&quot;. |

### Return type

[Participation](Participation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The participation matching the given identifier. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetParticipationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Participation> response = apiInstance.GetParticipationWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listparticipations"></a>
## ListParticipations

> PagedResourceListOfParticipation ListParticipations(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

[EARLY ACCESS] ListParticipations: List Participations

Fetch the last pre-AsAt date version of each Participation in scope (does not fetch the entire history).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ParticipationsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfParticipation result = apiInstance.ListParticipations(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the participation. Defaults to return the latest version of the participation if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing participations from a previous call to list participations.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Participation\&quot; domain to decorate onto each participation.                  These take the format {domain}/{scope}/{code} e.g. \&quot;Participation/system/Name\&quot;.                  All properties, except derived properties, are returned by default, without specifying here. |

### Return type

[PagedResourceListOfParticipation](PagedResourceListOfParticipation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Participations in scope. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListParticipationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfParticipation> response = apiInstance.ListParticipationsWithHttpInfo(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertparticipations"></a>
## UpsertParticipations

> ResourceListOfParticipation UpsertParticipations(ParticipationSetRequest? participationSetRequest = null)

[EARLY ACCESS] UpsertParticipations: Upsert Participation

Upsert; update existing participations with given ids, or create new participations otherwise.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ParticipationsApi>();
var participationSetRequest = new ParticipationSetRequest?(); // ParticipationSetRequest? (optional)
ResourceListOfParticipation result = apiInstance.UpsertParticipations(participationSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **participationSetRequest** | [ParticipationSetRequest?](ParticipationSetRequest?.md) | body | optional | The collection of participation requests. |

### Return type

[ResourceListOfParticipation](ResourceListOfParticipation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | A collection of participations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertParticipationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfParticipation> response = apiInstance.UpsertParticipationsWithHttpInfo(participationSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

