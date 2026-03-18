# Finbourne.Sdk.Lusid.Api.FundConfigurationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateFundConfiguration**](#createfundconfiguration) | **POST** `/api/api/fundconfigurations/{scope}` | [EXPERIMENTAL] CreateFundConfiguration: Create a FundConfiguration. |
| [**DeleteFundConfiguration**](#deletefundconfiguration) | **DELETE** `/api/api/fundconfigurations/{scope}/{code}` | [EXPERIMENTAL] DeleteFundConfiguration: Delete a FundConfiguration. |
| [**GetFundConfiguration**](#getfundconfiguration) | **GET** `/api/api/fundconfigurations/{scope}/{code}` | [EXPERIMENTAL] GetFundConfiguration: Get FundConfiguration. |
| [**ListFundConfigurations**](#listfundconfigurations) | **GET** `/api/api/fundconfigurations` | [EXPERIMENTAL] ListFundConfigurations: List FundConfiguration. |
| [**PatchFundConfiguration**](#patchfundconfiguration) | **PATCH** `/api/api/fundconfigurations/{scope}/{code}` | [EXPERIMENTAL] PatchFundConfiguration: Patch Fund Configuration. |
| [**UpsertFundConfigurationProperties**](#upsertfundconfigurationproperties) | **POST** `/api/api/fundconfigurations/{scope}/{code}/properties/$upsert` | [EXPERIMENTAL] UpsertFundConfigurationProperties: Upsert FundConfiguration properties |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FundConfigurationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
```

---

<a id="createfundconfiguration"></a>
## CreateFundConfiguration

> FundConfiguration CreateFundConfiguration(string scope, FundConfigurationRequest fundConfigurationRequest)

[EXPERIMENTAL] CreateFundConfiguration: Create a FundConfiguration.

Create the given FundConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
var scope = "scope_example";  // string
var fundConfigurationRequest = new FundConfigurationRequest(); // FundConfigurationRequest
FundConfiguration result = apiInstance.CreateFundConfiguration(scope, fundConfigurationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FundConfiguration. |
| **fundConfigurationRequest** | [FundConfigurationRequest](FundConfigurationRequest.md) | body | **required** | The definition of the FundConfiguration. |

### Return type

[FundConfiguration](FundConfiguration.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Fund configuration. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFundConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundConfiguration> response = apiInstance.CreateFundConfigurationWithHttpInfo(scope, fundConfigurationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletefundconfiguration"></a>
## DeleteFundConfiguration

> DeletedEntityResponse DeleteFundConfiguration(string scope, string code)

[EXPERIMENTAL] DeleteFundConfiguration: Delete a FundConfiguration.

Delete the given FundConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteFundConfiguration(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FundConfiguration to be deleted. |
| **code** | **string** | path | **required** | The code of the FundConfiguration to be deleted.               Together with the scope this uniquely identifies the FundConfiguration. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the FundConfiguration was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFundConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteFundConfigurationWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfundconfiguration"></a>
## GetFundConfiguration

> FundConfiguration GetFundConfiguration(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetFundConfiguration: Get FundConfiguration.

Retrieve the definition of a particular FundConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
FundConfiguration result = apiInstance.GetFundConfiguration(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FundConfiguration. |
| **code** | **string** | path | **required** | The code of the FundConfiguration. Together with the scope this uniquely identifies the FundConfiguration. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the FundConfiguration properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the FundConfiguration definition. Defaults to returning the latest version of the FundConfiguration definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;FundConfiguration&#39; domain to decorate onto the FundConfiguration.              These must take the format {domain}/{scope}/{code}, for example &#39;FundConfiguration/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[FundConfiguration](FundConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested FundConfiguration definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFundConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundConfiguration> response = apiInstance.GetFundConfigurationWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfundconfigurations"></a>
## ListFundConfigurations

> PagedResourceListOfFundConfiguration ListFundConfigurations(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFundConfigurations: List FundConfiguration.

List all the FundConfiguration matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFundConfiguration result = apiInstance.ListFundConfigurations(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the FundConfiguration.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the FundConfiguration. Defaults to returning the latest version of each FundConfiguration if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing FundConfiguration; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the FundConfiguration type, specify \&quot;id.Code eq &#39;FundConfiguration1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;FundConfiguration&#39; domain to decorate onto each FundConfiguration.              These must take the format {domain}/{scope}/{code}, for example &#39;FundConfiguration/Manager/Id&#39;. |

### Return type

[PagedResourceListOfFundConfiguration](PagedResourceListOfFundConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fund configurations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFundConfigurationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFundConfiguration> response = apiInstance.ListFundConfigurationsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchfundconfiguration"></a>
## PatchFundConfiguration

> FundConfiguration PatchFundConfiguration(string scope, string code, List<Operation> operation)

[EXPERIMENTAL] PatchFundConfiguration: Patch Fund Configuration.

Create or update certain fields for a particular FundConfiguration.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description, DealingFilters, PnlFilters, BackOutFilters, ExternalFeeFilters.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
FundConfiguration result = apiInstance.PatchFundConfiguration(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FundConfiguration. |
| **code** | **string** | path | **required** | The code of the FundConfiguration. Together with the              scope this uniquely identifies the FundConfiguration. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[FundConfiguration](FundConfiguration.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched FundConfiguration |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchFundConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundConfiguration> response = apiInstance.PatchFundConfigurationWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertfundconfigurationproperties"></a>
## UpsertFundConfigurationProperties

> FundConfigurationProperties UpsertFundConfigurationProperties(string scope, string code, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertFundConfigurationProperties: Upsert FundConfiguration properties

Update or insert one or more properties onto a single FundConfiguration. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'FundConfiguration'.                Upserting a property that exists for an FundConfiguration, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundConfigurationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
FundConfigurationProperties result = apiInstance.UpsertFundConfigurationProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the FundConfiguration to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the FundConfiguration to update or insert the properties onto. Together with the scope this uniquely identifies the FundConfiguration. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the Fund Configuration. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;FundConfiguration/Manager/Id\&quot;. |

### Return type

[FundConfigurationProperties](FundConfigurationProperties.md)

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
<summary>Using the UpsertFundConfigurationPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundConfigurationProperties> response = apiInstance.UpsertFundConfigurationPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

