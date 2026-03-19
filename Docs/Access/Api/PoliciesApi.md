# Finbourne.Sdk.Access.Api.PoliciesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddToPolicyCollection**](#addtopolicycollection) | **POST** `/access/api/policycollections/{code}/add` | AddToPolicyCollection: Add To PolicyCollection |
| [**CreatePolicy**](#createpolicy) | **POST** `/access/api/policies` | CreatePolicy: Create Policy |
| [**CreatePolicyCollection**](#createpolicycollection) | **POST** `/access/api/policycollections` | CreatePolicyCollection: Create PolicyCollection |
| [**DeletePolicy**](#deletepolicy) | **DELETE** `/access/api/policies/{code}` | DeletePolicy: Delete Policy |
| [**DeletePolicyCollection**](#deletepolicycollection) | **DELETE** `/access/api/policycollections/{code}` | DeletePolicyCollection: Delete PolicyCollection |
| [**Evaluate**](#evaluate) | **POST** `/access/api/me` | Evaluate: Run one or more evaluations |
| [**GetOwnPolicies**](#getownpolicies) | **GET** `/access/api/me` | GetOwnPolicies: Get policies of requesting user |
| [**GetPolicy**](#getpolicy) | **GET** `/access/api/policies/{code}` | GetPolicy: Get Policy |
| [**GetPolicyCollection**](#getpolicycollection) | **GET** `/access/api/policycollections/{code}` | GetPolicyCollection: Get PolicyCollection |
| [**ListPolicies**](#listpolicies) | **GET** `/access/api/policies` | ListPolicies: List Policies |
| [**ListPolicyCollections**](#listpolicycollections) | **GET** `/access/api/policycollections` | ListPolicyCollections: List PolicyCollections |
| [**PagePolicies**](#pagepolicies) | **GET** `/access/api/policies/page` | PagePolicies: Page Policies |
| [**PagePolicyCollections**](#pagepolicycollections) | **GET** `/access/api/policycollections/page` | PagePolicyCollections: Page PolicyCollections |
| [**RemoveFromPolicyCollection**](#removefrompolicycollection) | **POST** `/access/api/policycollections/{code}/remove` | RemoveFromPolicyCollection: Remove From PolicyCollection |
| [**UpdatePolicy**](#updatepolicy) | **PUT** `/access/api/policies/{code}` | UpdatePolicy: Update Policy |
| [**UpdatePolicyCollection**](#updatepolicycollection) | **PUT** `/access/api/policycollections/{code}` | UpdatePolicyCollection: Update PolicyCollection |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PoliciesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
```

---

<a id="addtopolicycollection"></a>
## AddToPolicyCollection

> PolicyCollectionResponse AddToPolicyCollection(string code, AddToPolicyCollectionRequest addToPolicyCollectionRequest, string? scope = null)

AddToPolicyCollection: Add To PolicyCollection

Add Policies and/or PolicyCollections to a PolicyCollection

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var addToPolicyCollectionRequest = new AddToPolicyCollectionRequest(); // AddToPolicyCollectionRequest
var scope = "scope_example";  // string? (optional)
PolicyCollectionResponse result = apiInstance.AddToPolicyCollection(code, addToPolicyCollectionRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the PolicyCollection |
| **addToPolicyCollectionRequest** | [AddToPolicyCollectionRequest](AddToPolicyCollectionRequest.md) | body | **required** | Ids of the PolicyCollections and/or Policies to add to the PolicyCollection |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the PolicyCollection |

### Return type

[PolicyCollectionResponse](PolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated PolicyCollection |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddToPolicyCollectionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyCollectionResponse> response = apiInstance.AddToPolicyCollectionWithHttpInfo(code, addToPolicyCollectionRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createpolicy"></a>
## CreatePolicy

> PolicyResponse CreatePolicy(PolicyCreationRequest policyCreationRequest)

CreatePolicy: Create Policy

Creates a Policy

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var policyCreationRequest = new PolicyCreationRequest(); // PolicyCreationRequest
PolicyResponse result = apiInstance.CreatePolicy(policyCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **policyCreationRequest** | [PolicyCreationRequest](PolicyCreationRequest.md) | body | **required** | The definition of the Policy |

### Return type

[PolicyResponse](PolicyResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created policy |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePolicyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyResponse> response = apiInstance.CreatePolicyWithHttpInfo(policyCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createpolicycollection"></a>
## CreatePolicyCollection

> PolicyCollectionResponse CreatePolicyCollection(PolicyCollectionCreationRequest policyCollectionCreationRequest)

CreatePolicyCollection: Create PolicyCollection

Creates a PolicyCollection

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var policyCollectionCreationRequest = new PolicyCollectionCreationRequest(); // PolicyCollectionCreationRequest
PolicyCollectionResponse result = apiInstance.CreatePolicyCollection(policyCollectionCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **policyCollectionCreationRequest** | [PolicyCollectionCreationRequest](PolicyCollectionCreationRequest.md) | body | **required** | The definition of the PolicyCollection |

### Return type

[PolicyCollectionResponse](PolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created PolicyCollection |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePolicyCollectionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyCollectionResponse> response = apiInstance.CreatePolicyCollectionWithHttpInfo(policyCollectionCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepolicy"></a>
## DeletePolicy

> void DeletePolicy(string code, string? scope = null)

DeletePolicy: Delete Policy

Deletes an identified Policy

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
apiInstance.DeletePolicy(code, scope);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Policy |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the Policy |

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
<summary>Using the DeletePolicyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeletePolicyWithHttpInfo(code, scope);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepolicycollection"></a>
## DeletePolicyCollection

> void DeletePolicyCollection(string code, string? scope = null)

DeletePolicyCollection: Delete PolicyCollection

Deletes an identified PolicyCollection

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
apiInstance.DeletePolicyCollection(code, scope);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the PolicyCollection |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the PolicyCollection |

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
<summary>Using the DeletePolicyCollectionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeletePolicyCollectionWithHttpInfo(code, scope);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="evaluate"></a>
## Evaluate

> Dictionary&lt;string, EvaluationResponse&gt; Evaluate(Dictionary<string, EvaluationRequest> requestBody, List<string>? applications = null)

Evaluate: Run one or more evaluations

Given a dictionary of evaluation requests (keyed by any arbitrary correlation identifier), each will be evaluated according to the current user's policies (deduced from the provided OAuth token).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var requestBody = new Dictionary<string, EvaluationRequest>(); // Dictionary<string, EvaluationRequest>
var applications = new List<string>?(); // List<string>? (optional)
Dictionary<string, EvaluationResponse> result = apiInstance.Evaluate(requestBody, applications);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, EvaluationRequest&gt;](EvaluationRequest.md) | body | **required** | A dictionary of evaluations, keyed using any arbitrary correlation id (it will be returned with the response for that evaluation). |
| **applications** | [List&lt;string&gt;?](string.md) | query | optional | Optional. The application type of the roles and policies to use when evaluating. |

### Return type

[Dictionary&lt;string, EvaluationResponse&gt;](EvaluationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Run an evaluation against the current user&#39;s entitlements |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the EvaluateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, EvaluationResponse>> response = apiInstance.EvaluateWithHttpInfo(requestBody, applications);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getownpolicies"></a>
## GetOwnPolicies

> List&lt;AttachedPolicyDefinitionResponse&gt; GetOwnPolicies(List<string>? applications = null)

GetOwnPolicies: Get policies of requesting user

Gets all Policies for the current user

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var applications = new List<string>?(); // List<string>? (optional)
List<AttachedPolicyDefinitionResponse> result = apiInstance.GetOwnPolicies(applications);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **applications** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Filter on the applications that the policies apply to |

### Return type

[List&lt;AttachedPolicyDefinitionResponse&gt;](AttachedPolicyDefinitionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get policies and licences of current user |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetOwnPoliciesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AttachedPolicyDefinitionResponse>> response = apiInstance.GetOwnPoliciesWithHttpInfo(applications);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpolicy"></a>
## GetPolicy

> PolicyResponse GetPolicy(string code, string? scope = null, DateTimeOffset? asAt = null)

GetPolicy: Get Policy

Gets an identified Policy

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PolicyResponse result = apiInstance.GetPolicy(code, scope, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Policy |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the Policy |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date and time at which to retrieve the Policy. Defaults to returning the latest version |

### Return type

[PolicyResponse](PolicyResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get a specific Policy |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPolicyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyResponse> response = apiInstance.GetPolicyWithHttpInfo(code, scope, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpolicycollection"></a>
## GetPolicyCollection

> PolicyCollectionResponse GetPolicyCollection(string code, string? scope = null)

GetPolicyCollection: Get PolicyCollection

Gets an identified PolicyCollection

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
PolicyCollectionResponse result = apiInstance.GetPolicyCollection(code, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the PolicyCollection |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the PolicyCollection |

### Return type

[PolicyCollectionResponse](PolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested PolicyCollection |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPolicyCollectionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyCollectionResponse> response = apiInstance.GetPolicyCollectionWithHttpInfo(code, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpolicies"></a>
## ListPolicies

> List&lt;PolicyResponse&gt; ListPolicies(string? scope = null)

ListPolicies: List Policies

Gets all Policies in a scope. For pagination support, use PagePolicies.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var scope = "scope_example";  // string? (optional)
List<PolicyResponse> result = apiInstance.ListPolicies(scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The requested scope |

### Return type

[List&lt;PolicyResponse&gt;](PolicyResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Policies |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPoliciesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<PolicyResponse>> response = apiInstance.ListPoliciesWithHttpInfo(scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpolicycollections"></a>
## ListPolicyCollections

> List&lt;PolicyCollectionResponse&gt; ListPolicyCollections(string? scope = null)

ListPolicyCollections: List PolicyCollections

Gets all PolicyCollections in a scope. For pagination support, use PagePolicyCollections

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var scope = "scope_example";  // string? (optional)
List<PolicyCollectionResponse> result = apiInstance.ListPolicyCollections(scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The requested scope |

### Return type

[List&lt;PolicyCollectionResponse&gt;](PolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested list of PolicyCollections |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPolicyCollectionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<PolicyCollectionResponse>> response = apiInstance.ListPolicyCollectionsWithHttpInfo(scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="pagepolicies"></a>
## PagePolicies

> ResourceListOfPolicyResponse PagePolicies(string? sortBy = null, int? limit = null, string? filter = null, string? page = null)

PagePolicies: Page Policies

Gets all Policies with pagination support.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
ResourceListOfPolicyResponse result = apiInstance.PagePolicies(sortBy, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sortBy** | **string?** | query | optional | Optional. Order the results by these fields. Use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. 2000 if not provided. When paginating, limit the number of returned results to this many |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set |
| **page** | **string?** | query | optional | Optional. Paging token returned from a previous result |

### Return type

[ResourceListOfPolicyResponse](ResourceListOfPolicyResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested list of Policies |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PagePoliciesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPolicyResponse> response = apiInstance.PagePoliciesWithHttpInfo(sortBy, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="pagepolicycollections"></a>
## PagePolicyCollections

> ResourceListOfPolicyCollectionResponse PagePolicyCollections(string? sortBy = null, int? limit = null, string? filter = null, string? page = null)

PagePolicyCollections: Page PolicyCollections

Gets all PolicyCollections with pagination support.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
ResourceListOfPolicyCollectionResponse result = apiInstance.PagePolicyCollections(sortBy, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sortBy** | **string?** | query | optional | Optional. Order the results by these fields. Use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. 2000 if not provided. When paginating, limit the number of returned results to this many |
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set |
| **page** | **string?** | query | optional | Optional. Paging token returned from a previous result |

### Return type

[ResourceListOfPolicyCollectionResponse](ResourceListOfPolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested list of PolicyCollections |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PagePolicyCollectionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPolicyCollectionResponse> response = apiInstance.PagePolicyCollectionsWithHttpInfo(sortBy, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removefrompolicycollection"></a>
## RemoveFromPolicyCollection

> PolicyCollectionResponse RemoveFromPolicyCollection(string code, RemoveFromPolicyCollectionRequest removeFromPolicyCollectionRequest, string? scope = null)

RemoveFromPolicyCollection: Remove From PolicyCollection

Remove Policies and/or PolicyCollections from a PolicyCollection

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var removeFromPolicyCollectionRequest = new RemoveFromPolicyCollectionRequest(); // RemoveFromPolicyCollectionRequest
var scope = "scope_example";  // string? (optional)
PolicyCollectionResponse result = apiInstance.RemoveFromPolicyCollection(code, removeFromPolicyCollectionRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the PolicyCollection |
| **removeFromPolicyCollectionRequest** | [RemoveFromPolicyCollectionRequest](RemoveFromPolicyCollectionRequest.md) | body | **required** | Ids of the PolicyCollections and/or Policies to remove from the PolicyCollection |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the PolicyCollection |

### Return type

[PolicyCollectionResponse](PolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated PolicyCollection |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemoveFromPolicyCollectionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyCollectionResponse> response = apiInstance.RemoveFromPolicyCollectionWithHttpInfo(code, removeFromPolicyCollectionRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatepolicy"></a>
## UpdatePolicy

> PolicyResponse UpdatePolicy(string code, PolicyUpdateRequest policyUpdateRequest, string? scope = null)

UpdatePolicy: Update Policy

Updates a Policy

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var policyUpdateRequest = new PolicyUpdateRequest(); // PolicyUpdateRequest
var scope = "scope_example";  // string? (optional)
PolicyResponse result = apiInstance.UpdatePolicy(code, policyUpdateRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Policy |
| **policyUpdateRequest** | [PolicyUpdateRequest](PolicyUpdateRequest.md) | body | **required** | The updated definition of the Policy |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the Policy |

### Return type

[PolicyResponse](PolicyResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated policy |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePolicyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyResponse> response = apiInstance.UpdatePolicyWithHttpInfo(code, policyUpdateRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatepolicycollection"></a>
## UpdatePolicyCollection

> PolicyCollectionResponse UpdatePolicyCollection(string code, PolicyCollectionUpdateRequest policyCollectionUpdateRequest, string? scope = null)

UpdatePolicyCollection: Update PolicyCollection

Updates a PolicyCollection

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PoliciesApi>();
var code = "code_example";  // string
var policyCollectionUpdateRequest = new PolicyCollectionUpdateRequest(); // PolicyCollectionUpdateRequest
var scope = "scope_example";  // string? (optional)
PolicyCollectionResponse result = apiInstance.UpdatePolicyCollection(code, policyCollectionUpdateRequest, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the PolicyCollection |
| **policyCollectionUpdateRequest** | [PolicyCollectionUpdateRequest](PolicyCollectionUpdateRequest.md) | body | **required** | The updated definition of the PolicyCollection |
| **scope** | **string?** | query | optional | Optional. Will use the default scope if not provided. The scope of the PolicyCollection |

### Return type

[PolicyCollectionResponse](PolicyCollectionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated PolicyCollection |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePolicyCollectionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PolicyCollectionResponse> response = apiInstance.UpdatePolicyCollectionWithHttpInfo(code, policyCollectionUpdateRequest, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

