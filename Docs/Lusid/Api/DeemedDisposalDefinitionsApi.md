# Finbourne.Sdk.Lusid.Api.DeemedDisposalDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDeemedDisposalDefinition**](#createdeemeddisposaldefinition) | **POST** `/api/api/deemeddisposaldefinitions/{scope}` | [EXPERIMENTAL] CreateDeemedDisposalDefinition: Create a Deemed Disposal Definition. |
| [**DeleteDeemedDisposalDefinition**](#deletedeemeddisposaldefinition) | **DELETE** `/api/api/deemeddisposaldefinitions/{scope}/{code}` | [EXPERIMENTAL] DeleteDeemedDisposalDefinition: Delete a Deemed Disposal Definition. |
| [**GetDeemedDisposalDefinition**](#getdeemeddisposaldefinition) | **GET** `/api/api/deemeddisposaldefinitions/{scope}/{code}` | [EXPERIMENTAL] GetDeemedDisposalDefinition: Get a Deemed Disposal Definition. |
| [**ListDeemedDisposalDefinitions**](#listdeemeddisposaldefinitions) | **GET** `/api/api/deemeddisposaldefinitions` | [EXPERIMENTAL] ListDeemedDisposalDefinitions: List Deemed Disposal Definitions. |
| [**UpdateDeemedDisposalDefinition**](#updatedeemeddisposaldefinition) | **PUT** `/api/api/deemeddisposaldefinitions/{scope}/{code}` | [EXPERIMENTAL] UpdateDeemedDisposalDefinition: Update a Deemed Disposal Definition. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<DeemedDisposalDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeemedDisposalDefinitionsApi>();
```

---

<a id="createdeemeddisposaldefinition"></a>
## CreateDeemedDisposalDefinition

> DeemedDisposalDefinition CreateDeemedDisposalDefinition(string scope, DeemedDisposalDefinitionRequest deemedDisposalDefinitionRequest)

[EXPERIMENTAL] CreateDeemedDisposalDefinition: Create a Deemed Disposal Definition.

Create a Deemed Disposal Definition whose filter selects the holdings a valuation point deems disposed of  and re-acquired at market value. The filter must be a valid holdings filter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeemedDisposalDefinitionsApi>();
var scope = "scope_example";  // string
var deemedDisposalDefinitionRequest = new DeemedDisposalDefinitionRequest(); // DeemedDisposalDefinitionRequest
DeemedDisposalDefinition result = apiInstance.CreateDeemedDisposalDefinition(scope, deemedDisposalDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Deemed Disposal Definition. |
| **deemedDisposalDefinitionRequest** | [DeemedDisposalDefinitionRequest](../Model/DeemedDisposalDefinitionRequest.md) | body | **required** | The contents of the Deemed Disposal Definition. |

### Return type

[DeemedDisposalDefinition](../Model/DeemedDisposalDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Deemed Disposal Definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateDeemedDisposalDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeemedDisposalDefinition> response = apiInstance.CreateDeemedDisposalDefinitionWithHttpInfo(scope, deemedDisposalDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletedeemeddisposaldefinition"></a>
## DeleteDeemedDisposalDefinition

> DeletedEntityResponse DeleteDeemedDisposalDefinition(string scope, string code)

[EXPERIMENTAL] DeleteDeemedDisposalDefinition: Delete a Deemed Disposal Definition.

Delete the given Deemed Disposal Definition. A definition that is applied by a valuation point cannot be deleted.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeemedDisposalDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteDeemedDisposalDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Deemed Disposal Definition to be deleted. |
| **code** | **string** | path | **required** | The code of the Deemed Disposal Definition to be deleted. Together with the scope this uniquely identifies the Deemed Disposal Definition. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Deemed Disposal Definition was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteDeemedDisposalDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteDeemedDisposalDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdeemeddisposaldefinition"></a>
## GetDeemedDisposalDefinition

> DeemedDisposalDefinition GetDeemedDisposalDefinition(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetDeemedDisposalDefinition: Get a Deemed Disposal Definition.

Retrieve the definition of a particular Deemed Disposal Definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeemedDisposalDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeemedDisposalDefinition result = apiInstance.GetDeemedDisposalDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Deemed Disposal Definition. |
| **code** | **string** | path | **required** | The code of the Deemed Disposal Definition. Together with the scope this uniquely identifies the Deemed Disposal Definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Deemed Disposal Definition. Defaults to returning the latest version if not specified. |

### Return type

[DeemedDisposalDefinition](../Model/DeemedDisposalDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Deemed Disposal Definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDeemedDisposalDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeemedDisposalDefinition> response = apiInstance.GetDeemedDisposalDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listdeemeddisposaldefinitions"></a>
## ListDeemedDisposalDefinitions

> PagedResourceListOfDeemedDisposalDefinition ListDeemedDisposalDefinitions(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListDeemedDisposalDefinitions: List Deemed Disposal Definitions.

List all the Deemed Disposal Definitions matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeemedDisposalDefinitionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfDeemedDisposalDefinition result = apiInstance.ListDeemedDisposalDefinitions(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Deemed Disposal Definitions. Defaults to returning the latest version of each if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Deemed Disposal Definitions; this              value is returned from the previous call. If a pagination token is provided, the filter and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the code, specify \&quot;id.Code eq &#39;Definition1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfDeemedDisposalDefinition](../Model/PagedResourceListOfDeemedDisposalDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Deemed Disposal Definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListDeemedDisposalDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfDeemedDisposalDefinition> response = apiInstance.ListDeemedDisposalDefinitionsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatedeemeddisposaldefinition"></a>
## UpdateDeemedDisposalDefinition

> DeemedDisposalDefinition UpdateDeemedDisposalDefinition(string scope, string code, UpdateDeemedDisposalDefinitionRequest updateDeemedDisposalDefinitionRequest)

[EXPERIMENTAL] UpdateDeemedDisposalDefinition: Update a Deemed Disposal Definition.

Replace the display name, description and filter of an existing Deemed Disposal Definition, creating a new  version. The filter must be a valid holdings filter.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DeemedDisposalDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateDeemedDisposalDefinitionRequest = new UpdateDeemedDisposalDefinitionRequest(); // UpdateDeemedDisposalDefinitionRequest
DeemedDisposalDefinition result = apiInstance.UpdateDeemedDisposalDefinition(scope, code, updateDeemedDisposalDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Deemed Disposal Definition. |
| **code** | **string** | path | **required** | The code of the Deemed Disposal Definition. Together with the scope this uniquely identifies the Deemed Disposal Definition. |
| **updateDeemedDisposalDefinitionRequest** | [UpdateDeemedDisposalDefinitionRequest](../Model/UpdateDeemedDisposalDefinitionRequest.md) | body | **required** | The new contents of the Deemed Disposal Definition. |

### Return type

[DeemedDisposalDefinition](../Model/DeemedDisposalDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Deemed Disposal Definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateDeemedDisposalDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeemedDisposalDefinition> response = apiInstance.UpdateDeemedDisposalDefinitionWithHttpInfo(scope, code, updateDeemedDisposalDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

