# Finbourne.Sdk.Lusid.Api.OrderGraphApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**ListOrderGraphBlocks**](#listordergraphblocks) | **GET** `/api/api/ordergraph/blocks` | ListOrderGraphBlocks: Lists blocks that pass the filter provided, and builds a summary picture of the state of their associated order entities. |
| [**ListOrderGraphPlacementChildren**](#listordergraphplacementchildren) | **GET** `/api/api/ordergraph/placementchildren/{scope}/{code}` | [EARLY ACCESS] ListOrderGraphPlacementChildren: Lists all placements for the parent placement specified by the scope and code, and builds a summary picture of the state of their associated order entities. |
| [**ListOrderGraphPlacements**](#listordergraphplacements) | **GET** `/api/api/ordergraph/placements` | ListOrderGraphPlacements: Lists placements that pass the filter provided, and builds a summary picture of the state of their associated order entities. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<OrderGraphApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderGraphApi>();
```

---

<a id="listordergraphblocks"></a>
## ListOrderGraphBlocks

> PagedResourceListOfOrderGraphBlock ListOrderGraphBlocks(DateTimeOffset? asAt = null, string? paginationToken = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null, bool? useComplianceV2 = null)

ListOrderGraphBlocks: Lists blocks that pass the filter provided, and builds a summary picture of the state of their associated order entities.

Lists all blocks of orders, subject to the filter, along with the IDs of orders, placements, allocations and  executions in the block, the total quantities of each, and a simple text field describing the overall state.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderGraphApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var paginationToken = "paginationToken_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "\"\"";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var useComplianceV2 = false;  // bool? (optional)
PagedResourceListOfOrderGraphBlock result = apiInstance.ListOrderGraphBlocks(asAt, paginationToken, sortBy, limit, filter, propertyKeys, useComplianceV2);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01832/ |
| **paginationToken** | **string?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01915/ |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01915/ |
| **filter** | **string?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01914/ Default: `&quot;&quot;` |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | Must be block-level properties. See https://support.lusid.com/knowledgebase/article/KA-01855/ |
| **useComplianceV2** | **bool?** | query | optional | Whether to use the V2 compliance engine when deriving compliance statuses for orders. (default: false) Default: `false` |

### Return type

[PagedResourceListOfOrderGraphBlock](PagedResourceListOfOrderGraphBlock.md)

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
<summary>Using the ListOrderGraphBlocksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfOrderGraphBlock> response = apiInstance.ListOrderGraphBlocksWithHttpInfo(asAt, paginationToken, sortBy, limit, filter, propertyKeys, useComplianceV2);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listordergraphplacementchildren"></a>
## ListOrderGraphPlacementChildren

> PagedResourceListOfOrderGraphPlacement ListOrderGraphPlacementChildren(string scope, string code, DateTimeOffset? asAt = null, string? paginationToken = null, List<string>? sortBy = null, int? limit = null, List<string>? propertyKeys = null)

[EARLY ACCESS] ListOrderGraphPlacementChildren: Lists all placements for the parent placement specified by the scope and code, and builds a summary picture of the state of their associated order entities.

Lists all child order placements, for the specified parent placement, along with the IDs of the block and order that the  placement is for, each placement's quantity, the IDs of all allocations and executions in the placement  and the total quantities of those, and a simple text field describing the overall state of the placement.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderGraphApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var paginationToken = "paginationToken_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfOrderGraphPlacement result = apiInstance.ListOrderGraphPlacementChildren(scope, code, asAt, paginationToken, sortBy, limit, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The parent placement&#39;s scope |
| **code** | **string** | path | **required** | The parent placement&#39;s code |
| **asAt** | **DateTimeOffset?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01832/ |
| **paginationToken** | **string?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01915/ |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName. |
| **limit** | **int?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01915/ |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | Must be placement properties. See https://support.lusid.com/knowledgebase/article/KA-01855/ |

### Return type

[PagedResourceListOfOrderGraphPlacement](PagedResourceListOfOrderGraphPlacement.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List all child Placements for the specified Placement. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListOrderGraphPlacementChildrenWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfOrderGraphPlacement> response = apiInstance.ListOrderGraphPlacementChildrenWithHttpInfo(scope, code, asAt, paginationToken, sortBy, limit, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listordergraphplacements"></a>
## ListOrderGraphPlacements

> PagedResourceListOfOrderGraphPlacement ListOrderGraphPlacements(DateTimeOffset? asAt = null, string? paginationToken = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

ListOrderGraphPlacements: Lists placements that pass the filter provided, and builds a summary picture of the state of their associated order entities.

Lists all order placements, subject to the filter, along with the IDs of the block and order that the  placement is for, each placement's quantity, the IDs of all allocations and executions in the placement  and the total quantities of those, and a simple text field describing the overall state of the placement.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderGraphApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var paginationToken = "paginationToken_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "\"\"";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfOrderGraphPlacement result = apiInstance.ListOrderGraphPlacements(asAt, paginationToken, sortBy, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01832/ |
| **paginationToken** | **string?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01915/ |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01915/ |
| **filter** | **string?** | query | optional | See https://support.lusid.com/knowledgebase/article/KA-01914/ Default: `&quot;&quot;` |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | Must be placement properties. See https://support.lusid.com/knowledgebase/article/KA-01855/ |

### Return type

[PagedResourceListOfOrderGraphPlacement](PagedResourceListOfOrderGraphPlacement.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Placements in scope. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListOrderGraphPlacementsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfOrderGraphPlacement> response = apiInstance.ListOrderGraphPlacementsWithHttpInfo(asAt, paginationToken, sortBy, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

