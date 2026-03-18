# Finbourne.Sdk.Scheduler.Api.ImagesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetImage**](#getimage) | **GET** `/scheduler2/api/images/{name}` | GetImage: Get metadata of a Docker Image |
| [**ListImages**](#listimages) | **GET** `/scheduler2/api/images/repository/{name}` | ListImages: List all images under same image repository |
| [**ListRepositories**](#listrepositories) | **GET** `/scheduler2/api/images/repository` | ListRepositories: List all Docker image repositories |
| [**UploadImage**](#uploadimage) | **POST** `/scheduler2/api/images` | UploadImage: Upload a Docker Image used for Scheduler jobs |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Scheduler.Api;
using Finbourne.Sdk.Scheduler.Client;
using Finbourne.Sdk.Scheduler.Extensions;
using Finbourne.Sdk.Services.Scheduler.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ImagesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ImagesApi>();
```

---

<a id="getimage"></a>
## GetImage

> Image GetImage(string name)

GetImage: Get metadata of a Docker Image

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ImagesApi>();
var name = "name_example";  // string
Image result = apiInstance.GetImage(name);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **name** | **string** | path | **required** | The name and tag of a Docker image. Format \&quot;ExampleImageName:latest\&quot; |

### Return type

[Image](Image.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetImageWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Image> response = apiInstance.GetImageWithHttpInfo(name);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listimages"></a>
## ListImages

> ResourceListOfImageSummary ListImages(string name, string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

ListImages: List all images under same image repository

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ImagesApi>();
var name = "name_example";  // string
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 2000;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfImageSummary result = apiInstance.ListImages(name, page, sortBy, start, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **name** | **string** | path | **required** | The name of the Repository |
| **page** | **string?** | query | optional | The pagination token to use to continue listing images from a previous call to list images.             This value is returned from the previous call. If a pagination token is provided the sortBy and filter fields             must not have changed since the original request. Also, if set, a start value cannot be provided. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. |
| **start** | **int?** | query | optional | When paginating, skip this number of results. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 2000 if not specified. Maximum is 5000. Default: `2000` |
| **filter** | **string?** | query | optional | Expression to filter the result set. |

### Return type

[ResourceListOfImageSummary](ResourceListOfImageSummary.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListImagesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfImageSummary> response = apiInstance.ListImagesWithHttpInfo(name, page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrepositories"></a>
## ListRepositories

> ResourceListOfRepository ListRepositories(string? page = null, List<string>? sortBy = null, int? start = null, int? limit = null, string? filter = null)

ListRepositories: List all Docker image repositories

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ImagesApi>();
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var start = 56;  // int? (optional)
var limit = 2000;  // int? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfRepository result = apiInstance.ListRepositories(page, sortBy, start, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing images from a previous call to list images.             This value is returned from the previous call. If a pagination token is provided the sortBy and filter fields             must not have changed since the original request. Also, if set, a start value cannot be provided. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. |
| **start** | **int?** | query | optional | When paginating, skip this number of results. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 2000 if not specified. Maximum is 5000. Default: `2000` |
| **filter** | **string?** | query | optional | Expression to filter the result set. |

### Return type

[ResourceListOfRepository](ResourceListOfRepository.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRepositoriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRepository> response = apiInstance.ListRepositoriesWithHttpInfo(page, sortBy, start, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="uploadimage"></a>
## UploadImage

> UploadImageInstructions UploadImage(UploadImageRequest uploadImageRequest)

UploadImage: Upload a Docker Image used for Scheduler jobs

Every image must have at least one tag. Note: your image will not be available until the returned Docker commands are executed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ImagesApi>();
var uploadImageRequest = new UploadImageRequest(); // UploadImageRequest
UploadImageInstructions result = apiInstance.UploadImage(uploadImageRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **uploadImageRequest** | [UploadImageRequest](UploadImageRequest.md) | body | **required** | Request to upload image |

### Return type

[UploadImageInstructions](UploadImageInstructions.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UploadImageWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UploadImageInstructions> response = apiInstance.UploadImageWithHttpInfo(uploadImageRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

