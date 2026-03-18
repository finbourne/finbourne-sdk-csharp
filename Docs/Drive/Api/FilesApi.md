# Finbourne.Sdk.Drive.Api.FilesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateFile**](#createfile) | **POST** `/drive/api/files` | CreateFile: Uploads a file to Lusid Drive. If using an SDK, consider using the UploadAsStreamAsync function for larger files instead. |
| [**DeleteFile**](#deletefile) | **DELETE** `/drive/api/files/{id}` | [EARLY ACCESS] DeleteFile: Deletes a file from Drive. |
| [**DownloadFile**](#downloadfile) | **GET** `/drive/api/files/{id}/contents` | DownloadFile: Download the file from Drive. |
| [**GetFile**](#getfile) | **GET** `/drive/api/files/{id}` | [EARLY ACCESS] GetFile: Get a file stored in Drive. |
| [**UpdateFileContents**](#updatefilecontents) | **PUT** `/drive/api/files/{id}/contents` | [EARLY ACCESS] UpdateFileContents: Updates contents of a file in Drive. |
| [**UpdateFileMetadata**](#updatefilemetadata) | **PUT** `/drive/api/files/{id}` | [EARLY ACCESS] UpdateFileMetadata: Updates metadata for a file in Drive. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Drive.Api;
using Finbourne.Sdk.Drive.Client;
using Finbourne.Sdk.Drive.Extensions;
using Finbourne.Sdk.Services.Drive.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FilesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
```

---

<a id="createfile"></a>
## CreateFile

> StorageObject CreateFile(string xLusidDriveFilename, string xLusidDrivePath, int contentLength, byte[] body)

CreateFile: Uploads a file to Lusid Drive. If using an SDK, consider using the UploadAsStreamAsync function for larger files instead.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
var xLusidDriveFilename = "xLusidDriveFilename_example";  // string
var xLusidDrivePath = "xLusidDrivePath_example";  // string
var contentLength = 56;  // int
var body = System.Text.Encoding.ASCII.GetBytes("BYTE_ARRAY_DATA_HERE");  // byte[]
StorageObject result = apiInstance.CreateFile(xLusidDriveFilename, xLusidDrivePath, contentLength, body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **xLusidDriveFilename** | **string** | header | **required** | File name. |
| **xLusidDrivePath** | **string** | header | **required** | File path. |
| **contentLength** | **int** | header | **required** | The size in bytes of the file to be uploaded |
| **body** | **byte[]** | body | **required** |  |

### Return type

[StorageObject](StorageObject.md)

### HTTP request headers

 - **Content-Type**: `application/octet-stream`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.CreateFileWithHttpInfo(xLusidDriveFilename, xLusidDrivePath, contentLength, body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletefile"></a>
## DeleteFile

> void DeleteFile(string id)

[EARLY ACCESS] DeleteFile: Deletes a file from Drive.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
var id = "id_example";  // string
apiInstance.DeleteFile(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Identifier of the file to be deleted. |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteFileWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="downloadfile"></a>
## DownloadFile

> System.IO.Stream DownloadFile(string id)

DownloadFile: Download the file from Drive.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
var id = "id_example";  // string
System.IO.Stream result = apiInstance.DownloadFile(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Identifier of the file to be downloaded. |

### Return type

**System.IO.Stream**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **410** | Malware detected, restricted from downloading file. |  -  |
| **423** | Virus scan in progress, restricted from downloading file. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DownloadFileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<System.IO.Stream> response = apiInstance.DownloadFileWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfile"></a>
## GetFile

> StorageObject GetFile(string id)

[EARLY ACCESS] GetFile: Get a file stored in Drive.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
var id = "id_example";  // string
StorageObject result = apiInstance.GetFile(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Identifier of the file to be retrieved. |

### Return type

[StorageObject](StorageObject.md)

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
<summary>Using the GetFileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.GetFileWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatefilecontents"></a>
## UpdateFileContents

> StorageObject UpdateFileContents(string id, int contentLength, byte[] body)

[EARLY ACCESS] UpdateFileContents: Updates contents of a file in Drive.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
var id = "id_example";  // string
var contentLength = 56;  // int
var body = System.Text.Encoding.ASCII.GetBytes("BYTE_ARRAY_DATA_HERE");  // byte[]
StorageObject result = apiInstance.UpdateFileContents(id, contentLength, body);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The unique file identifier |
| **contentLength** | **int** | header | **required** | The size in bytes of the file to be uploaded |
| **body** | **byte[]** | body | **required** |  |

### Return type

[StorageObject](StorageObject.md)

### HTTP request headers

 - **Content-Type**: `application/octet-stream`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateFileContentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.UpdateFileContentsWithHttpInfo(id, contentLength, body);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatefilemetadata"></a>
## UpdateFileMetadata

> StorageObject UpdateFileMetadata(string id, UpdateFile updateFile)

[EARLY ACCESS] UpdateFileMetadata: Updates metadata for a file in Drive.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FilesApi>();
var id = "id_example";  // string
var updateFile = new UpdateFile(); // UpdateFile
StorageObject result = apiInstance.UpdateFileMetadata(id, updateFile);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Identifier of the file to be updated |
| **updateFile** | [UpdateFile](UpdateFile.md) | body | **required** | Update to be applied to file |

### Return type

[StorageObject](StorageObject.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateFileMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.UpdateFileMetadataWithHttpInfo(id, updateFile);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

