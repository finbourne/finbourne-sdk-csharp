# Finbourne.Sdk.Identity.Api.IdentityProviderApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddScim**](#addscim) | **PUT** `/identity/api/identityprovider/scim` | AddScim: Add SCIM |
| [**RemoveScim**](#removescim) | **DELETE** `/identity/api/identityprovider/scim` | RemoveScim: Remove SCIM |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<IdentityProviderApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentityProviderApi>();
```

---

<a id="addscim"></a>
## AddScim

> AddScimResponse AddScim(string? apiTokenAction = null, DateTimeOffset? oldApiTokenDeactivation = null)

AddScim: Add SCIM

Generates an API token to be used for SCIM

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentityProviderApi>();
var apiTokenAction = "apiTokenAction_example";  // string? (optional)
var oldApiTokenDeactivation = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AddScimResponse result = apiInstance.AddScim(apiTokenAction, oldApiTokenDeactivation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **apiTokenAction** | **string?** | query | optional | The action to take. For the API token. Defaults to \&quot;ensure\&quot; |
| **oldApiTokenDeactivation** | **DateTimeOffset?** | query | optional | Optional deactivation date for the old API token. Only used if apiTokenAction is \&quot;regenerate\&quot; |

### Return type

[AddScimResponse](AddScimResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The base URL and API token to be used |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddScimWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AddScimResponse> response = apiInstance.AddScimWithHttpInfo(apiTokenAction, oldApiTokenDeactivation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removescim"></a>
## RemoveScim

> void RemoveScim()

RemoveScim: Remove SCIM

Deactivates any existing SCIM API token

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentityProviderApi>();
apiInstance.RemoveScim();
```

### Parameters
This endpoint does not need any parameter.

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemoveScimWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.RemoveScimWithHttpInfo();
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

