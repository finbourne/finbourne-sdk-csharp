# Finbourne.Sdk.Lusid.Api.AborConfigurationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateAborConfiguration**](#createaborconfiguration) | **POST** `/api/api/aborconfiguration/{scope}` | [EXPERIMENTAL] CreateAborConfiguration: Create an AborConfiguration. |
| [**DeleteAborConfiguration**](#deleteaborconfiguration) | **DELETE** `/api/api/aborconfiguration/{scope}/{code}` | [EXPERIMENTAL] DeleteAborConfiguration: Delete an AborConfiguration. |
| [**GetAborConfiguration**](#getaborconfiguration) | **GET** `/api/api/aborconfiguration/{scope}/{code}` | [EXPERIMENTAL] GetAborConfiguration: Get AborConfiguration. |
| [**GetAborConfigurationProperties**](#getaborconfigurationproperties) | **GET** `/api/api/aborconfiguration/{scope}/{code}/properties` | [EXPERIMENTAL] GetAborConfigurationProperties: Get Abor Configuration properties |
| [**ListAborConfigurations**](#listaborconfigurations) | **GET** `/api/api/aborconfiguration` | [EXPERIMENTAL] ListAborConfigurations: List AborConfiguration. |
| [**PatchAborConfiguration**](#patchaborconfiguration) | **PATCH** `/api/api/aborconfiguration/{scope}/{code}` | [EXPERIMENTAL] PatchAborConfiguration: Patch Abor Configuration. |
| [**UpsertAborConfigurationProperties**](#upsertaborconfigurationproperties) | **POST** `/api/api/aborconfiguration/{scope}/{code}/properties/$upsert` | [EXPERIMENTAL] UpsertAborConfigurationProperties: Upsert AborConfiguration properties |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AborConfigurationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
```

---

<a id="createaborconfiguration"></a>
## CreateAborConfiguration

> AborConfiguration CreateAborConfiguration(string scope, AborConfigurationRequest aborConfigurationRequest)

[EXPERIMENTAL] CreateAborConfiguration: Create an AborConfiguration.

Create the given AborConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var scope = "scope_example";  // string
var aborConfigurationRequest = new AborConfigurationRequest(); // AborConfigurationRequest
AborConfiguration result = apiInstance.CreateAborConfiguration(scope, aborConfigurationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the AborConfiguration. |
| **aborConfigurationRequest** | [AborConfigurationRequest](AborConfigurationRequest.md) | body | **required** | The definition of the AborConfiguration. |

### Return type

[AborConfiguration](AborConfiguration.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created abor configuration. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateAborConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborConfiguration> response = apiInstance.CreateAborConfigurationWithHttpInfo(scope, aborConfigurationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteaborconfiguration"></a>
## DeleteAborConfiguration

> DeletedEntityResponse DeleteAborConfiguration(string scope, string code)

[EXPERIMENTAL] DeleteAborConfiguration: Delete an AborConfiguration.

Delete the given AborConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteAborConfiguration(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the AborConfiguration to be deleted. |
| **code** | **string** | path | **required** | The code of the AborConfiguration to be deleted. Together with the scope this uniquely identifies the AborConfiguration. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Abor was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteAborConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteAborConfigurationWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaborconfiguration"></a>
## GetAborConfiguration

> AborConfiguration GetAborConfiguration(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetAborConfiguration: Get AborConfiguration.

Retrieve the definition of a particular AborConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
AborConfiguration result = apiInstance.GetAborConfiguration(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the AborConfiguration. |
| **code** | **string** | path | **required** | The code of the AborConfiguration. Together with the scope this uniquely identifies the AborConfiguration. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the AborConfiguration properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the AborConfiguration definition. Defaults to returning the latest version of the AborConfiguration definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;AborConfiguration&#39; domain to decorate onto the AborConfiguration.              These must take the format {domain}/{scope}/{code}, for example &#39;AborConfiguration/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[AborConfiguration](AborConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested AborConfiguration definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAborConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborConfiguration> response = apiInstance.GetAborConfigurationWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaborconfigurationproperties"></a>
## GetAborConfigurationProperties

> AborConfigurationProperties GetAborConfigurationProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAborConfigurationProperties: Get Abor Configuration properties

Get all the properties of a single abor Configuration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AborConfigurationProperties result = apiInstance.GetAborConfigurationProperties(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor Configuration to list the properties for. |
| **code** | **string** | path | **required** | The code of the Abor Configuration to list the properties for. Together with the scope this uniquely identifies the Abor Configuration. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Abor Configuration&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Abor Configuration&#39;s properties. Defaults to return the latest version of each property if not specified. |

### Return type

[AborConfigurationProperties](AborConfigurationProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified abor Configuration |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAborConfigurationPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborConfigurationProperties> response = apiInstance.GetAborConfigurationPropertiesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listaborconfigurations"></a>
## ListAborConfigurations

> PagedResourceListOfAborConfiguration ListAborConfigurations(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListAborConfigurations: List AborConfiguration.

List all the AborConfiguration matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfAborConfiguration result = apiInstance.ListAborConfigurations(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the AborConfiguration. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the AborConfiguration. Defaults to returning the latest version of each AAborConfigurationbor if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing AborConfiguration; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the AborConfiguration type, specify \&quot;id.Code eq &#39;AborConfiguration1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;AborConfiguration&#39; domain to decorate onto each AborConfiguration.              These must take the format {domain}/{scope}/{code}, for example &#39;AborConfiguration/Manager/Id&#39;. |

### Return type

[PagedResourceListOfAborConfiguration](PagedResourceListOfAborConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested abor configurations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAborConfigurationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAborConfiguration> response = apiInstance.ListAborConfigurationsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchaborconfiguration"></a>
## PatchAborConfiguration

> AborConfiguration PatchAborConfiguration(string scope, string code, List<Operation> operation)

[EXPERIMENTAL] PatchAborConfiguration: Patch Abor Configuration.

Create or update certain fields for a particular AborConfiguration.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description, PostingModuleCodes, CleardownModuleCodes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
AborConfiguration result = apiInstance.PatchAborConfiguration(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the AborConfiguration. |
| **code** | **string** | path | **required** | The code of the AborConfiguration.              Together with the scope this uniquely identifies the AborConfiguration. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[AborConfiguration](AborConfiguration.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched AborConfiguration |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchAborConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborConfiguration> response = apiInstance.PatchAborConfigurationWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertaborconfigurationproperties"></a>
## UpsertAborConfigurationProperties

> AborConfigurationProperties UpsertAborConfigurationProperties(string scope, string code, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertAborConfigurationProperties: Upsert AborConfiguration properties

Update or insert one or more properties onto a single AborConfiguration. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'AborConfiguration'.                Upserting a property that exists for an AborConfiguration, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
AborConfigurationProperties result = apiInstance.UpsertAborConfigurationProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the AborConfiguration to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the AborConfiguration to update or insert the properties onto. Together with the scope this uniquely identifies the AborConfiguration. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the chart of account. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;AborConfiguration/Manager/Id\&quot;. |

### Return type

[AborConfigurationProperties](AborConfigurationProperties.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted properties |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertAborConfigurationPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborConfigurationProperties> response = apiInstance.UpsertAborConfigurationPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

