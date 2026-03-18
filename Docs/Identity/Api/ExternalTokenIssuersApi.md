# Finbourne.Sdk.Identity.Api.ExternalTokenIssuersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateExternalTokenIssuer**](#createexternaltokenissuer) | **POST** `/identity/api/externaltokenissuers` | [EARLY ACCESS] CreateExternalTokenIssuer: Create an External Token Issuer |
| [**DeleteExternalTokenIssuer**](#deleteexternaltokenissuer) | **DELETE** `/identity/api/externaltokenissuers/{code}` | [EARLY ACCESS] DeleteExternalTokenIssuer: Deletes an External Token Issuer by code |
| [**GetExternalTokenIssuer**](#getexternaltokenissuer) | **GET** `/identity/api/externaltokenissuers/{code}` | [EARLY ACCESS] GetExternalTokenIssuer: Gets an External Token Issuer with code |
| [**ListExternalTokenIssuers**](#listexternaltokenissuers) | **GET** `/identity/api/externaltokenissuers` | [EARLY ACCESS] ListExternalTokenIssuers: Lists all External Token Issuers for a domain |
| [**UpdateExternalTokenIssuer**](#updateexternaltokenissuer) | **PUT** `/identity/api/externaltokenissuers/{code}` | [EARLY ACCESS] UpdateExternalTokenIssuer: Updates an existing External Token Issuer |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ExternalTokenIssuersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExternalTokenIssuersApi>();
```

---

<a id="createexternaltokenissuer"></a>
## CreateExternalTokenIssuer

> ExternalTokenIssuerResponse CreateExternalTokenIssuer(CreateExternalTokenIssuerRequest createExternalTokenIssuerRequest)

[EARLY ACCESS] CreateExternalTokenIssuer: Create an External Token Issuer

Creates an External Token Issuer

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExternalTokenIssuersApi>();
var createExternalTokenIssuerRequest = new CreateExternalTokenIssuerRequest(); // CreateExternalTokenIssuerRequest
ExternalTokenIssuerResponse result = apiInstance.CreateExternalTokenIssuer(createExternalTokenIssuerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createExternalTokenIssuerRequest** | [CreateExternalTokenIssuerRequest](CreateExternalTokenIssuerRequest.md) | body | **required** |  |

### Return type

[ExternalTokenIssuerResponse](ExternalTokenIssuerResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Create External Token Issuer |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateExternalTokenIssuerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ExternalTokenIssuerResponse> response = apiInstance.CreateExternalTokenIssuerWithHttpInfo(createExternalTokenIssuerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteexternaltokenissuer"></a>
## DeleteExternalTokenIssuer

> void DeleteExternalTokenIssuer(string code)

[EARLY ACCESS] DeleteExternalTokenIssuer: Deletes an External Token Issuer by code

Deletes an External Token Issuer

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExternalTokenIssuersApi>();
var code = "code_example";  // string
apiInstance.DeleteExternalTokenIssuer(code);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | Identifier of the External Token Issuer to delete |

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
<summary>Using the DeleteExternalTokenIssuerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteExternalTokenIssuerWithHttpInfo(code);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getexternaltokenissuer"></a>
## GetExternalTokenIssuer

> ExternalTokenIssuerResponse GetExternalTokenIssuer(string code)

[EARLY ACCESS] GetExternalTokenIssuer: Gets an External Token Issuer with code

Gets an External Token Issuer

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExternalTokenIssuersApi>();
var code = "code_example";  // string
ExternalTokenIssuerResponse result = apiInstance.GetExternalTokenIssuer(code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | Identifier of the External Token Issuer |

### Return type

[ExternalTokenIssuerResponse](ExternalTokenIssuerResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get External Token Issuer |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetExternalTokenIssuerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ExternalTokenIssuerResponse> response = apiInstance.GetExternalTokenIssuerWithHttpInfo(code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listexternaltokenissuers"></a>
## ListExternalTokenIssuers

> List&lt;ExternalTokenIssuerResponse&gt; ListExternalTokenIssuers()

[EARLY ACCESS] ListExternalTokenIssuers: Lists all External Token Issuers for a domain

Lists all External Token Issuers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExternalTokenIssuersApi>();
List<ExternalTokenIssuerResponse> result = apiInstance.ListExternalTokenIssuers();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;ExternalTokenIssuerResponse&gt;](ExternalTokenIssuerResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List External Token Issuers |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListExternalTokenIssuersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<ExternalTokenIssuerResponse>> response = apiInstance.ListExternalTokenIssuersWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateexternaltokenissuer"></a>
## UpdateExternalTokenIssuer

> ExternalTokenIssuerResponse UpdateExternalTokenIssuer(string code, UpdateExternalTokenIssuerRequest updateExternalTokenIssuerRequest)

[EARLY ACCESS] UpdateExternalTokenIssuer: Updates an existing External Token Issuer

Updates an External Token Issuer

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ExternalTokenIssuersApi>();
var code = "code_example";  // string
var updateExternalTokenIssuerRequest = new UpdateExternalTokenIssuerRequest(); // UpdateExternalTokenIssuerRequest
ExternalTokenIssuerResponse result = apiInstance.UpdateExternalTokenIssuer(code, updateExternalTokenIssuerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | Identifier of the External Token Issuer to update |
| **updateExternalTokenIssuerRequest** | [UpdateExternalTokenIssuerRequest](UpdateExternalTokenIssuerRequest.md) | body | **required** |  |

### Return type

[ExternalTokenIssuerResponse](ExternalTokenIssuerResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update External Token Issuer |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateExternalTokenIssuerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ExternalTokenIssuerResponse> response = apiInstance.UpdateExternalTokenIssuerWithHttpInfo(code, updateExternalTokenIssuerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

