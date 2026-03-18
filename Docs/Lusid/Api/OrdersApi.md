# Finbourne.Sdk.Lusid.Api.OrdersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteOrder**](#deleteorder) | **DELETE** `/api/api/orders/{scope}/{code}` | [EARLY ACCESS] DeleteOrder: Delete order |
| [**GetOrder**](#getorder) | **GET** `/api/api/orders/{scope}/{code}` | [EARLY ACCESS] GetOrder: Get Order |
| [**ListOrders**](#listorders) | **GET** `/api/api/orders` | ListOrders: List Orders |
| [**UpsertOrders**](#upsertorders) | **POST** `/api/api/orders` | UpsertOrders: Upsert Order |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<OrdersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrdersApi>();
```

---

<a id="deleteorder"></a>
## DeleteOrder

> DeletedEntityResponse DeleteOrder(string scope, string code)

[EARLY ACCESS] DeleteOrder: Delete order

Delete an order. Deletion will be valid from the order's creation datetime.  This means that the order will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrdersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteOrder(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The order scope. |
| **code** | **string** | path | **required** | The order&#39;s code. This, together with the scope uniquely identifies the order to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting an order. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteOrderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteOrderWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getorder"></a>
## GetOrder

> Order GetOrder(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] GetOrder: Get Order

Fetch an Order that matches the specified identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrdersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Order result = apiInstance.GetOrder(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the order belongs. |
| **code** | **string** | path | **required** | The order&#39;s unique identifier. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the order. Defaults to return the latest version of the order if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Orders\&quot; domain to decorate onto the order.              These take the format {domain}/{scope}/{code} e.g. \&quot;Orders/system/Name\&quot;. |

### Return type

[Order](Order.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The order matching the given identifier. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetOrderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Order> response = apiInstance.GetOrderWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listorders"></a>
## ListOrders

> PagedResourceListOfOrder ListOrders(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null, string? dataModelScope = null, string? dataModelCode = null, string? membershipType = null)

ListOrders: List Orders

Fetch the last pre-AsAt date version of each order with optional filtering (does not fetch the entire history).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrdersApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var membershipType = "membershipType_example";  // string? (optional)
PagedResourceListOfOrder result = apiInstance.ListOrders(asAt, page, sortBy, limit, filter, propertyKeys, dataModelScope, dataModelCode, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the order. Defaults to return the latest version of the order if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing orders from a previous call to list orders.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Orders\&quot; domain to decorate onto each order.                  These take the format {domain}/{scope}/{code} e.g. \&quot;Orders/system/Name\&quot;.                  All properties, except derived properties, are returned by default, without specifying here. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[PagedResourceListOfOrder](PagedResourceListOfOrder.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Orders. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfOrder> response = apiInstance.ListOrdersWithHttpInfo(asAt, page, sortBy, limit, filter, propertyKeys, dataModelScope, dataModelCode, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertorders"></a>
## UpsertOrders

> ResourceListOfOrder UpsertOrders(OrderSetRequest orderSetRequest, string? dataModelScope = null, string? dataModelCode = null)

UpsertOrders: Upsert Order

Upsert; update existing orders with given ids, or create new orders otherwise.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrdersApi>();
var orderSetRequest = new OrderSetRequest(); // OrderSetRequest
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
ResourceListOfOrder result = apiInstance.UpsertOrders(orderSetRequest, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **orderSetRequest** | [OrderSetRequest](OrderSetRequest.md) | body | **required** | The collection of order requests. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[ResourceListOfOrder](ResourceListOfOrder.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | A collection of orders. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfOrder> response = apiInstance.UpsertOrdersWithHttpInfo(orderSetRequest, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

