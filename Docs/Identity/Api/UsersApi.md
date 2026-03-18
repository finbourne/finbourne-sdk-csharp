# Finbourne.Sdk.Identity.Api.UsersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateUser**](#createuser) | **POST** `/identity/api/users` | CreateUser: Create User |
| [**DeleteUser**](#deleteuser) | **DELETE** `/identity/api/users/{id}` | DeleteUser: Delete User |
| [**ExpirePassword**](#expirepassword) | **POST** `/identity/api/users/{id}/lifecycle/$expirepassword` | ExpirePassword: Reset the user&#39;s password to a temporary one |
| [**FindUsersById**](#findusersbyid) | **GET** `/identity/api/directory` | FindUsersById: Find users by id endpoint |
| [**GetUser**](#getuser) | **GET** `/identity/api/users/{id}` | GetUser: Get User |
| [**GetUserSchema**](#getuserschema) | **GET** `/identity/api/users/schema` | [EARLY ACCESS] GetUserSchema: Get User Schema |
| [**ListRunnableUsers**](#listrunnableusers) | **GET** `/identity/api/users/$runnable` | [EARLY ACCESS] ListRunnableUsers: List Runable Users |
| [**ListUsers**](#listusers) | **GET** `/identity/api/users` | ListUsers: List Users |
| [**ResetFactors**](#resetfactors) | **POST** `/identity/api/users/{id}/lifecycle/$resetfactors` | ResetFactors: Reset MFA factors |
| [**ResetPassword**](#resetpassword) | **POST** `/identity/api/users/{id}/lifecycle/$resetpassword` | ResetPassword: Reset Password |
| [**SendActivationEmail**](#sendactivationemail) | **POST** `/identity/api/users/{id}/lifecycle/$activate` | SendActivationEmail: Sends an activation email to the User |
| [**UnlockUser**](#unlockuser) | **POST** `/identity/api/users/{id}/lifecycle/$unlock` | UnlockUser: Unlock User |
| [**UnsuspendUser**](#unsuspenduser) | **POST** `/identity/api/users/{id}/lifecycle/$unsuspend` | [EXPERIMENTAL] UnsuspendUser: Unsuspend user |
| [**UpdateUser**](#updateuser) | **PUT** `/identity/api/users/{id}` | UpdateUser: Update User |
| [**UpdateUserSchema**](#updateuserschema) | **PUT** `/identity/api/users/schema` | [EARLY ACCESS] UpdateUserSchema: Update User Schema |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<UsersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
```

---

<a id="createuser"></a>
## CreateUser

> UserResponse CreateUser(CreateUserRequest createUserRequest, bool? waitForReindex = null)

CreateUser: Create User

Create a new User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var createUserRequest = new CreateUserRequest(); // CreateUserRequest
var waitForReindex = false;  // bool? (optional)
UserResponse result = apiInstance.CreateUser(createUserRequest, waitForReindex);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createUserRequest** | [CreateUserRequest](CreateUserRequest.md) | body | **required** | Details of the User to be created |
| **waitForReindex** | **bool?** | query | optional | Should the request wait until the newly created User is indexed (available in List) before returning Default: `false` |

### Return type

[UserResponse](UserResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Create a new user |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateUserWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserResponse> response = apiInstance.CreateUserWithHttpInfo(createUserRequest, waitForReindex);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteuser"></a>
## DeleteUser

> void DeleteUser(string id, bool? purge = null)

DeleteUser: Delete User

By default the user will be de-provisioned and inactive, however their record will remain in the identity provider for audit purposes. If this is not desirable and removal of all trace of the user is required, the purge parameter can be specified to indicate the details should be purged completely.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
var purge = true;  // bool? (optional)
apiInstance.DeleteUser(id, purge);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the user |
| **purge** | **bool?** | query | optional | Whether to purge any trace of the user from the identity provider (will affect audit) |

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
<summary>Using the DeleteUserWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteUserWithHttpInfo(id, purge);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="expirepassword"></a>
## ExpirePassword

> TemporaryPassword ExpirePassword(string id)

ExpirePassword: Reset the user's password to a temporary one

Resets the user's password to a temporary one which is then expired

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
TemporaryPassword result = apiInstance.ExpirePassword(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User having its password reset |

### Return type

[TemporaryPassword](TemporaryPassword.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reset the user&#39;s password |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ExpirePasswordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TemporaryPassword> response = apiInstance.ExpirePasswordWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="findusersbyid"></a>
## FindUsersById

> ListUsersResponse FindUsersById(List<string> id)

FindUsersById: Find users by id endpoint

Finds a maximum of 50 users by ID

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = new List<string>(); // List<string>
ListUsersResponse result = apiInstance.FindUsersById(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | [List&lt;string&gt;](string.md) | query | **required** | A list of unique identifiers for the users |

### Return type

[ListUsersResponse](ListUsersResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the FindUsersByIdWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ListUsersResponse> response = apiInstance.FindUsersByIdWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getuser"></a>
## GetUser

> UserResponse GetUser(string id, bool? includeRoles = null)

GetUser: Get User

Get the specified User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
var includeRoles = true;  // bool? (optional)
UserResponse result = apiInstance.GetUser(id, includeRoles);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User |
| **includeRoles** | **bool?** | query | optional | Flag indicating that the users roles should be included in the response |

### Return type

[UserResponse](UserResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get the specified user |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetUserWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserResponse> response = apiInstance.GetUserWithHttpInfo(id, includeRoles);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getuserschema"></a>
## GetUserSchema

> UserSchemaResponse GetUserSchema()

[EARLY ACCESS] GetUserSchema: Get User Schema

Get the User Schema

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
UserSchemaResponse result = apiInstance.GetUserSchema();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[UserSchemaResponse](UserSchemaResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update the User Schema |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetUserSchemaWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserSchemaResponse> response = apiInstance.GetUserSchemaWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrunnableusers"></a>
## ListRunnableUsers

> List&lt;UserResponse&gt; ListRunnableUsers()

[EARLY ACCESS] ListRunnableUsers: List Runable Users

List the available runnable Users

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
List<UserResponse> result = apiInstance.ListRunnableUsers();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;UserResponse&gt;](UserResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List the available runnable users |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRunnableUsersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<UserResponse>> response = apiInstance.ListRunnableUsersWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listusers"></a>
## ListUsers

> List&lt;UserResponse&gt; ListUsers(bool? includeDeactivated = null)

ListUsers: List Users

List the available Users

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var includeDeactivated = false;  // bool? (optional)
List<UserResponse> result = apiInstance.ListUsers(includeDeactivated);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **includeDeactivated** | **bool?** | query | optional | Include previously deleted (not purged) users Default: `false` |

### Return type

[List&lt;UserResponse&gt;](UserResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List the available users |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListUsersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<UserResponse>> response = apiInstance.ListUsersWithHttpInfo(includeDeactivated);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="resetfactors"></a>
## ResetFactors

> void ResetFactors(string id)

ResetFactors: Reset MFA factors

Resets the MFA factors of the specified User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
apiInstance.ResetFactors(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User having their MFA factors reset |

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
<summary>Using the ResetFactorsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.ResetFactorsWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="resetpassword"></a>
## ResetPassword

> void ResetPassword(string id)

ResetPassword: Reset Password

Resets the password of the specified User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
apiInstance.ResetPassword(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User having their password reset |

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
<summary>Using the ResetPasswordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.ResetPasswordWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="sendactivationemail"></a>
## SendActivationEmail

> void SendActivationEmail(string id)

SendActivationEmail: Sends an activation email to the User

Sends an activation email to the specified User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
apiInstance.SendActivationEmail(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User to be activated |

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
<summary>Using the SendActivationEmailWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.SendActivationEmailWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="unlockuser"></a>
## UnlockUser

> void UnlockUser(string id)

UnlockUser: Unlock User

Unlocks the specified User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
apiInstance.UnlockUser(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User to be unlocked |

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
<summary>Using the UnlockUserWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.UnlockUserWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="unsuspenduser"></a>
## UnsuspendUser

> void UnsuspendUser(string id)

[EXPERIMENTAL] UnsuspendUser: Unsuspend user

Unsuspend the user

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
apiInstance.UnsuspendUser(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User to Unsuspend |

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
<summary>Using the UnsuspendUserWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.UnsuspendUserWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateuser"></a>
## UpdateUser

> UserResponse UpdateUser(string id, UpdateUserRequest updateUserRequest)

UpdateUser: Update User

Updates the specified User

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var id = "id_example";  // string
var updateUserRequest = new UpdateUserRequest(); // UpdateUserRequest
UserResponse result = apiInstance.UpdateUser(id, updateUserRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the User to be updated |
| **updateUserRequest** | [UpdateUserRequest](UpdateUserRequest.md) | body | **required** | The new definition of the User |

### Return type

[UserResponse](UserResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update a user |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateUserWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserResponse> response = apiInstance.UpdateUserWithHttpInfo(id, updateUserRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateuserschema"></a>
## UpdateUserSchema

> UserSchemaResponse UpdateUserSchema(UpdateUserSchemaRequest updateUserSchemaRequest)

[EARLY ACCESS] UpdateUserSchema: Update User Schema

Update the User Schema

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<UsersApi>();
var updateUserSchemaRequest = new UpdateUserSchemaRequest(); // UpdateUserSchemaRequest
UserSchemaResponse result = apiInstance.UpdateUserSchema(updateUserSchemaRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **updateUserSchemaRequest** | [UpdateUserSchemaRequest](UpdateUserSchemaRequest.md) | body | **required** | The new User Schema |

### Return type

[UserSchemaResponse](UserSchemaResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update the User Schema |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateUserSchemaWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UserSchemaResponse> response = apiInstance.UpdateUserSchemaWithHttpInfo(updateUserSchemaRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

