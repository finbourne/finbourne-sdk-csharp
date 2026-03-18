# Finbourne.Sdk.Identity.Api.MCPToolsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateMcpTool**](#createmcptool) | **POST** `/identity/api/mcptools/{scope}/{code}` | [EARLY ACCESS] CreateMcpTool: Create an MCP Tool |
| [**DeleteMcpTool**](#deletemcptool) | **DELETE** `/identity/api/mcptools/{scope}/{code}` | [EARLY ACCESS] DeleteMcpTool: Delete an MCP Tool |
| [**GetMcpTool**](#getmcptool) | **GET** `/identity/api/mcptools/{scope}/{code}` | [EARLY ACCESS] GetMcpTool: Get an MCP Tool |
| [**ListMcpTools**](#listmcptools) | **GET** `/identity/api/mcptools` | [EARLY ACCESS] ListMcpTools: List all MCP Tools |
| [**UpdateMcpTool**](#updatemcptool) | **PUT** `/identity/api/mcptools/{scope}/{code}` | [EARLY ACCESS] UpdateMcpTool: Update an MCP Tool |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<MCPToolsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MCPToolsApi>();
```

---

<a id="createmcptool"></a>
## CreateMcpTool

> McpToolResponse CreateMcpTool(string scope, string code, UpsertMcpToolRequest upsertMcpToolRequest)

[EARLY ACCESS] CreateMcpTool: Create an MCP Tool

Creates a new MCP tool definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MCPToolsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertMcpToolRequest = new UpsertMcpToolRequest(); // UpsertMcpToolRequest
McpToolResponse result = apiInstance.CreateMcpTool(scope, code, upsertMcpToolRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the MCP tool |
| **code** | **string** | path | **required** | The code of the MCP tool |
| **upsertMcpToolRequest** | [UpsertMcpToolRequest](UpsertMcpToolRequest.md) | body | **required** | The MCP tool definition |

### Return type

[McpToolResponse](McpToolResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Create MCP Tool |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateMcpToolWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<McpToolResponse> response = apiInstance.CreateMcpToolWithHttpInfo(scope, code, upsertMcpToolRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletemcptool"></a>
## DeleteMcpTool

> void DeleteMcpTool(string scope, string code)

[EARLY ACCESS] DeleteMcpTool: Delete an MCP Tool

Deletes an MCP tool (soft delete - closes the current version)

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MCPToolsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
apiInstance.DeleteMcpTool(scope, code);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the MCP tool |
| **code** | **string** | path | **required** | The code of the MCP tool |

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
<summary>Using the DeleteMcpToolWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteMcpToolWithHttpInfo(scope, code);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmcptool"></a>
## GetMcpTool

> McpToolResponse GetMcpTool(string scope, string code, int? version = null)

[EARLY ACCESS] GetMcpTool: Get an MCP Tool

Retrieves an MCP tool. If version is specified, retrieves that specific version for audit purposes. Otherwise, retrieves the current version.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MCPToolsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var version = 56;  // int? (optional)
McpToolResponse result = apiInstance.GetMcpTool(scope, code, version);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the MCP tool |
| **code** | **string** | path | **required** | The code of the MCP tool |
| **version** | **int?** | query | optional | Optional version number to retrieve. If not specified, returns the current version. |

### Return type

[McpToolResponse](McpToolResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get MCP Tool |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMcpToolWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<McpToolResponse> response = apiInstance.GetMcpToolWithHttpInfo(scope, code, version);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmcptools"></a>
## ListMcpTools

> List&lt;McpToolResponse&gt; ListMcpTools()

[EARLY ACCESS] ListMcpTools: List all MCP Tools

Lists all current MCP tools for the domain

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MCPToolsApi>();
List<McpToolResponse> result = apiInstance.ListMcpTools();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;McpToolResponse&gt;](McpToolResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List MCP Tools |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMcpToolsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<McpToolResponse>> response = apiInstance.ListMcpToolsWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatemcptool"></a>
## UpdateMcpTool

> McpToolResponse UpdateMcpTool(string scope, string code, UpsertMcpToolRequest upsertMcpToolRequest)

[EARLY ACCESS] UpdateMcpTool: Update an MCP Tool

Updates an existing MCP tool, creating a new version

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MCPToolsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertMcpToolRequest = new UpsertMcpToolRequest(); // UpsertMcpToolRequest
McpToolResponse result = apiInstance.UpdateMcpTool(scope, code, upsertMcpToolRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the MCP tool |
| **code** | **string** | path | **required** | The code of the MCP tool |
| **upsertMcpToolRequest** | [UpsertMcpToolRequest](UpsertMcpToolRequest.md) | body | **required** | The updated MCP tool definition |

### Return type

[McpToolResponse](McpToolResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update MCP Tool |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateMcpToolWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<McpToolResponse> response = apiInstance.UpdateMcpToolWithHttpInfo(scope, code, upsertMcpToolRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

