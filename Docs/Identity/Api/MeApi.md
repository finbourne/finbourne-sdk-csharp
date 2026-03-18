# Finbourne.Sdk.Identity.Api.MeApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetUserInfo**](#getuserinfo) | **GET** `/identity/api/me` | GetUserInfo: Get User Info |
| [**SetPassword**](#setpassword) | **PUT** `/identity/api/me/password` | SetPassword: Set password of current user |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<MeApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MeApi>();
```

---

<a id="getuserinfo"></a>
## GetUserInfo

> CurrentUserResponse GetUserInfo()

GetUserInfo: Get User Info

Get the requesting user's basic info

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MeApi>();
CurrentUserResponse result = apiInstance.GetUserInfo();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[CurrentUserResponse](CurrentUserResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get the specified user&#39;s info |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetUserInfoWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CurrentUserResponse> response = apiInstance.GetUserInfoWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setpassword"></a>
## SetPassword

> SetPasswordResponse SetPassword(SetPassword setPassword)

SetPassword: Set password of current user

Set the password of the current user to the specified value.              Note this is feature is only available to Service users authenticated using OpenID. For further information relating to usage of this feature please consult the documentation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MeApi>();
var setPassword = new SetPassword(); // SetPassword
SetPasswordResponse result = apiInstance.SetPassword(setPassword);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **setPassword** | [SetPassword](SetPassword.md) | body | **required** | The request containing the new password value |

### Return type

[SetPasswordResponse](SetPasswordResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Set the current user&#39;s password |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPasswordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SetPasswordResponse> response = apiInstance.SetPasswordWithHttpInfo(setPassword);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

