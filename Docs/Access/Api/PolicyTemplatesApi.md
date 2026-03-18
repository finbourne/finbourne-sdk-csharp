# Finbourne.Sdk.Access.Api.PolicyTemplatesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreatePolicyTemplate**](#createpolicytemplate) | **POST** `/access/api/policytemplates` | [EXPERIMENTAL] CreatePolicyTemplate: Create a Policy Template |
| [**DeletePolicyTemplate**](#deletepolicytemplate) | **DELETE** `/access/api/policytemplates/{code}` | [EXPERIMENTAL] DeletePolicyTemplate: Deleting a policy template |
| [**GeneratePolicyFromTemplate**](#generatepolicyfromtemplate) | **POST** `/access/api/policytemplates/$generatepolicy` | [EXPERIMENTAL] GeneratePolicyFromTemplate: Generate policy from template |
| [**GetPolicyTemplate**](#getpolicytemplate) | **GET** `/access/api/policytemplates/{code}` | [EXPERIMENTAL] GetPolicyTemplate: Retrieving one Policy Template |
| [**ListPolicyTemplates**](#listpolicytemplates) | **GET** `/access/api/policytemplates` | [EXPERIMENTAL] ListPolicyTemplates: List Policy Templates |
| [**UpdatePolicyTemplate**](#updatepolicytemplate) | **PUT** `/access/api/policytemplates/{code}` | [EXPERIMENTAL] UpdatePolicyTemplate: Update a Policy Template |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Access.Api;
using Finbourne.Sdk.Access.Client;
using Finbourne.Sdk.Access.Extensions;
using Finbourne.Sdk.Services.Access.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PolicyTemplatesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
```

---

<a id="createpolicytemplate"></a>
## CreatePolicyTemplate

> PolicyTemplateResponse CreatePolicyTemplate(PolicyTemplateCreationRequest policyTemplateCreationRequest)

[EXPERIMENTAL] CreatePolicyTemplate: Create a Policy Template

Creates a Policy Template

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
var policyTemplateCreationRequest = new PolicyTemplateCreationRequest(); // PolicyTemplateCreationRequest
PolicyTemplateResponse result = apiInstance.CreatePolicyTemplate(policyTemplateCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **policyTemplateCreationRequest** | [PolicyTemplateCreationRequest](PolicyTemplateCreationRequest.md) | body | **required** | The definition of the policy template |

### Return type

[PolicyTemplateResponse](PolicyTemplateResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created Policy Template |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePolicyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyTemplateResponse> response = apiInstance.CreatePolicyTemplateWithHttpInfo(policyTemplateCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepolicytemplate"></a>
## DeletePolicyTemplate

> void DeletePolicyTemplate(string code, string? scope = null)

[EXPERIMENTAL] DeletePolicyTemplate: Deleting a policy template

Deletes an identified Policy Template

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
apiInstance.DeletePolicyTemplate(code, scope);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Policy Template |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the Policy Template |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePolicyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeletePolicyTemplateWithHttpInfo(code, scope);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="generatepolicyfromtemplate"></a>
## GeneratePolicyFromTemplate

> GeneratedPolicyComponents GeneratePolicyFromTemplate(GeneratePolicyFromTemplateRequest generatePolicyFromTemplateRequest, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GeneratePolicyFromTemplate: Generate policy from template

Generates policies from templates

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
var generatePolicyFromTemplateRequest = new GeneratePolicyFromTemplateRequest(); // GeneratePolicyFromTemplateRequest
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GeneratedPolicyComponents result = apiInstance.GeneratePolicyFromTemplate(generatePolicyFromTemplateRequest, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **generatePolicyFromTemplateRequest** | [GeneratePolicyFromTemplateRequest](GeneratePolicyFromTemplateRequest.md) | body | **required** | Definition of the generate request |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date time of the data |

### Return type

[GeneratedPolicyComponents](GeneratedPolicyComponents.md)

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
<summary>Using the GeneratePolicyFromTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GeneratedPolicyComponents> response = apiInstance.GeneratePolicyFromTemplateWithHttpInfo(generatePolicyFromTemplateRequest, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpolicytemplate"></a>
## GetPolicyTemplate

> PolicyTemplateResponse GetPolicyTemplate(string code, DateTimeOffset? asAt = null, string? scope = null)

[EXPERIMENTAL] GetPolicyTemplate: Retrieving one Policy Template

Gets an identified Policy Template

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var scope = "scope_example";  // string? (optional)
PolicyTemplateResponse result = apiInstance.GetPolicyTemplate(code, asAt, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Policy Template |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date time of the data. If not specified defaults to current time |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the Policy Template |

### Return type

[PolicyTemplateResponse](PolicyTemplateResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get a specific Policy Template |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPolicyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyTemplateResponse> response = apiInstance.GetPolicyTemplateWithHttpInfo(code, asAt, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpolicytemplates"></a>
## ListPolicyTemplates

> ResourceListOfPolicyTemplateResponse ListPolicyTemplates(DateTimeOffset? asAt = null, string? sortBy = null, int? limit = null, string? filter = null, string? page = null)

[EXPERIMENTAL] ListPolicyTemplates: List Policy Templates

Gets all Policy Templates with pagination support.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
ResourceListOfPolicyTemplateResponse result = apiInstance.ListPolicyTemplates(asAt, sortBy, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date time of the data |
| **sortBy** | **string?** | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set |
| **page** | **string?** | query | optional | Optional. Paging token returned from a previous result |

### Return type

[ResourceListOfPolicyTemplateResponse](ResourceListOfPolicyTemplateResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Policy Templates |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPolicyTemplatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPolicyTemplateResponse> response = apiInstance.ListPolicyTemplatesWithHttpInfo(asAt, sortBy, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatepolicytemplate"></a>
## UpdatePolicyTemplate

> PolicyTemplateResponse UpdatePolicyTemplate(string code, PolicyTemplateUpdateRequest? policyTemplateUpdateRequest = null)

[EXPERIMENTAL] UpdatePolicyTemplate: Update a Policy Template

Updates an identified Policy Template

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PolicyTemplatesApi>();
var code = "code_example";  // string
var policyTemplateUpdateRequest = new PolicyTemplateUpdateRequest?(); // PolicyTemplateUpdateRequest? (optional)
PolicyTemplateResponse result = apiInstance.UpdatePolicyTemplate(code, policyTemplateUpdateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | Code of the policy template to update |
| **policyTemplateUpdateRequest** | [PolicyTemplateUpdateRequest?](PolicyTemplateUpdateRequest?.md) | body | optional | Definition of the updated policy template |

### Return type

[PolicyTemplateResponse](PolicyTemplateResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated Policy Template |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePolicyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyTemplateResponse> response = apiInstance.UpdatePolicyTemplateWithHttpInfo(code, policyTemplateUpdateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

