# Finbourne.Sdk.Horizon.Api.VendorApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetCoreFieldMappingsForProductEntity**](#getcorefieldmappingsforproductentity) | **GET** `/horizon/api/vendor/mappings/fields` | [EARLY ACCESS] GetCoreFieldMappingsForProductEntity: Get core field mappings for a given vendor product&#39;s entity. |
| [**GetOptionalMappingsForProductEntity**](#getoptionalmappingsforproductentity) | **GET** `/horizon/api/vendor/mappings/optional` | [EARLY ACCESS] GetOptionalMappingsForProductEntity: Get a user defined LUSID property mappings for the specified vendor / LUSID entity. |
| [**GetPropertyMappingsForProductEntity**](#getpropertymappingsforproductentity) | **GET** `/horizon/api/vendor/mappings/properties` | [EARLY ACCESS] GetPropertyMappingsForProductEntity: Gets the property mappings for a given vendor product&#39;s entity |
| [**QueryVendors**](#queryvendors) | **POST** `/horizon/api/vendor/$query` | [EARLY ACCESS] QueryVendors: Query for vendors and their packages with entities and sub-entities. |
| [**SetOptionalMappingsForProductEntity**](#setoptionalmappingsforproductentity) | **POST** `/horizon/api/vendor/mappings/optional` | [EARLY ACCESS] SetOptionalMappingsForProductEntity: Create a user defined LUSID property mappings for the specified vendor / LUSID entity. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<VendorApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorApi>();
```

---

<a id="getcorefieldmappingsforproductentity"></a>
## GetCoreFieldMappingsForProductEntity

> List&lt;LusidField&gt; GetCoreFieldMappingsForProductEntity(string vendorName, string productName, string lusidEntityType, string? lusidEntitySubType = null)

[EARLY ACCESS] GetCoreFieldMappingsForProductEntity: Get core field mappings for a given vendor product's entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorApi>();
var vendorName = "vendorName_example";  // string
var productName = "productName_example";  // string
var lusidEntityType = "lusidEntityType_example";  // string
var lusidEntitySubType = "lusidEntitySubType_example";  // string? (optional)
List<LusidField> result = apiInstance.GetCoreFieldMappingsForProductEntity(vendorName, productName, lusidEntityType, lusidEntitySubType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **vendorName** | **string** | query | **required** |  |
| **productName** | **string** | query | **required** |  |
| **lusidEntityType** | **string** | query | **required** |  |
| **lusidEntitySubType** | **string?** | query | optional |  |

### Return type

[List&lt;LusidField&gt;](LusidField.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCoreFieldMappingsForProductEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<LusidField>> response = apiInstance.GetCoreFieldMappingsForProductEntityWithHttpInfo(vendorName, productName, lusidEntityType, lusidEntitySubType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getoptionalmappingsforproductentity"></a>
## GetOptionalMappingsForProductEntity

> Dictionary&lt;string, LusidPropertyDefinitionOverrides&gt; GetOptionalMappingsForProductEntity(string vendorName, string productName, string lusidEntityType, string? lusidEntitySubType = null)

[EARLY ACCESS] GetOptionalMappingsForProductEntity: Get a user defined LUSID property mappings for the specified vendor / LUSID entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorApi>();
var vendorName = "vendorName_example";  // string
var productName = "productName_example";  // string
var lusidEntityType = "lusidEntityType_example";  // string
var lusidEntitySubType = "lusidEntitySubType_example";  // string? (optional)
Dictionary<string, LusidPropertyDefinitionOverrides> result = apiInstance.GetOptionalMappingsForProductEntity(vendorName, productName, lusidEntityType, lusidEntitySubType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **vendorName** | **string** | query | **required** |  |
| **productName** | **string** | query | **required** |  |
| **lusidEntityType** | **string** | query | **required** |  |
| **lusidEntitySubType** | **string?** | query | optional |  |

### Return type

[Dictionary&lt;string, LusidPropertyDefinitionOverrides&gt;](LusidPropertyDefinitionOverrides.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | The details of the input related failure |  -  |
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetOptionalMappingsForProductEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, LusidPropertyDefinitionOverrides>> response = apiInstance.GetOptionalMappingsForProductEntityWithHttpInfo(vendorName, productName, lusidEntityType, lusidEntitySubType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpropertymappingsforproductentity"></a>
## GetPropertyMappingsForProductEntity

> List&lt;LusidPropertyToVendorFieldMapping&gt; GetPropertyMappingsForProductEntity(string vendorName, string productName, string lusidEntityType, string? lusidEntitySubType = null)

[EARLY ACCESS] GetPropertyMappingsForProductEntity: Gets the property mappings for a given vendor product's entity

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorApi>();
var vendorName = "vendorName_example";  // string
var productName = "productName_example";  // string
var lusidEntityType = "lusidEntityType_example";  // string
var lusidEntitySubType = "lusidEntitySubType_example";  // string? (optional)
List<LusidPropertyToVendorFieldMapping> result = apiInstance.GetPropertyMappingsForProductEntity(vendorName, productName, lusidEntityType, lusidEntitySubType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **vendorName** | **string** | query | **required** |  |
| **productName** | **string** | query | **required** |  |
| **lusidEntityType** | **string** | query | **required** |  |
| **lusidEntitySubType** | **string?** | query | optional |  |

### Return type

[List&lt;LusidPropertyToVendorFieldMapping&gt;](LusidPropertyToVendorFieldMapping.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPropertyMappingsForProductEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<LusidPropertyToVendorFieldMapping>> response = apiInstance.GetPropertyMappingsForProductEntityWithHttpInfo(vendorName, productName, lusidEntityType, lusidEntitySubType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="queryvendors"></a>
## QueryVendors

> PagedResourceListOfVendorProduct QueryVendors(QueryRequest queryRequest)

[EARLY ACCESS] QueryVendors: Query for vendors and their packages with entities and sub-entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorApi>();
var queryRequest = new QueryRequest(); // QueryRequest
PagedResourceListOfVendorProduct result = apiInstance.QueryVendors(queryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **queryRequest** | [QueryRequest](QueryRequest.md) | body | **required** |  |

### Return type

[PagedResourceListOfVendorProduct](PagedResourceListOfVendorProduct.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryVendorsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfVendorProduct> response = apiInstance.QueryVendorsWithHttpInfo(queryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setoptionalmappingsforproductentity"></a>
## SetOptionalMappingsForProductEntity

> Dictionary&lt;string, LusidPropertyDefinitionOverridesResponse&gt; SetOptionalMappingsForProductEntity(string vendorName, string productName, string lusidEntityType, Dictionary<string, LusidPropertyDefinitionOverrides> requestBody, string? lusidEntitySubType = null)

[EARLY ACCESS] SetOptionalMappingsForProductEntity: Create a user defined LUSID property mappings for the specified vendor / LUSID entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<VendorApi>();
var vendorName = "vendorName_example";  // string
var productName = "productName_example";  // string
var lusidEntityType = "lusidEntityType_example";  // string
var requestBody = new Dictionary<string, LusidPropertyDefinitionOverrides>(); // Dictionary<string, LusidPropertyDefinitionOverrides>
var lusidEntitySubType = "lusidEntitySubType_example";  // string? (optional)
Dictionary<string, LusidPropertyDefinitionOverridesResponse> result = apiInstance.SetOptionalMappingsForProductEntity(vendorName, productName, lusidEntityType, requestBody, lusidEntitySubType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **vendorName** | **string** | query | **required** |  |
| **productName** | **string** | query | **required** |  |
| **lusidEntityType** | **string** | query | **required** |  |
| **requestBody** | [Dictionary&lt;string, LusidPropertyDefinitionOverrides&gt;](LusidPropertyDefinitionOverrides.md) | body | **required** |  |
| **lusidEntitySubType** | **string?** | query | optional |  |

### Return type

[Dictionary&lt;string, LusidPropertyDefinitionOverridesResponse&gt;](LusidPropertyDefinitionOverridesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | The details of the input related failure |  -  |
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetOptionalMappingsForProductEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, LusidPropertyDefinitionOverridesResponse>> response = apiInstance.SetOptionalMappingsForProductEntityWithHttpInfo(vendorName, productName, lusidEntityType, requestBody, lusidEntitySubType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

