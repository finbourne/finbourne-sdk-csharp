# Finbourne.Sdk.Lusid.Api.ApplicationMetadataApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetExcelAddin**](#getexceladdin) | **GET** `/api/api/metadata/downloads/exceladdin` | GetExcelAddin: Download Excel Addin |
| [**GetLusidVersions**](#getlusidversions) | **GET** `/api/api/metadata/versions` | GetLusidVersions: Get LUSID versions |
| [**ListAccessControlledResources**](#listaccesscontrolledresources) | **GET** `/api/api/metadata/access/resources` | ListAccessControlledResources: Get resources available for access control |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Lusid.Api;
using Finbourne.Sdk.Lusid.Client;
using Finbourne.Sdk.Lusid.Extensions;
using Finbourne.Sdk.Services.Lusid.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ApplicationMetadataApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationMetadataApi>();
```

---

<a id="getexceladdin"></a>
## GetExcelAddin

> FileResponse GetExcelAddin(string? version = null)

GetExcelAddin: Download Excel Addin

Download the LUSID Excel Addin for Microsoft Excel. Not providing a specific value will return the latest version being returned

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationMetadataApi>();
var version = "version_example";  // string? (optional)
FileResponse result = apiInstance.GetExcelAddin(version);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **version** | **string?** | query | optional | The requested version of the Excel plugin |

### Return type

[FileResponse](FileResponse.md)

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
<summary>Using the GetExcelAddinWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FileResponse> response = apiInstance.GetExcelAddinWithHttpInfo(version);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlusidversions"></a>
## GetLusidVersions

> VersionSummaryDto GetLusidVersions()

GetLusidVersions: Get LUSID versions

Get the semantic versions associated with LUSID and its ecosystem

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationMetadataApi>();
VersionSummaryDto result = apiInstance.GetLusidVersions();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[VersionSummaryDto](VersionSummaryDto.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Collection of versions associated with LUSID |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLusidVersionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionSummaryDto> response = apiInstance.GetLusidVersionsWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listaccesscontrolledresources"></a>
## ListAccessControlledResources

> ResourceListOfAccessControlledResource ListAccessControlledResources(string? filter = null)

ListAccessControlledResources: Get resources available for access control

Get the comprehensive set of resources that are available for access control

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationMetadataApi>();
var filter = "filter_example";  // string? (optional)
ResourceListOfAccessControlledResource result = apiInstance.ListAccessControlledResources(filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Optional. Expression to filter the result set.               For example, to filter on the Application, use \&quot;application eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfAccessControlledResource](ResourceListOfAccessControlledResource.md)

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
<summary>Using the ListAccessControlledResourcesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAccessControlledResource> response = apiInstance.ListAccessControlledResourcesWithHttpInfo(filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

