# Finbourne.Sdk.Drive.Api.FoldersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateFolder**](#createfolder) | **POST** `/drive/api/folders` | [EARLY ACCESS] CreateFolder: Create a new folder in LUSID Drive |
| [**DeleteFolder**](#deletefolder) | **DELETE** `/drive/api/folders/{id}` | [EARLY ACCESS] DeleteFolder: Delete a specified folder and all subfolders |
| [**GetFolder**](#getfolder) | **GET** `/drive/api/folders/{id}` | [EARLY ACCESS] GetFolder: Get metadata of folder |
| [**GetFolderContents**](#getfoldercontents) | **GET** `/drive/api/folders/{id}/contents` | GetFolderContents: List contents of a folder |
| [**GetRootFolder**](#getrootfolder) | **GET** `/drive/api/folders` | GetRootFolder: List contents of root folder |
| [**MoveFolder**](#movefolder) | **POST** `/drive/api/folders/{id}` | [EARLY ACCESS] MoveFolder: Move files to specified folder |
| [**UpdateFolder**](#updatefolder) | **PUT** `/drive/api/folders/{id}` | [EARLY ACCESS] UpdateFolder: Update an existing folder&#39;s name, path |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FoldersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
```

---

<a id="createfolder"></a>
## CreateFolder

> StorageObject CreateFolder(CreateFolder createFolder)

[EARLY ACCESS] CreateFolder: Create a new folder in LUSID Drive

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var createFolder = new CreateFolder(); // CreateFolder
StorageObject result = apiInstance.CreateFolder(createFolder);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createFolder** | [CreateFolder](CreateFolder.md) | body | **required** | A CreateFolder object that defines the name and path of the new folder |

### Return type

[StorageObject](StorageObject.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFolderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.CreateFolderWithHttpInfo(createFolder);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletefolder"></a>
## DeleteFolder

> void DeleteFolder(string id)

[EARLY ACCESS] DeleteFolder: Delete a specified folder and all subfolders

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var id = "id_example";  // string
apiInstance.DeleteFolder(id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique ID of the folder |

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
| **404** | No folder with this Id exists |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFolderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteFolderWithHttpInfo(id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfolder"></a>
## GetFolder

> StorageObject GetFolder(string id)

[EARLY ACCESS] GetFolder: Get metadata of folder

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var id = "id_example";  // string
StorageObject result = apiInstance.GetFolder(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique ID of the folder |

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
| **404** | No folder with this Id exists |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFolderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.GetFolderWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfoldercontents"></a>
## GetFolderContents

> PagedResourceListOfStorageObject GetFolderContents(string id, string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

GetFolderContents: List contents of a folder

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var id = "id_example";  // string
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 56;  // int? (optional)
var filter = "\"\"";  // string? (optional)
PagedResourceListOfStorageObject result = apiInstance.GetFolderContents(id, page, sortBy, start, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique ID of the folder |
| **page** | **string?** | query | optional | The pagination token to use to continue listing contents from a previous call to list contents.             This value is returned from the previous call. If a pagination token is provided the sortBy and filter fields             must not have changed since the original request. Also, if set, a start value cannot be provided. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order. |
| **start** | **int?** | query | optional | When paginating, skip this number of results. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Default: `&quot;&quot;` |

### Return type

[PagedResourceListOfStorageObject](PagedResourceListOfStorageObject.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No folder with this Id exists |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFolderContentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStorageObject> response = apiInstance.GetFolderContentsWithHttpInfo(id, page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getrootfolder"></a>
## GetRootFolder

> PagedResourceListOfStorageObject GetRootFolder(string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

GetRootFolder: List contents of root folder

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 56;  // int? (optional)
var filter = "\"true\"";  // string? (optional)
PagedResourceListOfStorageObject result = apiInstance.GetRootFolder(page, sortBy, start, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing contents from a previous call to list contents.             This value is returned from the previous call. If a pagination token is provided the sortBy and filter fields             must not have changed since the original request. Also, if set, a start value cannot be provided. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order. |
| **start** | **int?** | query | optional | When paginating, skip this number of results. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Default: `&quot;true&quot;` |

### Return type

[PagedResourceListOfStorageObject](PagedResourceListOfStorageObject.md)

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
<summary>Using the GetRootFolderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStorageObject> response = apiInstance.GetRootFolderWithHttpInfo(page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="movefolder"></a>
## MoveFolder

> PagedResourceListOfStorageObject MoveFolder(string id, List<string> requestBody, bool? overwrite = null, bool? deleteSource = null)

[EARLY ACCESS] MoveFolder: Move files to specified folder

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var id = "id_example";  // string
var requestBody = new List<string>(); // List<string>
var overwrite = false;  // bool? (optional)
var deleteSource = false;  // bool? (optional)
PagedResourceListOfStorageObject result = apiInstance.MoveFolder(id, requestBody, overwrite, deleteSource);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique ID of the folder where the files should be moved |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | Enumerable of unique IDs of files that should be moved |
| **overwrite** | **bool?** | query | optional | True if the destination has file with same name if should be overwritten Default: `false` |
| **deleteSource** | **bool?** | query | optional | If true after moving the original file is deleted Default: `false` |

### Return type

[PagedResourceListOfStorageObject](PagedResourceListOfStorageObject.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No folder or file with the supplied Id exists |  -  |
| **409** | There is already a file with the same name at this location |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the MoveFolderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStorageObject> response = apiInstance.MoveFolderWithHttpInfo(id, requestBody, overwrite, deleteSource);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatefolder"></a>
## UpdateFolder

> StorageObject UpdateFolder(string id, UpdateFolder updateFolder)

[EARLY ACCESS] UpdateFolder: Update an existing folder's name, path

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FoldersApi>();
var id = "id_example";  // string
var updateFolder = new UpdateFolder(); // UpdateFolder
StorageObject result = apiInstance.UpdateFolder(id, updateFolder);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | Unique ID of the folder |
| **updateFolder** | [UpdateFolder](UpdateFolder.md) | body | **required** | An UpdateFolder object that defines the new name or path of the folder |

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
| **404** | No folder with this Id exists |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateFolderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StorageObject> response = apiInstance.UpdateFolderWithHttpInfo(id, updateFolder);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

