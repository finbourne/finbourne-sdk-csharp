# Finbourne.Sdk.Identity.Api.RolesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddUserToRole**](#addusertorole) | **PUT** `/identity/api/roles/{id}/users/{userId}` | AddUserToRole: Add User to Role |
| [**CreateRole**](#createrole) | **POST** `/identity/api/roles` | CreateRole: Create Role |
| [**DeleteRole**](#deleterole) | **DELETE** `/identity/api/roles/{id}` | DeleteRole: Delete Role |
| [**GetRole**](#getrole) | **GET** `/identity/api/roles/{id}` | GetRole: Get Role |
| [**ListRoles**](#listroles) | **GET** `/identity/api/roles` | ListRoles: List Roles |
| [**ListUsersInRole**](#listusersinrole) | **GET** `/identity/api/roles/{id}/users` | ListUsersInRole: Get the users in the specified role. |
| [**RemoveUserFromRole**](#removeuserfromrole) | **DELETE** `/identity/api/roles/{id}/users/{userId}` | RemoveUserFromRole: Remove User from Role |
| [**UpdateRole**](#updaterole) | **PUT** `/identity/api/roles/{id}` | UpdateRole: Update Role |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Identity.Api;
using Finbourne.Sdk.Identity.Client;
using Finbourne.Sdk.Identity.Extensions;
using Finbourne.Sdk.Services.Identity.Model;
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

<a id="addusertorole"></a>
## AddUserToRole

> void AddUserToRole(string id, string userId)

AddUserToRole: Add User to Role

Adds the User to the specified Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var id = "id_example";  // string
var userId = "userId_example";  // string
apiInstance.AddUserToRole(id, userId);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the Role |
| **userId** | **string** | path | **required** | The unique identifier for the User |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **404** | Not Found |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddUserToRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.AddUserToRoleWithHttpInfo(id, userId);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createrole"></a>
## CreateRole

> RoleResponse CreateRole(CreateRoleRequest createRoleRequest)

CreateRole: Create Role

Creates a new Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var createRoleRequest = new CreateRoleRequest(); // CreateRoleRequest
RoleResponse result = apiInstance.CreateRole(createRoleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createRoleRequest** | [CreateRoleRequest](CreateRoleRequest.md) | body | **required** | Details of the role to be created |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Create a new role |  -  |
| **409** | A role with the same Name already exists. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.CreateRoleWithHttpInfo(createRoleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterole"></a>
## DeleteRole

> void DeleteRole(string id)

DeleteRole: Delete Role

Delete the specified role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var id = "id_example";  // string
apiInstance.DeleteRole(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the role |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

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
apiInstance.DeleteRoleWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrole"></a>
## GetRole

> RoleResponse GetRole(string id)

GetRole: Get Role

Get the specified role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var id = "id_example";  // string
RoleResponse result = apiInstance.GetRole(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the role |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get the specified role |  -  |
| **404** | Not Found |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.GetRoleWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listroles"></a>
## ListRoles

> List&lt;RoleResponse&gt; ListRoles()

ListRoles: List Roles

List the available Roles

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
List<RoleResponse> result = apiInstance.ListRoles();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;RoleResponse&gt;](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List the available roles |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRolesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<RoleResponse>> response = apiInstance.ListRolesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listusersinrole"></a>
## ListUsersInRole

> List&lt;UserResponse&gt; ListUsersInRole(string id)

ListUsersInRole: Get the users in the specified role.

List all Users in the specified Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var id = "id_example";  // string
List<UserResponse> result = apiInstance.ListUsersInRole(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the Role |

### Return type

[List&lt;UserResponse&gt;](UserResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The users in the role |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListUsersInRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<UserResponse>> response = apiInstance.ListUsersInRoleWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removeuserfromrole"></a>
## RemoveUserFromRole

> void RemoveUserFromRole(string id, string userId)

RemoveUserFromRole: Remove User from Role

Removes the User from the specified Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var id = "id_example";  // string
var userId = "userId_example";  // string
apiInstance.RemoveUserFromRole(id, userId);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the Role |
| **userId** | **string** | path | **required** | The unique identifier for the User |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **404** | Not Found |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemoveUserFromRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.RemoveUserFromRoleWithHttpInfo(id, userId);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updaterole"></a>
## UpdateRole

> RoleResponse UpdateRole(string id, UpdateRoleRequest? updateRoleRequest = null)

UpdateRole: Update Role

Update the specified Role

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RolesApi>();
var id = "id_example";  // string
var updateRoleRequest = new UpdateRoleRequest?(); // UpdateRoleRequest? (optional)
RoleResponse result = apiInstance.UpdateRole(id, updateRoleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the role to be updated |
| **updateRoleRequest** | [UpdateRoleRequest?](UpdateRoleRequest?.md) | body | optional | The new definition of the role |

### Return type

[RoleResponse](RoleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update a role |  -  |
| **404** | Not Found |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateRoleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<RoleResponse> response = apiInstance.UpdateRoleWithHttpInfo(id, updateRoleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

