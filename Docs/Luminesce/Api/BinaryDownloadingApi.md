# Finbourne.Sdk.Luminesce.Api.BinaryDownloadingApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DownloadBinary**](#downloadbinary) | **GET** `/honeycomb/api/Download/download` | DownloadBinary: Download a Luminesce Binary you may run on-site |
| [**GetBinaryVersions**](#getbinaryversions) | **GET** `/honeycomb/api/Download/versions` | GetBinaryVersions: List available versions of binaries |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<BinaryDownloadingApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BinaryDownloadingApi>();
```

---

<a id="downloadbinary"></a>
## DownloadBinary

> System.IO.Stream DownloadBinary(LuminesceBinaryType? type = null, string? version = null)

DownloadBinary: Download a Luminesce Binary you may run on-site

 Downloads the latest version (or specific if needs be) of the specified Luminesce Binary, given the required entitlements.  > This endpoint is an alternative to time-consuming manual distribution via Drive or Email. > it relies on an underlying datastore that is not quite as \"Highly Available\" to the degree  > that FINBOURNE services generally are.   > Thus it is not subject to the same SLAs as other API endpoints are. > *If you perceive an outage, please try again later.*  Once a file has been downloaded the following steps can be used to install it (for the dotnet tools at least):  (1) Open a terminal and cd to the directory you downloaded it to  (2) Install / extract files from that package via:  ``` dotnet tool install NameOfFileWithoutVersionNumberOrExtension -g - -add-source \".\" ``` e.g. ``` dotnet tool install Finbourne.Luminesce.DbProviders.Oracle_Snowflake -g - -add-source \".\" ``` More information on the installations can be found [here](https://support.lusid.com/docs/how-do-i-use-the-luminesce-cli).  (3) Execute them (see documentation for specific binary, e.g. [Sql.Db.Mine](https://support.lusid.com/docs/readwrite-to-sql-databases-sqldbmine) or [CLI](https://support.lusid.com/docs/how-do-i-use-the-luminesce-cli)).  The installed binaries can then be found in - Windows - `%USERPROFILE%\\.dotnet\\tools\\.store\\` - Linux/macOS - `$HOME/.dotnet/tools/.store/`  Note that the binaries all require the dotnet runtime to be installed. - `dotnet8` is required for all versions `1.18.X+` - `dotnet6` is required for all versions `1.17.X-` *Please upgrade if still running these*  The following error codes are to be anticipated with standard Problem Detail reports: - 400 BadRequest - binary file is not available for some reason (e.g. permissions or invalid version) - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BinaryDownloadingApi>();
var type = new LuminesceBinaryType?(); // LuminesceBinaryType? (optional)
var version = "version_example";  // string? (optional)
System.IO.Stream result = apiInstance.DownloadBinary(type, version);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | [LuminesceBinaryType?](LuminesceBinaryType?.md) | query | optional | Type of binary to download (each requires separate licenses and entitlements) |
| **version** | **string?** | query | optional | An explicit version of the binary.  Leave blank to get the latest version (recommended) |

### Return type

**System.IO.Stream**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/octet-stream`, `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The .nupkg or .msi file of the requested binary |  -  |
| **400** | Bad Request |  -  |
| **403** | Forbidden |  -  |

<details>
<summary>Using the DownloadBinaryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.DownloadBinaryWithHttpInfo(type, version);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbinaryversions"></a>
## GetBinaryVersions

> List&lt;string&gt; GetBinaryVersions(LuminesceBinaryType? type = null)

GetBinaryVersions: List available versions of binaries

 Gets all available versions of a given binary type (from newest to oldest) This does not mean you are entitled to download them.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BinaryDownloadingApi>();
var type = new LuminesceBinaryType?(); // LuminesceBinaryType? (optional)
List<string> result = apiInstance.GetBinaryVersions(type);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **type** | [LuminesceBinaryType?](LuminesceBinaryType?.md) | query | optional | Type of binary to fetch available versions of |

### Return type

**List<string>**

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
<summary>Using the GetBinaryVersionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<string>> response = apiInstance.GetBinaryVersionsWithHttpInfo(type);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

