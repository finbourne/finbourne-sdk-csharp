# Finbourne.Sdk.Identity.Api.AuthenticationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetAuthenticationInformation**](#getauthenticationinformation) | **GET** `/identity/api/authentication/information` | GetAuthenticationInformation: Gets AuthenticationInformation |
| [**GetPasswordPolicy**](#getpasswordpolicy) | **GET** `/identity/api/authentication/password-policy/{userType}` | GetPasswordPolicy: Gets password policy for a user type |
| [**GetSupportAccessHistory**](#getsupportaccesshistory) | **GET** `/identity/api/authentication/support` | GetSupportAccessHistory: Get the history of all support access granted and any information pertaining to their termination |
| [**GetSupportRoles**](#getsupportroles) | **GET** `/identity/api/authentication/support-roles` | GetSupportRoles: Get mapping of support roles, the internal representation to a human friendly representation |
| [**GrantSupportAccess**](#grantsupportaccess) | **POST** `/identity/api/authentication/support` | GrantSupportAccess: Grants FINBOURNE support access to your account |
| [**InvalidateSupportAccess**](#invalidatesupportaccess) | **DELETE** `/identity/api/authentication/support` | InvalidateSupportAccess: Revoke any FINBOURNE support access to your account |
| [**UpdatePasswordPolicy**](#updatepasswordpolicy) | **PUT** `/identity/api/authentication/password-policy/{userType}` | UpdatePasswordPolicy: Updates password policy for a user type |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AuthenticationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
```

---

<a id="getauthenticationinformation"></a>
## GetAuthenticationInformation

> AuthenticationInformation GetAuthenticationInformation()

GetAuthenticationInformation: Gets AuthenticationInformation

Get the AuthenticationInformation associated with the current domain. This includes all the necessary information to login to this domain.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
AuthenticationInformation result = apiInstance.GetAuthenticationInformation();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[AuthenticationInformation](AuthenticationInformation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get authentication information |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAuthenticationInformationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AuthenticationInformation> response = apiInstance.GetAuthenticationInformationWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpasswordpolicy"></a>
## GetPasswordPolicy

> PasswordPolicyResponse GetPasswordPolicy(string userType)

GetPasswordPolicy: Gets password policy for a user type

Get the password policy for a given user type

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
var userType = "userType_example";  // string
PasswordPolicyResponse result = apiInstance.GetPasswordPolicy(userType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userType** | **string** | path | **required** | The type of user (should only be personal or service) |

### Return type

[PasswordPolicyResponse](PasswordPolicyResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get password policy |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPasswordPolicyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PasswordPolicyResponse> response = apiInstance.GetPasswordPolicyWithHttpInfo(userType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsupportaccesshistory"></a>
## GetSupportAccessHistory

> List&lt;SupportAccessResponse&gt; GetSupportAccessHistory(DateTimeOffset? start = null, DateTimeOffset? end = null)

GetSupportAccessHistory: Get the history of all support access granted and any information pertaining to their termination

The active and inactive support requests will be returned, inactive support requests will have information pertaining to their termination including obfuscated userIds of those who created and terminated the request

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
var start = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var end = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<SupportAccessResponse> result = apiInstance.GetSupportAccessHistory(start, end);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **start** | **DateTimeOffset?** | query | optional | The start expiry date to query support access requests from |
| **end** | **DateTimeOffset?** | query | optional | The end expiry date to query support access requests to |

### Return type

[List&lt;SupportAccessResponse&gt;](SupportAccessResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get support access history |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSupportAccessHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<SupportAccessResponse>> response = apiInstance.GetSupportAccessHistoryWithHttpInfo(start, end);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsupportroles"></a>
## GetSupportRoles

> SupportRolesResponse GetSupportRoles()

GetSupportRoles: Get mapping of support roles, the internal representation to a human friendly representation

Get mapping of support roles, the internal representation to a human friendly representation

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
SupportRolesResponse result = apiInstance.GetSupportRoles();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[SupportRolesResponse](SupportRolesResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get support roles |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSupportRolesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SupportRolesResponse> response = apiInstance.GetSupportRolesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="grantsupportaccess"></a>
## GrantSupportAccess

> SupportAccessResponse GrantSupportAccess(SupportAccessRequest supportAccessRequest)

GrantSupportAccess: Grants FINBOURNE support access to your account

Granting support access will allow FINBOURNE employees full access to your data with the express intent to investigate support issues You can revoke this (and all) access at any time using the InvalidateSupportAccess endpoint.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
var supportAccessRequest = new SupportAccessRequest(); // SupportAccessRequest
SupportAccessResponse result = apiInstance.GrantSupportAccess(supportAccessRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **supportAccessRequest** | [SupportAccessRequest](SupportAccessRequest.md) | body | **required** | Request detailing the duration and reasons for supplying support access |

### Return type

[SupportAccessResponse](SupportAccessResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Grant Support Access |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GrantSupportAccessWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SupportAccessResponse> response = apiInstance.GrantSupportAccessWithHttpInfo(supportAccessRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="invalidatesupportaccess"></a>
## InvalidateSupportAccess

> List&lt;SupportAccessResponse&gt; InvalidateSupportAccess()

InvalidateSupportAccess: Revoke any FINBOURNE support access to your account

This will result in a loss of access to your data for all FINBOURNE support agents

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
List<SupportAccessResponse> result = apiInstance.InvalidateSupportAccess();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;SupportAccessResponse&gt;](SupportAccessResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Invalidate all currently active support requests |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the InvalidateSupportAccessWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<SupportAccessResponse>> response = apiInstance.InvalidateSupportAccessWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatepasswordpolicy"></a>
## UpdatePasswordPolicy

> PasswordPolicyResponse UpdatePasswordPolicy(string userType, UpdatePasswordPolicyRequest? updatePasswordPolicyRequest = null)

UpdatePasswordPolicy: Updates password policy for a user type

Update the password policy for a given user type

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AuthenticationApi>();
var userType = "userType_example";  // string
var updatePasswordPolicyRequest = new UpdatePasswordPolicyRequest?(); // UpdatePasswordPolicyRequest? (optional)
PasswordPolicyResponse result = apiInstance.UpdatePasswordPolicy(userType, updatePasswordPolicyRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **userType** | **string** | path | **required** | The type of user (should only be personal or service) |
| **updatePasswordPolicyRequest** | [UpdatePasswordPolicyRequest?](UpdatePasswordPolicyRequest?.md) | body | optional | The password policy for the given user type |

### Return type

[PasswordPolicyResponse](PasswordPolicyResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update password policy |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePasswordPolicyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PasswordPolicyResponse> response = apiInstance.UpdatePasswordPolicyWithHttpInfo(userType, updatePasswordPolicyRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

