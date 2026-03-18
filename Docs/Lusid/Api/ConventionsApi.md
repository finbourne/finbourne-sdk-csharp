# Finbourne.Sdk.Lusid.Api.ConventionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteCdsFlowConventions**](#deletecdsflowconventions) | **DELETE** `/api/api/conventions/credit/conventions/{scope}/{code}` | [BETA] DeleteCdsFlowConventions: Delete the CDS Flow Conventions of given scope and code, assuming that it is present. |
| [**DeleteFlowConventions**](#deleteflowconventions) | **DELETE** `/api/api/conventions/rates/flowconventions/{scope}/{code}` | [BETA] DeleteFlowConventions: Delete the Flow Conventions of given scope and code, assuming that it is present. |
| [**DeleteIndexConvention**](#deleteindexconvention) | **DELETE** `/api/api/conventions/rates/indexconventions/{scope}/{code}` | [BETA] DeleteIndexConvention: Delete the Index Convention of given scope and code, assuming that it is present. |
| [**GetCdsFlowConventions**](#getcdsflowconventions) | **GET** `/api/api/conventions/credit/conventions/{scope}/{code}` | [BETA] GetCdsFlowConventions: Get CDS Flow Conventions |
| [**GetFlowConventions**](#getflowconventions) | **GET** `/api/api/conventions/rates/flowconventions/{scope}/{code}` | [BETA] GetFlowConventions: Get Flow Conventions |
| [**GetIndexConvention**](#getindexconvention) | **GET** `/api/api/conventions/rates/indexconventions/{scope}/{code}` | [BETA] GetIndexConvention: Get Index Convention |
| [**ListCdsFlowConventions**](#listcdsflowconventions) | **GET** `/api/api/conventions/credit/conventions` | [BETA] ListCdsFlowConventions: List the set of CDS Flow Conventions |
| [**ListFlowConventions**](#listflowconventions) | **GET** `/api/api/conventions/rates/flowconventions` | [BETA] ListFlowConventions: List the set of Flow Conventions |
| [**ListIndexConvention**](#listindexconvention) | **GET** `/api/api/conventions/rates/indexconventions` | [BETA] ListIndexConvention: List the set of Index Conventions |
| [**UpsertCdsFlowConventions**](#upsertcdsflowconventions) | **POST** `/api/api/conventions/credit/conventions` | [BETA] UpsertCdsFlowConventions: Upsert a set of CDS Flow Conventions. This creates or updates the data in Lusid. |
| [**UpsertFlowConventions**](#upsertflowconventions) | **POST** `/api/api/conventions/rates/flowconventions` | [BETA] UpsertFlowConventions: Upsert Flow Conventions. This creates or updates the data in Lusid. |
| [**UpsertIndexConvention**](#upsertindexconvention) | **POST** `/api/api/conventions/rates/indexconventions` | [BETA] UpsertIndexConvention: Upsert a set of Index Convention. This creates or updates the data in Lusid. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ConventionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
```

---

<a id="deletecdsflowconventions"></a>
## DeleteCdsFlowConventions

> AnnulSingleStructuredDataResponse DeleteCdsFlowConventions(string scope, string code)

[BETA] DeleteCdsFlowConventions: Delete the CDS Flow Conventions of given scope and code, assuming that it is present.

Delete the specified CDS Flow Conventions from a single scope.  The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.  It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteCdsFlowConventions(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the CDS Flow Conventions to delete. |
| **code** | **string** | path | **required** | The CDS Flow Conventions to delete. |

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
<summary>Using the DeleteCdsFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteCdsFlowConventionsWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteflowconventions"></a>
## DeleteFlowConventions

> AnnulSingleStructuredDataResponse DeleteFlowConventions(string scope, string code)

[BETA] DeleteFlowConventions: Delete the Flow Conventions of given scope and code, assuming that it is present.

Delete the specified conventions from a single scope.  The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.  It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteFlowConventions(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Flow Conventions to delete. |
| **code** | **string** | path | **required** | The Flow Conventions to delete. |

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
<summary>Using the DeleteFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteFlowConventionsWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteindexconvention"></a>
## DeleteIndexConvention

> AnnulSingleStructuredDataResponse DeleteIndexConvention(string scope, string code)

[BETA] DeleteIndexConvention: Delete the Index Convention of given scope and code, assuming that it is present.

Delete the specified Index Convention from a single scope.  The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.  It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteIndexConvention(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Index Convention to delete. |
| **code** | **string** | path | **required** | The Index Convention to delete. |

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
<summary>Using the DeleteIndexConventionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteIndexConventionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcdsflowconventions"></a>
## GetCdsFlowConventions

> GetCdsFlowConventionsResponse GetCdsFlowConventions(string scope, string code, DateTimeOffset? asAt = null)

[BETA] GetCdsFlowConventions: Get CDS Flow Conventions

Get a CDS Flow Conventions from a single scope.  The response will return either the conventions that has been stored, or a failure explaining why the request was unsuccessful.  It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetCdsFlowConventionsResponse result = apiInstance.GetCdsFlowConventions(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the CDS Flow Conventions to retrieve. |
| **code** | **string** | path | **required** | The name of the CDS Flow Conventions to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the CDS Flow Conventions. Defaults to return the latest version if not specified. |

### Return type

[GetCdsFlowConventionsResponse](GetCdsFlowConventionsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved CDS Flow Conventions or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCdsFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetCdsFlowConventionsResponse> response = apiInstance.GetCdsFlowConventionsWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getflowconventions"></a>
## GetFlowConventions

> GetFlowConventionsResponse GetFlowConventions(string scope, string code, DateTimeOffset? asAt = null)

[BETA] GetFlowConventions: Get Flow Conventions

Get a Flow Conventions from a single scope.  The response will return either the conventions that has been stored, or a failure explaining why the request was unsuccessful.  It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetFlowConventionsResponse result = apiInstance.GetFlowConventions(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Flow Conventions to retrieve. |
| **code** | **string** | path | **required** | The name of the Flow Conventions to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Flow Conventions. Defaults to return the latest version if not specified. |

### Return type

[GetFlowConventionsResponse](GetFlowConventionsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Flow Conventions or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetFlowConventionsResponse> response = apiInstance.GetFlowConventionsWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getindexconvention"></a>
## GetIndexConvention

> GetIndexConventionResponse GetIndexConvention(string scope, string code, DateTimeOffset? asAt = null)

[BETA] GetIndexConvention: Get Index Convention

Get a Index Convention from a single scope.  The response will return either the conventions that has been stored, or a failure explaining why the request was unsuccessful.  It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetIndexConventionResponse result = apiInstance.GetIndexConvention(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Index Convention to retrieve. |
| **code** | **string** | path | **required** | The name of the Index Convention to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Index Convention. Defaults to return the latest version if not specified. |

### Return type

[GetIndexConventionResponse](GetIndexConventionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Index Convention or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetIndexConventionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetIndexConventionResponse> response = apiInstance.GetIndexConventionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcdsflowconventions"></a>
## ListCdsFlowConventions

> ResourceListOfGetCdsFlowConventionsResponse ListCdsFlowConventions(DateTimeOffset? asAt = null)

[BETA] ListCdsFlowConventions: List the set of CDS Flow Conventions

List the set of CDS Flow Conventions at the specified date/time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfGetCdsFlowConventionsResponse result = apiInstance.ListCdsFlowConventions(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the conventions. Defaults to latest if not specified. |

### Return type

[ResourceListOfGetCdsFlowConventionsResponse](ResourceListOfGetCdsFlowConventionsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested CDS Flow conventions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCdsFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetCdsFlowConventionsResponse> response = apiInstance.ListCdsFlowConventionsWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listflowconventions"></a>
## ListFlowConventions

> ResourceListOfGetFlowConventionsResponse ListFlowConventions(DateTimeOffset? asAt = null)

[BETA] ListFlowConventions: List the set of Flow Conventions

List the set of Flow Conventions at the specified date/time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfGetFlowConventionsResponse result = apiInstance.ListFlowConventions(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the conventions. Defaults to latest if not specified. |

### Return type

[ResourceListOfGetFlowConventionsResponse](ResourceListOfGetFlowConventionsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Flow conventions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetFlowConventionsResponse> response = apiInstance.ListFlowConventionsWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listindexconvention"></a>
## ListIndexConvention

> ResourceListOfGetIndexConventionResponse ListIndexConvention(DateTimeOffset? asAt = null)

[BETA] ListIndexConvention: List the set of Index Conventions

List the set of Index Conventions at the specified date/time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfGetIndexConventionResponse result = apiInstance.ListIndexConvention(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the conventions. Defaults to latest if not specified. |

### Return type

[ResourceListOfGetIndexConventionResponse](ResourceListOfGetIndexConventionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Index conventions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListIndexConventionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetIndexConventionResponse> response = apiInstance.ListIndexConventionWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcdsflowconventions"></a>
## UpsertCdsFlowConventions

> UpsertSingleStructuredDataResponse UpsertCdsFlowConventions(UpsertCdsFlowConventionsRequest upsertCdsFlowConventionsRequest)

[BETA] UpsertCdsFlowConventions: Upsert a set of CDS Flow Conventions. This creates or updates the data in Lusid.

Update or insert CDS Flow Conventions in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted CDS Flow Conventions or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var upsertCdsFlowConventionsRequest = new UpsertCdsFlowConventionsRequest(); // UpsertCdsFlowConventionsRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertCdsFlowConventions(upsertCdsFlowConventionsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertCdsFlowConventionsRequest** | [UpsertCdsFlowConventionsRequest](UpsertCdsFlowConventionsRequest.md) | body | **required** | The CDS Flow Conventions to update or insert |

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
<summary>Using the UpsertCdsFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertCdsFlowConventionsWithHttpInfo(upsertCdsFlowConventionsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertflowconventions"></a>
## UpsertFlowConventions

> UpsertSingleStructuredDataResponse UpsertFlowConventions(UpsertFlowConventionsRequest upsertFlowConventionsRequest)

[BETA] UpsertFlowConventions: Upsert Flow Conventions. This creates or updates the data in Lusid.

Update or insert Flow Conventions in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Flow Conventions or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var upsertFlowConventionsRequest = new UpsertFlowConventionsRequest(); // UpsertFlowConventionsRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertFlowConventions(upsertFlowConventionsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertFlowConventionsRequest** | [UpsertFlowConventionsRequest](UpsertFlowConventionsRequest.md) | body | **required** | The Flow Conventions to update or insert |

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
<summary>Using the UpsertFlowConventionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertFlowConventionsWithHttpInfo(upsertFlowConventionsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertindexconvention"></a>
## UpsertIndexConvention

> UpsertSingleStructuredDataResponse UpsertIndexConvention(UpsertIndexConventionRequest upsertIndexConventionRequest)

[BETA] UpsertIndexConvention: Upsert a set of Index Convention. This creates or updates the data in Lusid.

Update or insert Index Convention in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Index Convention or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ConventionsApi>();
var upsertIndexConventionRequest = new UpsertIndexConventionRequest(); // UpsertIndexConventionRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertIndexConvention(upsertIndexConventionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertIndexConventionRequest** | [UpsertIndexConventionRequest](UpsertIndexConventionRequest.md) | body | **required** | The Index Conventions to update or insert |

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
<summary>Using the UpsertIndexConventionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertIndexConventionWithHttpInfo(upsertIndexConventionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

