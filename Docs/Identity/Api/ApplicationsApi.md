# Finbourne.Sdk.Identity.Api.ApplicationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateApplication**](#createapplication) | **POST** `/identity/api/applications` | [EARLY ACCESS] CreateApplication: Create Application |
| [**DeleteApplication**](#deleteapplication) | **DELETE** `/identity/api/applications/{id}` | [EARLY ACCESS] DeleteApplication: Delete Application |
| [**GetApplication**](#getapplication) | **GET** `/identity/api/applications/{id}` | GetApplication: Get Application |
| [**ListApplications**](#listapplications) | **GET** `/identity/api/applications` | ListApplications: List Applications |
| [**RotateApplicationSecrets**](#rotateapplicationsecrets) | **POST** `/identity/api/applications/{id}/lifecycle/$newsecret` | [EARLY ACCESS] RotateApplicationSecrets: Rotate Application Secrets |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ApplicationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationsApi>();
```

---

<a id="createapplication"></a>
## CreateApplication

> OAuthApplication CreateApplication(CreateApplicationRequest? createApplicationRequest = null)

[EARLY ACCESS] CreateApplication: Create Application

Create a new Application

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationsApi>();
var createApplicationRequest = new CreateApplicationRequest?(); // CreateApplicationRequest? (optional)
OAuthApplication result = apiInstance.CreateApplication(createApplicationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createApplicationRequest** | [CreateApplicationRequest?](CreateApplicationRequest?.md) | body | optional | Details of the application to be created |

### Return type

[OAuthApplication](OAuthApplication.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Create Application |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateApplicationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<OAuthApplication> response = apiInstance.CreateApplicationWithHttpInfo(createApplicationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteapplication"></a>
## DeleteApplication

> void DeleteApplication(string id)

[EARLY ACCESS] DeleteApplication: Delete Application

Delete the specified application

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationsApi>();
var id = "id_example";  // string
apiInstance.DeleteApplication(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the application |

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
<summary>Using the DeleteApplicationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteApplicationWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getapplication"></a>
## GetApplication

> OAuthApplication GetApplication(string id, bool? includeSecret = null)

GetApplication: Get Application

get the specified application, and optionally the OIDC secret

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationsApi>();
var id = "id_example";  // string
var includeSecret = true;  // bool? (optional)
OAuthApplication result = apiInstance.GetApplication(id, includeSecret);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the application |
| **includeSecret** | **bool?** | query | optional | Optional. If set to true, the application secrets will be returned in plain text |

### Return type

[OAuthApplication](OAuthApplication.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get the specified application |  -  |
| **404** | Not Found |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetApplicationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<OAuthApplication> response = apiInstance.GetApplicationWithHttpInfo(id, includeSecret);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listapplications"></a>
## ListApplications

> List&lt;OAuthApplication&gt; ListApplications()

ListApplications: List Applications

List the available applications

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationsApi>();
List<OAuthApplication> result = apiInstance.ListApplications();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;OAuthApplication&gt;](OAuthApplication.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List the available applications |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListApplicationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<OAuthApplication>> response = apiInstance.ListApplicationsWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="rotateapplicationsecrets"></a>
## RotateApplicationSecrets

> OAuthApplication RotateApplicationSecrets(string id)

[EARLY ACCESS] RotateApplicationSecrets: Rotate Application Secrets

Rotate the secrets for the specified application

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationsApi>();
var id = "id_example";  // string
OAuthApplication result = apiInstance.RotateApplicationSecrets(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique identifier for the application |

### Return type

[OAuthApplication](OAuthApplication.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Rotate Application Secrets |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RotateApplicationSecretsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<OAuthApplication> response = apiInstance.RotateApplicationSecretsWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

