# Finbourne.Sdk.Access.Api.RolesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddPolicyCollectionToRole**](#addpolicycollectiontorole) | **POST** `/access/api/roles/{scope}/{code}/policycollections` | AddPolicyCollectionToRole: Add policy collections to a role |
| [**CreateRole**](#createrole) | **POST** `/access/api/roles` | CreateRole: Create Role |
| [**DeleteRole**](#deleterole) | **DELETE** `/access/api/roles/{code}` | DeleteRole: Delete Role |
| [**GetRole**](#getrole) | **GET** `/access/api/roles/{code}` | GetRole: Get Role |
| [**ListRoles**](#listroles) | **GET** `/access/api/roles` | ListRoles: List Roles |
| [**RemovePolicyCollectionFromRole**](#removepolicycollectionfromrole) | **DELETE** `/access/api/roles/{scope}/{code}/policycollections/{policycollectionscope}/{policycollectioncode}` | RemovePolicyCollectionFromRole: Remove policy collection from role |
| [**UpdateRole**](#updaterole) | **PUT** `/access/api/roles/{code}` | UpdateRole: Update Role |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RolesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
```

---

<a id="addpolicycollectiontorole"></a>
## AddPolicyCollectionToRole

> RoleResponse AddPolicyCollectionToRole(string scope, string code, AddPolicyCollectionToRoleRequest addPolicyCollectionToRoleRequest)

AddPolicyCollectionToRole: Add policy collections to a role

Assigns policy collections to a role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var addPolicyCollectionToRoleRequest = new AddPolicyCollectionToRoleRequest(); // AddPolicyCollectionToRoleRequest
RoleResponse result = apiInstance.AddPolicyCollectionToRole(scope, code, addPolicyCollectionToRoleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Role |
| **code** | **string** | path | **required** | The code of the Role |
| **addPolicyCollectionToRoleRequest** | [AddPolicyCollectionToRoleRequest](AddPolicyCollectionToRoleRequest.md) | body | **required** | The policy collections to add |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AddPolicyCollectionToRole |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddPolicyCollectionToRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.AddPolicyCollectionToRoleWithHttpInfo(scope, code, addPolicyCollectionToRoleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createrole"></a>
## CreateRole

> RoleResponse CreateRole(RoleCreationRequest roleCreationRequest)

CreateRole: Create Role

Creates a Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var roleCreationRequest = new RoleCreationRequest(); // RoleCreationRequest
RoleResponse result = apiInstance.CreateRole(roleCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **roleCreationRequest** | [RoleCreationRequest](RoleCreationRequest.md) | body | **required** | The definition of the Role |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created Role |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.CreateRoleWithHttpInfo(roleCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterole"></a>
## DeleteRole

> void DeleteRole(string code, string? scope = null)

DeleteRole: Delete Role

Deletes an identified Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
apiInstance.DeleteRole(code, scope);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Role |
| **scope** | **string?** | query | optional | &gt;Optional. Will use default scope if not supplied. The scope of the Role |

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
<summary>Using the DeleteRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteRoleWithHttpInfo(code, scope);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrole"></a>
## GetRole

> RoleResponse GetRole(string code, string? scope = null)

GetRole: Get Role

Gets an identified Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var code = "code_example";  // string
var scope = "scope_example";  // string? (optional)
RoleResponse result = apiInstance.GetRole(code, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Role |
| **scope** | **string?** | query | optional | Optional. Will use default scope if not supplied. The scope of the Role |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested Role |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.GetRoleWithHttpInfo(code, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listroles"></a>
## ListRoles

> List&lt;RoleResponse&gt; ListRoles(string? scope = null)

ListRoles: List Roles

Gets all Roles in a scope

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var scope = "scope_example";  // string? (optional)
List<RoleResponse> result = apiInstance.ListRoles(scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string?** | query | optional | Optional. Will use all scopes if not supplied. The requested scope |

### Return type

[List&lt;RoleResponse&gt;](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Roles |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRolesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<RoleResponse>> response = apiInstance.ListRolesWithHttpInfo(scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removepolicycollectionfromrole"></a>
## RemovePolicyCollectionFromRole

> RoleResponse RemovePolicyCollectionFromRole(string scope, string code, string policycollectionscope, string policycollectioncode)

RemovePolicyCollectionFromRole: Remove policy collection from role

Removes a policy collection from a role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var policycollectionscope = "policycollectionscope_example";  // string
var policycollectioncode = "policycollectioncode_example";  // string
RoleResponse result = apiInstance.RemovePolicyCollectionFromRole(scope, code, policycollectionscope, policycollectioncode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Role |
| **code** | **string** | path | **required** | The code of the Role |
| **policycollectionscope** | **string** | path | **required** | The scope of policy collection to remove from the Role |
| **policycollectioncode** | **string** | path | **required** | The code of the policy collection to remove from the Role |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | RemovePolicyCollectionFromRole |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemovePolicyCollectionFromRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.RemovePolicyCollectionFromRoleWithHttpInfo(scope, code, policycollectionscope, policycollectioncode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterole"></a>
## UpdateRole

> RoleResponse UpdateRole(string code, RoleUpdateRequest roleUpdateRequest, string? scope = null, string? beforeScope = null, string? beforeCode = null, string? afterScope = null, string? afterCode = null)

UpdateRole: Update Role

Updates a Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var code = "code_example";  // string
var roleUpdateRequest = new RoleUpdateRequest(); // RoleUpdateRequest
var scope = "scope_example";  // string? (optional)
var beforeScope = "beforeScope_example";  // string? (optional)
var beforeCode = "beforeCode_example";  // string? (optional)
var afterScope = "afterScope_example";  // string? (optional)
var afterCode = "afterCode_example";  // string? (optional)
RoleResponse result = apiInstance.UpdateRole(code, roleUpdateRequest, scope, beforeScope, beforeCode, afterScope, afterCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The code of the Role |
| **roleUpdateRequest** | [RoleUpdateRequest](RoleUpdateRequest.md) | body | **required** | The updated definition of the Role |
| **scope** | **string?** | query | optional | &gt;Optional. Will use default scope if not supplied. The scope of the Role |
| **beforeScope** | **string?** | query | optional | Optional. The scope of the Role. Will use default scope if not supplied. |
| **beforeCode** | **string?** | query | optional | Optional. The code of the Role |
| **afterScope** | **string?** | query | optional | Optional. The scope of the Role. Will use default scope if not supplied. |
| **afterCode** | **string?** | query | optional | Optional. The code of the Role |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated Role |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.UpdateRoleWithHttpInfo(code, roleUpdateRequest, scope, beforeScope, beforeCode, afterScope, afterCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

