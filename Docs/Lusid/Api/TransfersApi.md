# Finbourne.Sdk.Lusid.Api.TransfersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTransfer**](#createtransfer) | **POST** `/api/api/transfers` | [EXPERIMENTAL] CreateTransfer: Create a transfer. |
| [**DeleteTransfer**](#deletetransfer) | **DELETE** `/api/api/transfers/{scope}/{code}` | [EXPERIMENTAL] DeleteTransfer: Delete a transfer. |
| [**GetTransfer**](#gettransfer) | **POST** `/api/api/transfers/$get` | [EXPERIMENTAL] GetTransfer: Get a transfer |
| [**ListTransfers**](#listtransfers) | **GET** `/api/api/transfers` | [EXPERIMENTAL] ListTransfers: List transfers |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransfersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
```

---

<a id="createtransfer"></a>
## CreateTransfer

> CreateTransferResponse CreateTransfer(CreateTransferRequest createTransferRequest)

[EXPERIMENTAL] CreateTransfer: Create a transfer.

Move a position between two portfolios, exchange one instrument for another within a portfolio, or do  both at once.  The outgoing and incoming transaction legs and the Transfer entity recording them are written as a single  atomic operation: if any part of the request is rejected, nothing is written.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
var createTransferRequest = new CreateTransferRequest(); // CreateTransferRequest
CreateTransferResponse result = apiInstance.CreateTransfer(createTransferRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createTransferRequest** | [CreateTransferRequest](../Model/CreateTransferRequest.md) | body | **required** | The transfer to create. |

### Return type

[CreateTransferResponse](../Model/CreateTransferResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The transfer that was created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTransferWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CreateTransferResponse> response = apiInstance.CreateTransferWithHttpInfo(createTransferRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransfer"></a>
## DeleteTransfer

> DeletedEntityResponse DeleteTransfer(string scope, string code, string portfolioScopeOut, string portfolioCodeOut, string portfolioScopeIn, string portfolioCodeIn)

[EXPERIMENTAL] DeleteTransfer: Delete a transfer.

Delete the Transfer entity recording a transfer and cancel the transaction legs it still has, as a single  atomic operation: if any part of the request is rejected, nothing is changed. A leg that has already gone is  skipped, so a transfer with no legs left can still be deleted to clear the record.                A transfer is identified by its scope, its code and both of its portfolios, so all four are required. Where  no transfer matches all four, the request is reported as not found.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var portfolioScopeOut = "portfolioScopeOut_example";  // string
var portfolioCodeOut = "portfolioCodeOut_example";  // string
var portfolioScopeIn = "portfolioScopeIn_example";  // string
var portfolioCodeIn = "portfolioCodeIn_example";  // string
DeletedEntityResponse result = apiInstance.DeleteTransfer(scope, code, portfolioScopeOut, portfolioCodeOut, portfolioScopeIn, portfolioCodeIn);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transfer. |
| **code** | **string** | path | **required** | The code of the transfer. Together with the scope and both portfolios this uniquely               identifies the transfer. |
| **portfolioScopeOut** | **string** | query | **required** | The scope of the portfolio the outgoing leg is booked in. |
| **portfolioCodeOut** | **string** | query | **required** | The code of the portfolio the outgoing leg is booked in. |
| **portfolioScopeIn** | **string** | query | **required** | The scope of the portfolio the incoming leg is booked in. |
| **portfolioCodeIn** | **string** | query | **required** | The code of the portfolio the incoming leg is booked in. Equal to               portfolioCodeOut for a switch between instruments within one portfolio. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The asAt the deletion landed at. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No transfer with the given scope, code and portfolios. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTransferWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteTransferWithHttpInfo(scope, code, portfolioScopeOut, portfolioCodeOut, portfolioScopeIn, portfolioCodeIn);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransfer"></a>
## GetTransfer

> Transfer GetTransfer(GetTransferRequest getTransferRequest, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetTransfer: Get a transfer

Retrieve a transfer and both of the transactions it booked.  A transfer is identified by its scope, its code and both of its portfolios, so all four are supplied in  the request body rather than in the path.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
var getTransferRequest = new GetTransferRequest(); // GetTransferRequest
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Transfer result = apiInstance.GetTransfer(getTransferRequest, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **getTransferRequest** | [GetTransferRequest](../Model/GetTransferRequest.md) | body | **required** | The transfer to retrieve. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transfer. Defaults to latest              version if not specified. |

### Return type

[Transfer](../Model/Transfer.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested transfer and both of its transactions. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No transfer exists with the requested scope, code and portfolios. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransferWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Transfer> response = apiInstance.GetTransferWithHttpInfo(getTransferRequest, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtransfers"></a>
## ListTransfers

> ResourceListOfTransfer ListTransfers(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListTransfers: List transfers

List transfers matching the specified criteria, decorated with the requested properties.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ResourceListOfTransfer result = apiInstance.ListTransfers(asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transfers. Defaults to latest              version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transfers from a previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. NOTE: Filtering on nested transaction out/in fields is not supported. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | The collection of &#x60;PropertyKey&#x60;s to decorate onto each transfer. |

### Return type

[ResourceListOfTransfer](../Model/ResourceListOfTransfer.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of transfers matching the specified criteria. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTransfersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTransfer> response = apiInstance.ListTransfersWithHttpInfo(asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

