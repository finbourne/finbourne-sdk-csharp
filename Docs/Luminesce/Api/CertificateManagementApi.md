# Finbourne.Sdk.Luminesce.Api.CertificateManagementApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DownloadCertificate**](#downloadcertificate) | **GET** `/honeycomb/api/Certificate/certificate` | DownloadCertificate: Download domain or your personal certificates |
| [**ListCertificates**](#listcertificates) | **GET** `/honeycomb/api/Certificate/certificates` | ListCertificates: List previously minted certificates |
| [**ManageCertificate**](#managecertificate) | **PUT** `/honeycomb/api/Certificate/manage` | ManageCertificate: Create / Renew / Revoke a certificate |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Luminesce.Api;
using Finbourne.Sdk.Luminesce.Client;
using Finbourne.Sdk.Luminesce.Extensions;
using Finbourne.Sdk.Services.Luminesce.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CertificateManagementApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CertificateManagementApi>();
```

---

<a id="downloadcertificate"></a>
## DownloadCertificate

> System.IO.Stream DownloadCertificate(CertificateType? type = null, CertificateFileType? fileType = null, bool? mayAutoCreate = null)

DownloadCertificate: Download domain or your personal certificates

 Downloads your latest Domain or your User certificate's public or private key - if any.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - certificate is not available for some reason - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CertificateManagementApi>();
var type = new CertificateType?(); // CertificateType? (optional)
var fileType = new CertificateFileType?(); // CertificateFileType? (optional)
var mayAutoCreate = false;  // bool? (optional)
System.IO.Stream result = apiInstance.DownloadCertificate(type, fileType, mayAutoCreate);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | [CertificateType?](CertificateType?.md) | query | optional | User or Domain level cert (Domain level requires additional entitlements) |
| **fileType** | [CertificateFileType?](CertificateFileType?.md) | query | optional | Should the public key or private key be downloaded? (both must be in place to run providers) |
| **mayAutoCreate** | **bool?** | query | optional | If no matching cert is available, should an attempt be made to Create/Renew it with default options? Default: `false` |

### Return type

**System.IO.Stream**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the DownloadCertificateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.DownloadCertificateWithHttpInfo(type, fileType, mayAutoCreate);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcertificates"></a>
## ListCertificates

> List&lt;CertificateState&gt; ListCertificates()

ListCertificates: List previously minted certificates

 Lists all the certificates previously minted to which you have access.  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CertificateManagementApi>();
List<CertificateState> result = apiInstance.ListCertificates();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;CertificateState&gt;](CertificateState.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the ListCertificatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<CertificateState>> response = apiInstance.ListCertificatesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="managecertificate"></a>
## ManageCertificate

> CertificateState ManageCertificate(CertificateAction? action = null, CertificateType? type = null, int? version = null, DateTimeOffset? validityStart = null, DateTimeOffset? validityEnd = null, bool? dryRun = null)

ManageCertificate: Create / Renew / Revoke a certificate

 Manages a certificate.  This could be creating a new one, renewing an old one or revoking one explicitly.  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - something about the request cannot be processed - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CertificateManagementApi>();
var action = new CertificateAction?(); // CertificateAction? (optional)
var type = new CertificateType?(); // CertificateType? (optional)
var version = 1;  // int? (optional)
var validityStart = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var validityEnd = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var dryRun = true;  // bool? (optional)
CertificateState result = apiInstance.ManageCertificate(action, type, version, validityStart, validityEnd, dryRun);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **action** | [CertificateAction?](CertificateAction?.md) | query | optional | The Action to perform, e.g. Create / Renew / Revoke |
| **type** | [CertificateType?](CertificateType?.md) | query | optional | User or Domain level cert (Domain level requires additional entitlements) |
| **version** | **int?** | query | optional | Version number of the cert, the request will fail to validate if incorrect Default: `1` |
| **validityStart** | **DateTimeOffset?** | query | optional | When should the cert first be valid (defaults to the current time in UTC) |
| **validityEnd** | **DateTimeOffset?** | query | optional | When should the cert no longer be valid (defaults to 13 months from now) |
| **dryRun** | **bool?** | query | optional | True will just validate the request, but perform no changes to any system Default: `true` |

### Return type

[CertificateState](CertificateState.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the ManageCertificateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CertificateState> response = apiInstance.ManageCertificateWithHttpInfo(action, type, version, validityStart, validityEnd, dryRun);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

