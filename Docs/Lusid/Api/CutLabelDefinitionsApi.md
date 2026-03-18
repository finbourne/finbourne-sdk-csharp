# Finbourne.Sdk.Lusid.Api.CutLabelDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCutLabelDefinition**](#createcutlabeldefinition) | **POST** `/api/api/systemconfiguration/cutlabels` | CreateCutLabelDefinition: Create a Cut Label |
| [**DeleteCutLabelDefinition**](#deletecutlabeldefinition) | **DELETE** `/api/api/systemconfiguration/cutlabels/{code}` | DeleteCutLabelDefinition: Delete a Cut Label |
| [**GetCutLabelDefinition**](#getcutlabeldefinition) | **GET** `/api/api/systemconfiguration/cutlabels/{code}` | GetCutLabelDefinition: Get a Cut Label |
| [**ListCutLabelDefinitions**](#listcutlabeldefinitions) | **GET** `/api/api/systemconfiguration/cutlabels` | ListCutLabelDefinitions: List Existing Cut Labels |
| [**UpdateCutLabelDefinition**](#updatecutlabeldefinition) | **PUT** `/api/api/systemconfiguration/cutlabels/{code}` | UpdateCutLabelDefinition: Update a Cut Label |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CutLabelDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CutLabelDefinitionsApi>();
```

---

<a id="createcutlabeldefinition"></a>
## CreateCutLabelDefinition

> CutLabelDefinition CreateCutLabelDefinition(CreateCutLabelDefinitionRequest? createCutLabelDefinitionRequest = null)

CreateCutLabelDefinition: Create a Cut Label

Create a Cut Label valid in all scopes

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CutLabelDefinitionsApi>();
var createCutLabelDefinitionRequest = new CreateCutLabelDefinitionRequest?(); // CreateCutLabelDefinitionRequest? (optional)
CutLabelDefinition result = apiInstance.CreateCutLabelDefinition(createCutLabelDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createCutLabelDefinitionRequest** | [CreateCutLabelDefinitionRequest?](CreateCutLabelDefinitionRequest?.md) | body | optional | The cut label definition |

### Return type

[CutLabelDefinition](CutLabelDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created cut label |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCutLabelDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CutLabelDefinition> response = apiInstance.CreateCutLabelDefinitionWithHttpInfo(createCutLabelDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecutlabeldefinition"></a>
## DeleteCutLabelDefinition

> DateTimeOffset DeleteCutLabelDefinition(string code)

DeleteCutLabelDefinition: Delete a Cut Label

Delete a specified cut label

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CutLabelDefinitionsApi>();
var code = "code_example";  // string
DateTimeOffset result = apiInstance.DeleteCutLabelDefinition(code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The Code of the Cut Label that is being Deleted |

### Return type

**DateTimeOffset**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time of deletion |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCutLabelDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DateTimeOffset> response = apiInstance.DeleteCutLabelDefinitionWithHttpInfo(code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcutlabeldefinition"></a>
## GetCutLabelDefinition

> CutLabelDefinition GetCutLabelDefinition(string code, DateTimeOffset? asAt = null)

GetCutLabelDefinition: Get a Cut Label

Get a specified cut label at a given time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CutLabelDefinitionsApi>();
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CutLabelDefinition result = apiInstance.GetCutLabelDefinition(code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The Code of the Cut Label that is being queried |
| **asAt** | **DateTimeOffset?** | query | optional | The time at which to get the Cut Label |

### Return type

[CutLabelDefinition](CutLabelDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested cut label |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCutLabelDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CutLabelDefinition> response = apiInstance.GetCutLabelDefinitionWithHttpInfo(code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcutlabeldefinitions"></a>
## ListCutLabelDefinitions

> PagedResourceListOfCutLabelDefinition ListCutLabelDefinitions(DateTimeOffset? asAt = null, List<string>? sortBy = null, int? limit = null, string? filter = null, string? page = null)

ListCutLabelDefinitions: List Existing Cut Labels

List all the Cut Label Definitions that are valid at the given AsAt time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CutLabelDefinitionsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfCutLabelDefinition result = apiInstance.ListCutLabelDefinitions(asAt, sortBy, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The As At time at which listed Cut Labels are valid |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.              For example, to filter on code, use \&quot;code eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing cut labels from a previous call This value is returned from the previous call.  If a pagination token is provided the sortBy, filter, and asAt fields  must not have changed since the original request. |

### Return type

[PagedResourceListOfCutLabelDefinition](PagedResourceListOfCutLabelDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of cut labels |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCutLabelDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCutLabelDefinition> response = apiInstance.ListCutLabelDefinitionsWithHttpInfo(asAt, sortBy, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecutlabeldefinition"></a>
## UpdateCutLabelDefinition

> CutLabelDefinition UpdateCutLabelDefinition(string code, UpdateCutLabelDefinitionRequest? updateCutLabelDefinitionRequest = null)

UpdateCutLabelDefinition: Update a Cut Label

Update a specified cut label

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CutLabelDefinitionsApi>();
var code = "code_example";  // string
var updateCutLabelDefinitionRequest = new UpdateCutLabelDefinitionRequest?(); // UpdateCutLabelDefinitionRequest? (optional)
CutLabelDefinition result = apiInstance.UpdateCutLabelDefinition(code, updateCutLabelDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The Code of the Cut Label that is being updated |
| **updateCutLabelDefinitionRequest** | [UpdateCutLabelDefinitionRequest?](UpdateCutLabelDefinitionRequest?.md) | body | optional | The cut label update definition |

### Return type

[CutLabelDefinition](CutLabelDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cut label |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateCutLabelDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CutLabelDefinition> response = apiInstance.UpdateCutLabelDefinitionWithHttpInfo(code, updateCutLabelDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

