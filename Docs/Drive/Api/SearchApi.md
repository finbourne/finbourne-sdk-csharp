# Finbourne.Sdk.Drive.Api.SearchApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**Search**](#search) | **POST** `/drive/api/search` | [EARLY ACCESS] Search: Search for a file or folder with a given name and path |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SearchApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
```

---

<a id="search"></a>
## Search

> PagedResourceListOfStorageObject Search(SearchBody searchBody, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

[EARLY ACCESS] Search: Search for a file or folder with a given name and path

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SearchApi>();
var searchBody = new SearchBody(); // SearchBody
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "\"\"";  // string? (optional)
PagedResourceListOfStorageObject result = apiInstance.Search(searchBody, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **searchBody** | [SearchBody](SearchBody.md) | body | **required** | Search parameters |
| **page** | **string?** | query | optional |  |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional |  |
| **limit** | **int?** | query | optional |  |
| **filter** | **string?** | query | optional |  Default: `&quot;&quot;` |

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
| **0** | Error response |  -  |

<details>
<summary>Using the SearchWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStorageObject> response = apiInstance.SearchWithHttpInfo(searchBody, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

