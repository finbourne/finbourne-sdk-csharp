# Finbourne.Sdk.Access.Api.UserRolesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddPolicyCollectionToUserRole**](#addpolicycollectiontouserrole) | **POST** `/access/api/userroles/{userid}/policycollections` | AddPolicyCollectionToUserRole: Add a policy collection to a user-role |
| [**AddPolicyToUserRole**](#addpolicytouserrole) | **POST** `/access/api/userroles/{userid}/policies` | AddPolicyToUserRole: Add a policy to a user-role |
| [**CreateUserRole**](#createuserrole) | **POST** `/access/api/userroles` | CreateUserRole: Create a user-role |
| [**DeleteUserRole**](#deleteuserrole) | **DELETE** `/access/api/userroles/{userid}` | DeleteUserRole: Delete a user-role |
| [**GetUserRole**](#getuserrole) | **GET** `/access/api/userroles/{userid}` | GetUserRole: Get a user-role |
| [**ListUserRoles**](#listuserroles) | **GET** `/access/api/userroles` | ListUserRoles: List user-roles |
| [**RemovePolicyCollectionFromUserRole**](#removepolicycollectionfromuserrole) | **DELETE** `/access/api/userroles/{userid}/policycollections/{policyCollectionScope}/{policyCollectionCode}` | RemovePolicyCollectionFromUserRole: Remove a policy collection from a user-role |
| [**RemovePolicyFromUserRole**](#removepolicyfromuserrole) | **DELETE** `/access/api/userroles/{userid}/policies/{policyScope}/{policyCode}` | RemovePolicyFromUserRole: Remove a policy from a user-role |
| [**UpdateUserRole**](#updateuserrole) | **POST** `/access/api/userroles/{userid}/update` | UpdateUserRole: Update a user-role |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<UserRolesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
```

---

<a id="addpolicycollectiontouserrole"></a>
## AddPolicyCollectionToUserRole

> UserRoleResponse AddPolicyCollectionToUserRole(string userid, AddPolicyCollectionToRoleRequest addPolicyCollectionToRoleRequest)

AddPolicyCollectionToUserRole: Add a policy collection to a user-role

Adds a policy collection to a user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
var addPolicyCollectionToRoleRequest = new AddPolicyCollectionToRoleRequest(); // AddPolicyCollectionToRoleRequest
UserRoleResponse result = apiInstance.AddPolicyCollectionToUserRole(userid, addPolicyCollectionToRoleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the User Role to get |
| **addPolicyCollectionToRoleRequest** | [AddPolicyCollectionToRoleRequest](AddPolicyCollectionToRoleRequest.md) | body | **required** | Dto of the policy collection to be added. |

### Return type

[UserRoleResponse](UserRoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User role with added policy collection. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddPolicyCollectionToUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserRoleResponse> response = apiInstance.AddPolicyCollectionToUserRoleWithHttpInfo(userid, addPolicyCollectionToRoleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="addpolicytouserrole"></a>
## AddPolicyToUserRole

> UserRoleResponse AddPolicyToUserRole(string userid, AddPolicyToRoleRequest addPolicyToRoleRequest)

AddPolicyToUserRole: Add a policy to a user-role

Adds a policy to a user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
var addPolicyToRoleRequest = new AddPolicyToRoleRequest(); // AddPolicyToRoleRequest
UserRoleResponse result = apiInstance.AddPolicyToUserRole(userid, addPolicyToRoleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the User Role to get |
| **addPolicyToRoleRequest** | [AddPolicyToRoleRequest](AddPolicyToRoleRequest.md) | body | **required** | Dto of the policy to be added. |

### Return type

[UserRoleResponse](UserRoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User role with added policy collection. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddPolicyToUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserRoleResponse> response = apiInstance.AddPolicyToUserRoleWithHttpInfo(userid, addPolicyToRoleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createuserrole"></a>
## CreateUserRole

> UserRoleResponse CreateUserRole(UserRoleCreationRequest userRoleCreationRequest)

CreateUserRole: Create a user-role

Creates a new user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userRoleCreationRequest = new UserRoleCreationRequest(); // UserRoleCreationRequest
UserRoleResponse result = apiInstance.CreateUserRole(userRoleCreationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userRoleCreationRequest** | [UserRoleCreationRequest](UserRoleCreationRequest.md) | body | **required** | Definition of the user-role to create. |

### Return type

[UserRoleResponse](UserRoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User role that has been created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserRoleResponse> response = apiInstance.CreateUserRoleWithHttpInfo(userRoleCreationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteuserrole"></a>
## DeleteUserRole

> void DeleteUserRole(string userid)

DeleteUserRole: Delete a user-role

Deletes an identified user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
apiInstance.DeleteUserRole(userid);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the user-role to delete. |

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
<summary>Using the DeleteUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteUserRoleWithHttpInfo(userid);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getuserrole"></a>
## GetUserRole

> UserRoleResponse GetUserRole(string userid)

GetUserRole: Get a user-role

Get an identified user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
UserRoleResponse result = apiInstance.GetUserRole(userid);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the user-role to get. |

### Return type

[UserRoleResponse](UserRoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested user role. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserRoleResponse> response = apiInstance.GetUserRoleWithHttpInfo(userid);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listuserroles"></a>
## ListUserRoles

> ResourceListOfUserRoleResponse ListUserRoles(string? filter = null, string? sortBy = null, int? limit = null, string? page = null)

ListUserRoles: List user-roles

Lists all user-roles and pages.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
ResourceListOfUserRoleResponse result = apiInstance.ListUserRoles(filter, sortBy, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set |
| **sortBy** | **string?** | query | optional | Optional. Order the results by these fields. Use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |
| **page** | **string?** | query | optional | Optional. Encoded page string returned from a previous search result that will retrieve             the next page of data. |

### Return type

[ResourceListOfUserRoleResponse](ResourceListOfUserRoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListUserRolesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfUserRoleResponse> response = apiInstance.ListUserRolesWithHttpInfo(filter, sortBy, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removepolicycollectionfromuserrole"></a>
## RemovePolicyCollectionFromUserRole

> void RemovePolicyCollectionFromUserRole(string userid, string policyCollectionScope, string policyCollectionCode)

RemovePolicyCollectionFromUserRole: Remove a policy collection from a user-role

Removes a policy collection from a user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
var policyCollectionScope = "policyCollectionScope_example";  // string
var policyCollectionCode = "policyCollectionCode_example";  // string
apiInstance.RemovePolicyCollectionFromUserRole(userid, policyCollectionScope, policyCollectionCode);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the User Role to get |
| **policyCollectionScope** | **string** | path | **required** | The scope of policy collection to remove from the User Role |
| **policyCollectionCode** | **string** | path | **required** | The code of the policy collection to remove from the User Role |

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
<summary>Using the RemovePolicyCollectionFromUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.RemovePolicyCollectionFromUserRoleWithHttpInfo(userid, policyCollectionScope, policyCollectionCode);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removepolicyfromuserrole"></a>
## RemovePolicyFromUserRole

> void RemovePolicyFromUserRole(string userid, string policyScope, string policyCode)

RemovePolicyFromUserRole: Remove a policy from a user-role

Removes a policy from a user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
var policyScope = "policyScope_example";  // string
var policyCode = "policyCode_example";  // string
apiInstance.RemovePolicyFromUserRole(userid, policyScope, policyCode);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the User Role to get |
| **policyScope** | **string** | path | **required** | The scope of the policy to remove from the User Role |
| **policyCode** | **string** | path | **required** | The code of the policy to remove from the User Role |

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
<summary>Using the RemovePolicyFromUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.RemovePolicyFromUserRoleWithHttpInfo(userid, policyScope, policyCode);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateuserrole"></a>
## UpdateUserRole

> UserRoleResponse UpdateUserRole(string userid, UserRoleUpdateRequest userRoleUpdateRequest)

UpdateUserRole: Update a user-role

Updates an identified user-role.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UserRolesApi>();
var userid = "userid_example";  // string
var userRoleUpdateRequest = new UserRoleUpdateRequest(); // UserRoleUpdateRequest
UserRoleResponse result = apiInstance.UpdateUserRole(userid, userRoleUpdateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userid** | **string** | path | **required** | Id of the user-role to be updated. |
| **userRoleUpdateRequest** | [UserRoleUpdateRequest](UserRoleUpdateRequest.md) | body | **required** | Definition of the update to apply to the user-role. |

### Return type

[UserRoleResponse](UserRoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User role that has been updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateUserRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserRoleResponse> response = apiInstance.UpdateUserRoleWithHttpInfo(userid, userRoleUpdateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

