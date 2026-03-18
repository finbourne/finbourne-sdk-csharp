# Finbourne.Sdk.Luminesce.Api.CurrentTableFieldCatalogApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetCatalog**](#getcatalog) | **GET** `/honeycomb/api/Catalog` | GetCatalog: Get a Flattened Table/Field Catalog |
| [**GetCatalogV1**](#getcatalogv1) | **GET** `/honeycomb/api/CatalogV1` | [DEPRECATED] GetCatalogV1: Get a Flattened Table/Field Catalog |
| [**GetFields**](#getfields) | **GET** `/honeycomb/api/Catalog/fields` | GetFields: List field and parameters for providers |
| [**GetFieldsV1**](#getfieldsv1) | **GET** `/honeycomb/api/CatalogV1/fields` | [DEPRECATED] GetFieldsV1: List field and parameters for providers |
| [**GetProviders**](#getproviders) | **GET** `/honeycomb/api/Catalog/providers` | GetProviders: List available providers |
| [**GetProvidersV1**](#getprovidersv1) | **GET** `/honeycomb/api/CatalogV1/providers` | [DEPRECATED] GetProvidersV1: List available providers |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Luminesce.Api;
using Finbourne.Sdk.Luminesce.Client;
using Finbourne.Sdk.Luminesce.Extensions;
using Finbourne.Sdk.Services.Luminesce.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CurrentTableFieldCatalogApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
```

---

<a id="getcatalog"></a>
## GetCatalog

> string GetCatalog(string? freeTextSearch = null, bool? jsonProper = null)

GetCatalog: Get a Flattened Table/Field Catalog

 Returns the User's full version of the catalog (Providers, their fields and associated information) that are currently running that you have access to (in Json format).  This is the entire catalog flattened, which is often quite large and always a bit repetitive.   The internal results are cached for several minutes.  Consider using `api/Catalog/providers` and `api/Catalog/fields` for a more granular and incremental loading flow.  It is possible to be throttled if you make too many requests in a short period of time, receiving a: - 429 Too Many Requests : Please try your request again soon  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
var freeTextSearch = "freeTextSearch_example";  // string? (optional)
var jsonProper = false;  // bool? (optional)
string result = apiInstance.GetCatalog(freeTextSearch, jsonProper);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **freeTextSearch** | **string?** | query | optional | Limit the catalog to only things in some way dealing with the passed in text string |
| **jsonProper** | **bool?** | query | optional | Should this be text/json (not json-encoded-as-a-string) Default: `false` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetCatalogWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetCatalogWithHttpInfo(freeTextSearch, jsonProper);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcatalogv1"></a>
## GetCatalogV1

> string GetCatalogV1(string? freeTextSearch = null, bool? jsonProper = null, bool? useCache = null)

[DEPRECATED] GetCatalogV1: Get a Flattened Table/Field Catalog

 Returns the User's full version of the catalog (Providers, their fields and associated information) that are currently running that you have access to (in Json format).  This is the entire catalog flattened, which is often quite large and always a bit repetitive.   The internal results are cached for several minutes.  Consider using `api/Catalog/providers` and `api/Catalog/fields` for a more granular and incremental loading flow.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
var freeTextSearch = "freeTextSearch_example";  // string? (optional)
var jsonProper = false;  // bool? (optional)
var useCache = false;  // bool? (optional)
string result = apiInstance.GetCatalogV1(freeTextSearch, jsonProper, useCache);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **freeTextSearch** | **string?** | query | optional | Limit the catalog to only things in some way dealing with the passed in text string |
| **jsonProper** | **bool?** | query | optional | Should this be text/json (not json-encoded-as-a-string) Default: `false` |
| **useCache** | **bool?** | query | optional | Should the available cache be used? false is effectively to pick up a change in the catalog Default: `false` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetCatalogV1WithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetCatalogV1WithHttpInfo(freeTextSearch, jsonProper, useCache);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfields"></a>
## GetFields

> string GetFields(string? tableLike = null, bool? addLineage = null)

GetFields: List field and parameters for providers

 Returns the User's full version of the catalog but only the field/parameter-level information  (as well as the TableName they refer to, of course) for tables matching the `tableLike` (manually include wildcards if desired).  The internal results are cached for several minutes.  It is possible to be throttled if you make too many requests in a short period of time, receiving a: - 429 Too Many Requests : Please try your request again soon  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
var tableLike = "\"%\"";  // string? (optional)
var addLineage = false;  // bool? (optional)
string result = apiInstance.GetFields(tableLike, addLineage);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **tableLike** | **string?** | query | optional | Allows for SQL-LIKE style filtering of which Providers you want the fields for. Default: `&quot;%&quot;` |
| **addLineage** | **bool?** | query | optional | Adds in any column lineage which is registered in the catalog to the results. Default: `false` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetFieldsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetFieldsWithHttpInfo(tableLike, addLineage);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfieldsv1"></a>
## GetFieldsV1

> string GetFieldsV1(string? tableLike = null)

[DEPRECATED] GetFieldsV1: List field and parameters for providers

 Returns the User's full version of the catalog but only the field/parameter-level information  (as well as the TableName they refer to, of course) for tables matching the `tableLike` (manually include wildcards if desired).  The internal results are cached for several minutes.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
var tableLike = "\"%\"";  // string? (optional)
string result = apiInstance.GetFieldsV1(tableLike);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **tableLike** | **string?** | query | optional |  Default: `&quot;%&quot;` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetFieldsV1WithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetFieldsV1WithHttpInfo(tableLike);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getproviders"></a>
## GetProviders

> string GetProviders(string? freeTextSearch = null, bool? addLineage = null)

GetProviders: List available providers

 Returns the User's full version of the catalog but only the table/provider-level information they have access to.  The internal results are cached for several minutes.  It is possible to be throttled if you make too many requests in a short period of time, receiving a: - 429 Too Many Requests : Please try your request again soon  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
var freeTextSearch = "freeTextSearch_example";  // string? (optional)
var addLineage = false;  // bool? (optional)
string result = apiInstance.GetProviders(freeTextSearch, addLineage);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **freeTextSearch** | **string?** | query | optional | Limit the catalog to only things in some way dealing with the passed in text string |
| **addLineage** | **bool?** | query | optional | Adds in any column lineage which is registered in the catalog to the results. Default: `false` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetProvidersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetProvidersWithHttpInfo(freeTextSearch, addLineage);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getprovidersv1"></a>
## GetProvidersV1

> string GetProvidersV1(string? freeTextSearch = null, bool? useCache = null)

[DEPRECATED] GetProvidersV1: List available providers

 Returns the User's full version of the catalog but only the table/provider-level information they have access to.  The internal results are cached for several minutes.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CurrentTableFieldCatalogApi>();
var freeTextSearch = "freeTextSearch_example";  // string? (optional)
var useCache = true;  // bool? (optional)
string result = apiInstance.GetProvidersV1(freeTextSearch, useCache);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **freeTextSearch** | **string?** | query | optional | Limit the catalog to only things in some way dealing with the passed in text string |
| **useCache** | **bool?** | query | optional | Should the available cache be used? false is effectively to pick up a change in the catalog Default: `true` |

### Return type

**string**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetProvidersV1WithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<string> response = apiInstance.GetProvidersV1WithHttpInfo(freeTextSearch, useCache);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

