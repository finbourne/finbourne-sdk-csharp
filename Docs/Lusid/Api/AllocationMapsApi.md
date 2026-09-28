# Finbourne.Sdk.Lusid.Api.AllocationMapsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddAllocationMapException**](#addallocationmapexception) | **POST** `/api/api/allocationmaps/{scope}/{code}/exceptions` | [EXPERIMENTAL] AddAllocationMapException: Add an exception to an Allocation Map. |
| [**CreateAllocationMap**](#createallocationmap) | **POST** `/api/api/allocationmaps/{scope}` | [EXPERIMENTAL] CreateAllocationMap: Create an Allocation Map. |
| [**DeleteAllocationMap**](#deleteallocationmap) | **DELETE** `/api/api/allocationmaps/{scope}/{code}` | [EXPERIMENTAL] DeleteAllocationMap: Delete an Allocation Map. |
| [**GetAllocationMap**](#getallocationmap) | **GET** `/api/api/allocationmaps/{scope}/{code}` | [EXPERIMENTAL] GetAllocationMap: Get an Allocation Map. |
| [**ListAllocationMaps**](#listallocationmaps) | **GET** `/api/api/allocationmaps` | [EXPERIMENTAL] ListAllocationMaps: List Allocation Maps. |
| [**RemoveAllocationMapException**](#removeallocationmapexception) | **DELETE** `/api/api/allocationmaps/{scope}/{code}/exceptions/{investorRecordId}` | [EXPERIMENTAL] RemoveAllocationMapException: Remove an exception from an Allocation Map. |
| [**ResolveAllocationMap**](#resolveallocationmap) | **POST** `/api/api/allocationmaps/{scope}/{code}/resolve` | [EXPERIMENTAL] ResolveAllocationMap: Resolve an Allocation Map. |
| [**UpsertAllocationMap**](#upsertallocationmap) | **PUT** `/api/api/allocationmaps/{scope}/{code}` | [EXPERIMENTAL] UpsertAllocationMap: Upsert an Allocation Map. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AllocationMapsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
```

---

<a id="addallocationmapexception"></a>
## AddAllocationMapException

> AllocationMap AddAllocationMapException(string scope, string code, AllocationMapException allocationMapException, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] AddAllocationMapException: Add an exception to an Allocation Map.

Add a per-investor exception (an exclusion or a fixed percentage) to the map's participants, from an  effective datetime. The result is a new bitemporal version of the map. An investor record may carry at most  one exception; to change it, remove the existing one first or upsert the whole map.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationMapException = new AllocationMapException(); // AllocationMapException
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationMap result = apiInstance.AddAllocationMapException(scope, code, allocationMapException, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **code** | **string** | path | **required** | The code of the Allocation Map. Together with the scope this uniquely identifies the Allocation Map. |
| **allocationMapException** | [AllocationMapException](../Model/AllocationMapException.md) | body | **required** | The exception to add. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the exception applies. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationMap](../Model/AllocationMap.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Allocation Map with the exception added. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddAllocationMapExceptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationMap> response = apiInstance.AddAllocationMapExceptionWithHttpInfo(scope, code, allocationMapException, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createallocationmap"></a>
## CreateAllocationMap

> AllocationMap CreateAllocationMap(string scope, AllocationMapRequest allocationMapRequest)

[EXPERIMENTAL] CreateAllocationMap: Create an Allocation Map.

Create a new Allocation Map. The scope is provided in the route and the code in the request body. The map  names the structure member it hangs off, who participates, and the basis used to share each kind of event.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var allocationMapRequest = new AllocationMapRequest(); // AllocationMapRequest
AllocationMap result = apiInstance.CreateAllocationMap(scope, allocationMapRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **allocationMapRequest** | [AllocationMapRequest](../Model/AllocationMapRequest.md) | body | **required** | The definition of the Allocation Map. |

### Return type

[AllocationMap](../Model/AllocationMap.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Allocation Map. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateAllocationMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationMap> response = apiInstance.CreateAllocationMapWithHttpInfo(scope, allocationMapRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteallocationmap"></a>
## DeleteAllocationMap

> DeletedEntityResponse DeleteAllocationMap(string scope, string code, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteAllocationMap: Delete an Allocation Map.

Delete an Allocation Map from an effective datetime. The Allocation Map is no longer readable from that  effective datetime onwards.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteAllocationMap(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **code** | **string** | path | **required** | The code of the Allocation Map. Together with the scope this uniquely identifies the Allocation Map. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the Allocation Map is deleted. Defaults to the current LUSID system datetime if not specified. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Allocation Map was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteAllocationMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteAllocationMapWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallocationmap"></a>
## GetAllocationMap

> AllocationMap GetAllocationMap(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAllocationMap: Get an Allocation Map.

Retrieve the definition of a particular Allocation Map at an effective and asAt datetime, including its  participants, exceptions and the basis declared for each event type.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AllocationMap result = apiInstance.GetAllocationMap(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **code** | **string** | path | **required** | The code of the Allocation Map. Together with the scope this uniquely identifies the Allocation Map. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Allocation Map. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Allocation Map. Defaults to returning the latest version if not specified. |

### Return type

[AllocationMap](../Model/AllocationMap.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Allocation Map. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllocationMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationMap> response = apiInstance.GetAllocationMapWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listallocationmaps"></a>
## ListAllocationMaps

> PagedResourceListOfAllocationMap ListAllocationMaps(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListAllocationMaps: List Allocation Maps.

List all the Allocation Maps matching a particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfAllocationMap result = apiInstance.ListAllocationMaps(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Allocation Maps. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Allocation Maps. Defaults to returning the latest version of each Allocation Map if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Allocation Maps; this value is returned from the previous call.              If a pagination token is provided, the filter, effectiveAt and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the Allocation Map code, specify \&quot;id.Code eq &#39;AllocationMap1&#39;\&quot;.              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfAllocationMap](../Model/PagedResourceListOfAllocationMap.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Allocation Maps. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAllocationMapsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAllocationMap> response = apiInstance.ListAllocationMapsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removeallocationmapexception"></a>
## RemoveAllocationMapException

> AllocationMap RemoveAllocationMapException(string scope, string code, string investorRecordId, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] RemoveAllocationMapException: Remove an exception from an Allocation Map.

Remove the exception held against an investor record, from an effective datetime. The result is a new  bitemporal version of the map in which that investor is treated like every other participant.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var investorRecordId = "investorRecordId_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationMap result = apiInstance.RemoveAllocationMapException(scope, code, investorRecordId, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **code** | **string** | path | **required** | The code of the Allocation Map. Together with the scope this uniquely identifies the Allocation Map. |
| **investorRecordId** | **string** | path | **required** | The investor record whose exception is removed. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the exception no longer applies. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationMap](../Model/AllocationMap.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Allocation Map with the exception removed. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemoveAllocationMapExceptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationMap> response = apiInstance.RemoveAllocationMapExceptionWithHttpInfo(scope, code, investorRecordId, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="resolveallocationmap"></a>
## ResolveAllocationMap

> AllocationMapResolution ResolveAllocationMap(string scope, string code, AllocationMapResolveRequest allocationMapResolveRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] ResolveAllocationMap: Resolve an Allocation Map.

Dry-run the map against an event: share the supplied amount across the participants in force at the  effective datetime, applying fixed-percentage exceptions off the top and the declared basis to the remainder.  Nothing is booked. Basis values (for example committed capital per investor) are supplied in the request  until the investor register can provide them.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationMapResolveRequest = new AllocationMapResolveRequest(); // AllocationMapResolveRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AllocationMapResolution result = apiInstance.ResolveAllocationMap(scope, code, allocationMapResolveRequest, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **code** | **string** | path | **required** | The code of the Allocation Map. Together with the scope this uniquely identifies the Allocation Map. |
| **allocationMapResolveRequest** | [AllocationMapResolveRequest](../Model/AllocationMapResolveRequest.md) | body | **required** | The event to resolve and the basis values to use. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to resolve the map. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to read the map. Defaults to the latest version if not specified. |

### Return type

[AllocationMapResolution](../Model/AllocationMapResolution.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The resolved allocation. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ResolveAllocationMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationMapResolution> response = apiInstance.ResolveAllocationMapWithHttpInfo(scope, code, allocationMapResolveRequest, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertallocationmap"></a>
## UpsertAllocationMap

> AllocationMap UpsertAllocationMap(string scope, string code, AllocationMapRequest allocationMapRequest)

[EXPERIMENTAL] UpsertAllocationMap: Upsert an Allocation Map.

Update or insert an Allocation Map. If the Allocation Map does not exist it is created, otherwise it is  updated. The code in the request body must match the code in the route.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationMapsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationMapRequest = new AllocationMapRequest(); // AllocationMapRequest
AllocationMap result = apiInstance.UpsertAllocationMap(scope, code, allocationMapRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Map. |
| **code** | **string** | path | **required** | The code of the Allocation Map. Together with the scope this uniquely identifies the Allocation Map. |
| **allocationMapRequest** | [AllocationMapRequest](../Model/AllocationMapRequest.md) | body | **required** | The definition of the Allocation Map. |

### Return type

[AllocationMap](../Model/AllocationMap.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted Allocation Map. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertAllocationMapWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationMap> response = apiInstance.UpsertAllocationMapWithHttpInfo(scope, code, allocationMapRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

