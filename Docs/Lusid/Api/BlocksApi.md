# Finbourne.Sdk.Lusid.Api.BlocksApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteBlock**](#deleteblock) | **DELETE** `/api/api/blocks/{scope}/{code}` | [EARLY ACCESS] DeleteBlock: Delete block |
| [**GetBlock**](#getblock) | **GET** `/api/api/blocks/{scope}/{code}` | [EARLY ACCESS] GetBlock: Get Block |
| [**ListBlocks**](#listblocks) | **GET** `/api/api/blocks` | [EARLY ACCESS] ListBlocks: List Blocks |
| [**UpsertBlocks**](#upsertblocks) | **POST** `/api/api/blocks` | [EARLY ACCESS] UpsertBlocks: Upsert Block |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<BlocksApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BlocksApi>();
```

---

<a id="deleteblock"></a>
## DeleteBlock

> DeletedEntityResponse DeleteBlock(string scope, string code)

[EARLY ACCESS] DeleteBlock: Delete block

Delete an block. Deletion will be valid from the block's creation datetime.  This means that the block will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BlocksApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteBlock(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The block scope. |
| **code** | **string** | path | **required** | The block&#39;s code. This, together with the scope uniquely identifies the block to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting an block. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteBlockWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteBlockWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getblock"></a>
## GetBlock

> Block GetBlock(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] GetBlock: Get Block

Fetch a Block that matches the specified identifier

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BlocksApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Block result = apiInstance.GetBlock(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the block belongs. |
| **code** | **string** | path | **required** | The block&#39;s unique identifier. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the block. Defaults to return the latest version of the block if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Block\&quot; domain to decorate onto the block.              These take the format {domain}/{scope}/{code} e.g. \&quot;Block/system/Name\&quot;. |

### Return type

[Block](Block.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The block matching the given identifier. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetBlockWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Block> response = apiInstance.GetBlockWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listblocks"></a>
## ListBlocks

> PagedResourceListOfBlock ListBlocks(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

[EARLY ACCESS] ListBlocks: List Blocks

Fetch the last pre-AsAt date version of each block in scope (does not fetch the entire history).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BlocksApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfBlock result = apiInstance.ListBlocks(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the block. Defaults to return the latest version of the block if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing blocks from a previous call to list blocks.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Block\&quot; domain to decorate onto each block.                  These take the format {domain}/{scope}/{code} e.g. \&quot;Block/system/Name\&quot;.                  All properties, except derived properties, are returned by default, without specifying here. |

### Return type

[PagedResourceListOfBlock](PagedResourceListOfBlock.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Blocks in scope. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListBlocksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfBlock> response = apiInstance.ListBlocksWithHttpInfo(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertblocks"></a>
## UpsertBlocks

> ResourceListOfBlock UpsertBlocks(BlockSetRequest? blockSetRequest = null)

[EARLY ACCESS] UpsertBlocks: Upsert Block

Upsert; update existing blocks with given ids, or create new blocks otherwise.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<BlocksApi>();
var blockSetRequest = new BlockSetRequest?(); // BlockSetRequest? (optional)
ResourceListOfBlock result = apiInstance.UpsertBlocks(blockSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **blockSetRequest** | [BlockSetRequest?](BlockSetRequest?.md) | body | optional | The collection of block requests. |

### Return type

[ResourceListOfBlock](ResourceListOfBlock.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | A collection of blocks. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertBlocksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfBlock> response = apiInstance.UpsertBlocksWithHttpInfo(blockSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

