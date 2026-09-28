# Finbourne.Sdk.Lusid.Api.FundStructuresApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddFundStructureMember**](#addfundstructuremember) | **POST** `/api/api/fundstructures/{scope}/{code}/members` | [EXPERIMENTAL] AddFundStructureMember: Add a member to a Fund Structure. |
| [**CreateFundStructure**](#createfundstructure) | **POST** `/api/api/fundstructures/{scope}` | [EXPERIMENTAL] CreateFundStructure: Create a Fund Structure. |
| [**DeleteFundStructure**](#deletefundstructure) | **DELETE** `/api/api/fundstructures/{scope}/{code}` | [EXPERIMENTAL] DeleteFundStructure: Delete a Fund Structure. |
| [**GetFundStructure**](#getfundstructure) | **GET** `/api/api/fundstructures/{scope}/{code}` | [EXPERIMENTAL] GetFundStructure: Get a Fund Structure. |
| [**ListFundStructures**](#listfundstructures) | **GET** `/api/api/fundstructures` | [EXPERIMENTAL] ListFundStructures: List Fund Structures. |
| [**RemoveFundStructureMember**](#removefundstructuremember) | **DELETE** `/api/api/fundstructures/{scope}/{code}/members/{nodeCode}` | [EXPERIMENTAL] RemoveFundStructureMember: Remove a member from a Fund Structure. |
| [**UpsertFundStructure**](#upsertfundstructure) | **PUT** `/api/api/fundstructures/{scope}/{code}` | [EXPERIMENTAL] UpsertFundStructure: Upsert a Fund Structure. |

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

<a id="addfundstructuremember"></a>
## AddFundStructureMember

> FundStructure AddFundStructureMember(string scope, string code, FundStructureMemberRequest fundStructureMemberRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] AddFundStructureMember: Add a member to a Fund Structure.

Add a node and the links that join it to existing members, from an effective datetime. The result is a new  bitemporal version of the structure. The change applies to the version in force at that datetime; if a  later version of the structure already exists the request is rejected, since the member would otherwise  drop out when that version begins. Upsert the full definition for each affected version in that case.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fundStructureMemberRequest = new FundStructureMemberRequest(); // FundStructureMemberRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
FundStructure result = apiInstance.AddFundStructureMember(scope, code, fundStructureMemberRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure. |
| **code** | **string** | path | **required** | The code of the Fund Structure. Together with the scope this uniquely identifies the Fund Structure. |
| **fundStructureMemberRequest** | [FundStructureMemberRequest](../Model/FundStructureMemberRequest.md) | body | **required** | The node to add and the links joining it to existing members. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the member is part of the structure. Defaults to the current LUSID system datetime if not specified. |

### Return type

[FundStructure](../Model/FundStructure.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Fund Structure with the member added. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddFundStructureMemberWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundStructure> response = apiInstance.AddFundStructureMemberWithHttpInfo(scope, code, fundStructureMemberRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

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
| **fundStructureRequest** | [FundStructureRequest](../Model/FundStructureRequest.md) | body | **required** | The definition of the Fund Structure. |

### Return type

[FundStructure](../Model/FundStructure.md)

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

<a id="deletefundstructure"></a>
## DeleteFundStructure

> DeletedEntityResponse DeleteFundStructure(string scope, string code, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteFundStructure: Delete a Fund Structure.

Delete a Fund Structure from the given effective datetime. It remains retrievable at earlier effective datetimes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteFundStructure(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure to be deleted. |
| **code** | **string** | path | **required** | The code of the Fund Structure to be deleted. Together with the scope this uniquely identifies the Fund Structure. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the Fund Structure is deleted. Defaults to the current LUSID system datetime if not specified. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Fund Structure was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFundStructureWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteFundStructureWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfundstructure"></a>
## GetFundStructure

> FundStructure GetFundStructure(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetFundStructure: Get a Fund Structure.

Retrieve the definition of a particular Fund Structure at an effective and asAt datetime, including its nodes,  edges, allocation groups and the funds its nodes refer to.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
FundStructure result = apiInstance.GetFundStructure(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure. |
| **code** | **string** | path | **required** | The code of the Fund Structure. Together with the scope this uniquely identifies the Fund Structure. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Fund Structure. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Fund Structure. Defaults to returning the latest version if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the &#39;FundStructure&#39; domain to decorate onto the Fund Structure.              These must take the format {domain}/{scope}/{code}, for example &#39;FundStructure/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[FundStructure](../Model/FundStructure.md)

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
ApiResponse<FundStructure> response = apiInstance.GetFundStructureWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfundstructures"></a>
## ListFundStructures

> PagedResourceListOfFundStructure ListFundStructures(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFundStructures: List Fund Structures.

List all the Fund Structures matching the given criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFundStructure result = apiInstance.ListFundStructures(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Fund Structures. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list Fund Structures. Defaults to returning the latest version of each Fund Structure if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Fund Structures; this value is returned from the previous call. If a pagination token is provided, the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the Fund Structure code, specify \&quot;id.Code eq &#39;Structure1&#39;\&quot;. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the &#39;FundStructure&#39; domain to decorate onto each Fund Structure.              These must take the format {domain}/{scope}/{code}, for example &#39;FundStructure/Manager/Id&#39;. |

### Return type

[PagedResourceListOfFundStructure](../Model/PagedResourceListOfFundStructure.md)

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
ApiResponse<PagedResourceListOfFundStructure> response = apiInstance.ListFundStructuresWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removefundstructuremember"></a>
## RemoveFundStructureMember

> FundStructure RemoveFundStructureMember(string scope, string code, string nodeCode, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] RemoveFundStructureMember: Remove a member from a Fund Structure.

Remove a node and every link that touches it, from an effective datetime. The result is a new bitemporal  version of the structure. The change applies to the version in force at that datetime; if a later version  of the structure already exists the request is rejected, since the member would otherwise reappear when  that version begins. Upsert the full definition for each affected version in that case.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var nodeCode = "nodeCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
FundStructure result = apiInstance.RemoveFundStructureMember(scope, code, nodeCode, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure. |
| **code** | **string** | path | **required** | The code of the Fund Structure. Together with the scope this uniquely identifies the Fund Structure. |
| **nodeCode** | **string** | path | **required** | The node code of the member to remove. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the member is no longer part of the structure. Defaults to the current LUSID system datetime if not specified. |

### Return type

[FundStructure](../Model/FundStructure.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Fund Structure with the member removed. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemoveFundStructureMemberWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundStructure> response = apiInstance.RemoveFundStructureMemberWithHttpInfo(scope, code, nodeCode, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertfundstructure"></a>
## UpsertFundStructure

> FundStructure UpsertFundStructure(string scope, string code, FundStructureRequest fundStructureRequest)

[EXPERIMENTAL] UpsertFundStructure: Upsert a Fund Structure.

Create or replace the full definition of a Fund Structure from an effective datetime. A change to the  definition becomes a new bitemporal version: the structure as it was declared at earlier effective datetimes,  and as of earlier asAt datetimes, remains retrievable.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundStructuresApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fundStructureRequest = new FundStructureRequest(); // FundStructureRequest
FundStructure result = apiInstance.UpsertFundStructure(scope, code, fundStructureRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund Structure. |
| **code** | **string** | path | **required** | The code of the Fund Structure. Together with the scope this uniquely identifies the Fund Structure, and must match the code in the request body. |
| **fundStructureRequest** | [FundStructureRequest](../Model/FundStructureRequest.md) | body | **required** | The full definition of the Fund Structure from the effective datetime in the request, or the current LUSID system datetime if not specified. |

### Return type

[FundStructure](../Model/FundStructure.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Fund Structure as it stands from the effective datetime. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertFundStructureWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundStructure> response = apiInstance.UpsertFundStructureWithHttpInfo(scope, code, fundStructureRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

