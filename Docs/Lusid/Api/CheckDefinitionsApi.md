# Finbourne.Sdk.Lusid.Api.CheckDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCheckDefinition**](#createcheckdefinition) | **POST** `/api/api/dataquality/checkdefinitions` | [EXPERIMENTAL] CreateCheckDefinition: Create a Check Definition |
| [**DeleteCheckDefinition**](#deletecheckdefinition) | **DELETE** `/api/api/dataquality/checkdefinitions/{scope}/{code}` | [EXPERIMENTAL] DeleteCheckDefinition: Deletes a particular Check Definition |
| [**DeleteRules**](#deleterules) | **POST** `/api/api/dataquality/checkdefinitions/{scope}/{code}/$deleteRules` | [EXPERIMENTAL] DeleteRules: Delete rules on a particular Check Definition |
| [**GetCheckDefinition**](#getcheckdefinition) | **GET** `/api/api/dataquality/checkdefinitions/{scope}/{code}` | [EXPERIMENTAL] GetCheckDefinition: Get a single Check Definition by scope and code. |
| [**ListCheckDefinitions**](#listcheckdefinitions) | **GET** `/api/api/dataquality/checkdefinitions` | [EXPERIMENTAL] ListCheckDefinitions: List Check Definitions |
| [**RunCheckDefinition**](#runcheckdefinition) | **POST** `/api/api/dataquality/checkdefinitions/{scope}/{code}/$run` | [EXPERIMENTAL] RunCheckDefinition: Runs a Check Definition against given dataset. |
| [**UpdateCheckDefinition**](#updatecheckdefinition) | **PUT** `/api/api/dataquality/checkdefinitions/{scope}/{code}` | [EXPERIMENTAL] UpdateCheckDefinition: Update Check Definition defined by scope and code |
| [**UpsertRules**](#upsertrules) | **POST** `/api/api/dataquality/checkdefinitions/{scope}/{code}/$upsertRules` | [EXPERIMENTAL] UpsertRules: Upsert rules to a particular Check Definition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CheckDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
```

---

<a id="createcheckdefinition"></a>
## CreateCheckDefinition

> CheckDefinition CreateCheckDefinition(CreateCheckDefinitionRequest? createCheckDefinitionRequest = null)

[EXPERIMENTAL] CreateCheckDefinition: Create a Check Definition

Creates a Check Definition. Returns the created Check Definition at the current effectiveAt.  Note that Check Definitions are mono-temporal, however they can have Time-Variant Properties.  Upserted Properties will be returned at the latest AsAt and EffectiveAt

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var createCheckDefinitionRequest = new CreateCheckDefinitionRequest?(); // CreateCheckDefinitionRequest? (optional)
CheckDefinition result = apiInstance.CreateCheckDefinition(createCheckDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createCheckDefinitionRequest** | [CreateCheckDefinitionRequest?](CreateCheckDefinitionRequest?.md) | body | optional | The request containing the details of the Check Definition |

### Return type

[CheckDefinition](CheckDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created Check Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCheckDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CheckDefinition> response = apiInstance.CreateCheckDefinitionWithHttpInfo(createCheckDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecheckdefinition"></a>
## DeleteCheckDefinition

> DeletedEntityResponse DeleteCheckDefinition(string scope, string code)

[EXPERIMENTAL] DeleteCheckDefinition: Deletes a particular Check Definition

The deletion will take effect from the Check Definition deletion datetime.  i.e. will no longer exist at any asAt datetime after the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteCheckDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Check Definition. |
| **code** | **string** | path | **required** | The code of the specified Check Definition. Together with the domain and scope this uniquely              identifies the Check Definition. |

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
<summary>Using the DeleteCheckDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCheckDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterules"></a>
## DeleteRules

> CheckDefinition DeleteRules(string scope, string code, List<DeleteDataQualityRule>? deleteDataQualityRule = null)

[EXPERIMENTAL] DeleteRules: Delete rules on a particular Check Definition

Delete rules for a given check definition. This will not affect any other rules that are not included in the request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var deleteDataQualityRule = new List<DeleteDataQualityRule>?(); // List<DeleteDataQualityRule>? (optional)
CheckDefinition result = apiInstance.DeleteRules(scope, code, deleteDataQualityRule);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Check Definition. |
| **code** | **string** | path | **required** | The code of the specified Check Definition. Together with the domain and scope this uniquely              identifies the Check Definition. |
| **deleteDataQualityRule** | [List&lt;DeleteDataQualityRule&gt;?](DeleteDataQualityRule.md) | body | optional | The request containing the rules to be deleted |

### Return type

[CheckDefinition](CheckDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated check definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CheckDefinition> response = apiInstance.DeleteRulesWithHttpInfo(scope, code, deleteDataQualityRule);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcheckdefinition"></a>
## GetCheckDefinition

> CheckDefinition GetCheckDefinition(string scope, string code, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetCheckDefinition: Get a single Check Definition by scope and code.

Retrieves one Check Definition by scope and code.  Check Definitions are mono-temporal. The EffectiveAt is only applied to Time-Variant Properties.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
CheckDefinition result = apiInstance.GetCheckDefinition(scope, code, asAt, effectiveAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Check Definition. |
| **code** | **string** | path | **required** | The code of the specified Check Definition. Together with the scope this uniquely              identifies the Check Definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Check Definition definition. Defaults to return              the latest version of the definition if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the check definition properties.              Defaults to the current LUSID system datetime if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;CheckDefinition&#39; domain to decorate onto              the Check Definition.              These must have the format {domain}/{scope}/{code}, for example &#39;CheckDefinition/system/Name&#39;. |

### Return type

[CheckDefinition](CheckDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Check Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCheckDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CheckDefinition> response = apiInstance.GetCheckDefinitionWithHttpInfo(scope, code, asAt, effectiveAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcheckdefinitions"></a>
## ListCheckDefinitions

> PagedResourceListOfCheckDefinition ListCheckDefinitions(DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListCheckDefinitions: List Check Definitions

List all the Check Definitions matching a particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfCheckDefinition result = apiInstance.ListCheckDefinitions(asAt, effectiveAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Check Definitions. Defaults to returning the latest version of each Check Definition if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Check Definitions.              Note that Check Definitions are monotemporal, the effectiveAt is for Timevariant Properties on the Check Definition only.              Defaults to the current LUSID system datetime if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Check Definitions; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the displayName, specify \&quot;displayName eq &#39;MyCheckDefinition&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;CheckDefinition&#39; domain to decorate onto each Check Definition.              These must take the format {domain}/{scope}/{code}, for example &#39;CheckDefinition/Account/id&#39;. |

### Return type

[PagedResourceListOfCheckDefinition](PagedResourceListOfCheckDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Check Definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCheckDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCheckDefinition> response = apiInstance.ListCheckDefinitionsWithHttpInfo(asAt, effectiveAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runcheckdefinition"></a>
## RunCheckDefinition

> RunCheckResponse RunCheckDefinition(string scope, string code, RunCheckRequest? runCheckRequest = null)

[EXPERIMENTAL] RunCheckDefinition: Runs a Check Definition against given dataset.

Runs a Check Definition against given dataset.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var runCheckRequest = new RunCheckRequest?(); // RunCheckRequest? (optional)
RunCheckResponse result = apiInstance.RunCheckDefinition(scope, code, runCheckRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the CheckDefinition to run. |
| **code** | **string** | path | **required** | Code of the CheckDefinition to run. |
| **runCheckRequest** | [RunCheckRequest?](RunCheckRequest?.md) | body | optional | Run request defining what dataset to run against. |

### Return type

[RunCheckResponse](RunCheckResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunCheckDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RunCheckResponse> response = apiInstance.RunCheckDefinitionWithHttpInfo(scope, code, runCheckRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecheckdefinition"></a>
## UpdateCheckDefinition

> CheckDefinition UpdateCheckDefinition(string scope, string code, UpdateCheckDefinitionRequest? updateCheckDefinitionRequest = null)

[EXPERIMENTAL] UpdateCheckDefinition: Update Check Definition defined by scope and code

Overwrites an existing Check Definition  Update request has the same required fields as Create apart from the id.  Returns the updated Check Definition at the current effectiveAt.  Note that Check Definitions are mono-temporal, however they can have Time-Variant Properties.  Updated Properties will be returned at the latest AsAt and EffectiveAt

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateCheckDefinitionRequest = new UpdateCheckDefinitionRequest?(); // UpdateCheckDefinitionRequest? (optional)
CheckDefinition result = apiInstance.UpdateCheckDefinition(scope, code, updateCheckDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Check Definition. |
| **code** | **string** | path | **required** | The code of the specified Check Definition. Together with the domain and scope this uniquely identifies the Check Definition. |
| **updateCheckDefinitionRequest** | [UpdateCheckDefinitionRequest?](UpdateCheckDefinitionRequest?.md) | body | optional | The request containing the updated details of the Check Definition |

### Return type

[CheckDefinition](CheckDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated version of the requested Check Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateCheckDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CheckDefinition> response = apiInstance.UpdateCheckDefinitionWithHttpInfo(scope, code, updateCheckDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertrules"></a>
## UpsertRules

> CheckDefinition UpsertRules(string scope, string code, List<UpsertDataQualityRule>? upsertDataQualityRule = null)

[EXPERIMENTAL] UpsertRules: Upsert rules to a particular Check Definition

Upsert rules for a given check definition. This will not affect any other rules that are not included in the request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CheckDefinitionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertDataQualityRule = new List<UpsertDataQualityRule>?(); // List<UpsertDataQualityRule>? (optional)
CheckDefinition result = apiInstance.UpsertRules(scope, code, upsertDataQualityRule);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the specified Check Definition. |
| **code** | **string** | path | **required** | The code of the specified Check Definition. Together with the domain and scope this uniquely              identifies the Check Definition. |
| **upsertDataQualityRule** | [List&lt;UpsertDataQualityRule&gt;?](UpsertDataQualityRule.md) | body | optional | The request containing the rules to be upserted |

### Return type

[CheckDefinition](CheckDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated check definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CheckDefinition> response = apiInstance.UpsertRulesWithHttpInfo(scope, code, upsertDataQualityRule);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

