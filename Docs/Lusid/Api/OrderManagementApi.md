# Finbourne.Sdk.Lusid.Api.OrderManagementApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BookTransactions**](#booktransactions) | **POST** `/api/api/ordermanagement/booktransactions` | BookTransactions: Books transactions using specific allocations as a source. |
| [**CancelOrders**](#cancelorders) | **POST** `/api/api/ordermanagement/cancelorders` | [EARLY ACCESS] CancelOrders: Cancel existing orders |
| [**CancelOrdersAndMoveRemaining**](#cancelordersandmoveremaining) | **POST** `/api/api/ordermanagement/cancelordersandmoveremaining` | [EARLY ACCESS] CancelOrdersAndMoveRemaining: Cancel existing orders and move any unplaced quantities to new orders in new blocks |
| [**CancelPlacements**](#cancelplacements) | **POST** `/api/api/ordermanagement/$cancelplacements` | [EARLY ACCESS] CancelPlacements: Cancel existing placements |
| [**CreateOrders**](#createorders) | **POST** `/api/api/ordermanagement/createorders` | CreateOrders: Upsert a Block and associated orders |
| [**GetOrderHistory**](#getorderhistory) | **GET** `/api/api/ordermanagement/order/{scope}/{code}/$history` | GetOrderHistory: Get the history of an order and related entity changes |
| [**MoveOrders**](#moveorders) | **POST** `/api/api/ordermanagement/moveorders` | [EARLY ACCESS] MoveOrders: Move orders to new or existing block |
| [**PlaceBlocks**](#placeblocks) | **POST** `/api/api/ordermanagement/placeblocks` | [EARLY ACCESS] PlaceBlocks: Places blocks for a given list of placement requests. |
| [**RunAllocationService**](#runallocationservice) | **POST** `/api/api/ordermanagement/allocate` | RunAllocationService: Runs the Allocation Service |
| [**SweepBlocks**](#sweepblocks) | **POST** `/api/api/ordermanagement/SweepBlocks` | [EXPERIMENTAL] SweepBlocks: Sweeps specified blocks, for each block that meets the requirements. The request may be partially successful. |
| [**UpdateOrders**](#updateorders) | **POST** `/api/api/ordermanagement/updateorders` | [EARLY ACCESS] UpdateOrders: Update existing orders |
| [**UpdatePlacements**](#updateplacements) | **POST** `/api/api/ordermanagement/$updateplacements` | [EARLY ACCESS] UpdatePlacements: Update existing placements |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<OrderManagementApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
```

---

<a id="booktransactions"></a>
## BookTransactions

> BookTransactionsResponse BookTransactions(BookTransactionsRequest bookTransactionsRequest, bool? applyFeesAndCommission = null, bool? markOrdersAndAllocationsAsBooked = null)

BookTransactions: Books transactions using specific allocations as a source.

Takes a collection of allocation IDs, and maps fields from those allocations and related orders onto new transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var bookTransactionsRequest = new BookTransactionsRequest(); // BookTransactionsRequest
var applyFeesAndCommission = true;  // bool? (optional)
var markOrdersAndAllocationsAsBooked = false;  // bool? (optional)
BookTransactionsResponse result = apiInstance.BookTransactions(bookTransactionsRequest, applyFeesAndCommission, markOrdersAndAllocationsAsBooked);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **bookTransactionsRequest** | [BookTransactionsRequest](BookTransactionsRequest.md) | body | **required** | The allocations to create transactions for |
| **applyFeesAndCommission** | **bool?** | query | optional | Whether to apply fees and commissions to transactions (default: true) Default: `true` |
| **markOrdersAndAllocationsAsBooked** | **bool?** | query | optional | Whether to mark allocations and fully-booked orders with state Booked Default: `false` |

### Return type

[BookTransactionsResponse](BookTransactionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The results from booking transactions from allocations |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BookTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BookTransactionsResponse> response = apiInstance.BookTransactionsWithHttpInfo(bookTransactionsRequest, applyFeesAndCommission, markOrdersAndAllocationsAsBooked);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="cancelorders"></a>
## CancelOrders

> CancelOrdersResponse CancelOrders(Dictionary<string, ResourceId> requestBody)

[EARLY ACCESS] CancelOrders: Cancel existing orders

The response returns both the collection of successfully canceled orders, as well as those  that failed. For each failure, a reason is provided. It is important to check the failed set for  unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var requestBody = new Dictionary<string, ResourceId>(); // Dictionary<string, ResourceId>
CancelOrdersResponse result = apiInstance.CancelOrders(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, ResourceId&gt;](ResourceId.md) | body | **required** | The request containing the ids of the orders to be cancelled. |

### Return type

[CancelOrdersResponse](CancelOrdersResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully cancelled orders along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CancelOrdersResponse> response = apiInstance.CancelOrdersWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="cancelordersandmoveremaining"></a>
## CancelOrdersAndMoveRemaining

> CancelOrdersAndMoveRemainingResponse CancelOrdersAndMoveRemaining(Dictionary<string, CancelOrdersAndMoveRemainingRequest> requestBody)

[EARLY ACCESS] CancelOrdersAndMoveRemaining: Cancel existing orders and move any unplaced quantities to new orders in new blocks

Cancels existing orders, reducing their quantities to those aleady placed. Any remaining quantities are moved  to new orders in new blocks. The placed quantities are distributed to the cancelled orders on a pro-rata basis.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var requestBody = new Dictionary<string, CancelOrdersAndMoveRemainingRequest>(); // Dictionary<string, CancelOrdersAndMoveRemainingRequest>
CancelOrdersAndMoveRemainingResponse result = apiInstance.CancelOrdersAndMoveRemaining(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, CancelOrdersAndMoveRemainingRequest&gt;](CancelOrdersAndMoveRemainingRequest.md) | body | **required** | The request containing the orders to be cancelled, and the destinations of remaining quantities. |

### Return type

[CancelOrdersAndMoveRemainingResponse](CancelOrdersAndMoveRemainingResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully cancelled and moved orders, along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelOrdersAndMoveRemainingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CancelOrdersAndMoveRemainingResponse> response = apiInstance.CancelOrdersAndMoveRemainingWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="cancelplacements"></a>
## CancelPlacements

> CancelPlacementsResponse CancelPlacements(Dictionary<string, ResourceId> requestBody)

[EARLY ACCESS] CancelPlacements: Cancel existing placements

The response returns both the collection of successfully canceled placements, as well as those  that failed. For each failure, a reason is provided. It is important to check the failed set for  unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var requestBody = new Dictionary<string, ResourceId>(); // Dictionary<string, ResourceId>
CancelPlacementsResponse result = apiInstance.CancelPlacements(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, ResourceId&gt;](ResourceId.md) | body | **required** | The request containing the ids of the placements to be cancelled. |

### Return type

[CancelPlacementsResponse](CancelPlacementsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully cancelled placements along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelPlacementsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CancelPlacementsResponse> response = apiInstance.CancelPlacementsWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createorders"></a>
## CreateOrders

> ResourceListOfBlockAndOrders CreateOrders(BlockAndOrdersCreateRequest blockAndOrdersCreateRequest)

CreateOrders: Upsert a Block and associated orders

Create orders, and blocks if they don't already exist.  This will fail if the block exists and already references orders with differing blocking fields.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var blockAndOrdersCreateRequest = new BlockAndOrdersCreateRequest(); // BlockAndOrdersCreateRequest
ResourceListOfBlockAndOrders result = apiInstance.CreateOrders(blockAndOrdersCreateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **blockAndOrdersCreateRequest** | [BlockAndOrdersCreateRequest](BlockAndOrdersCreateRequest.md) | body | **required** | The collection of block and orders requests. |

### Return type

[ResourceListOfBlockAndOrders](ResourceListOfBlockAndOrders.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | A collection of block and associated orders. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfBlockAndOrders> response = apiInstance.CreateOrdersWithHttpInfo(blockAndOrdersCreateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getorderhistory"></a>
## GetOrderHistory

> ResourceListOfChangeIntervalWithOrderManagementDetail GetOrderHistory(string scope, string code, DateTimeOffset? asAt = null)

GetOrderHistory: Get the history of an order and related entity changes

Get the changes that have happened to an order and related entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfChangeIntervalWithOrderManagementDetail result = apiInstance.GetOrderHistory(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the order. |
| **code** | **string** | path | **required** | The code of the order. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the history of the order and related entities. Defaults              to return the latest version if not specified. |

### Return type

[ResourceListOfChangeIntervalWithOrderManagementDetail](ResourceListOfChangeIntervalWithOrderManagementDetail.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The history of the specified order and related entities (changes that have been made to it). |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Order not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetOrderHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfChangeIntervalWithOrderManagementDetail> response = apiInstance.GetOrderHistoryWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="moveorders"></a>
## MoveOrders

> ResourceListOfMovedOrderToDifferentBlockResponse MoveOrders(MoveOrdersToDifferentBlocksRequest moveOrdersToDifferentBlocksRequest)

[EARLY ACCESS] MoveOrders: Move orders to new or existing block

Move an order to a block, creating the block if it does not already exist.   This will fail if the block exists and already references orders with differing fields to the upsert request.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var moveOrdersToDifferentBlocksRequest = new MoveOrdersToDifferentBlocksRequest(); // MoveOrdersToDifferentBlocksRequest
ResourceListOfMovedOrderToDifferentBlockResponse result = apiInstance.MoveOrders(moveOrdersToDifferentBlocksRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **moveOrdersToDifferentBlocksRequest** | [MoveOrdersToDifferentBlocksRequest](MoveOrdersToDifferentBlocksRequest.md) | body | **required** | The collection of order and destination block ids. |

### Return type

[ResourceListOfMovedOrderToDifferentBlockResponse](ResourceListOfMovedOrderToDifferentBlockResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of block and order pairs for each order moved into a block, and the Id of the order&#39;s previous block (if any). |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the MoveOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfMovedOrderToDifferentBlockResponse> response = apiInstance.MoveOrdersWithHttpInfo(moveOrdersToDifferentBlocksRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="placeblocks"></a>
## PlaceBlocks

> ResourceListOfPlacement PlaceBlocks(PlaceBlocksRequest? placeBlocksRequest = null)

[EARLY ACCESS] PlaceBlocks: Places blocks for a given list of placement requests.

The referenced block's existence will be verified.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var placeBlocksRequest = new PlaceBlocksRequest?(); // PlaceBlocksRequest? (optional)
ResourceListOfPlacement result = apiInstance.PlaceBlocks(placeBlocksRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **placeBlocksRequest** | [PlaceBlocksRequest?](PlaceBlocksRequest?.md) | body | optional | The request containing the blocks to the placed. |

### Return type

[ResourceListOfPlacement](ResourceListOfPlacement.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The block placements. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PlaceBlocksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPlacement> response = apiInstance.PlaceBlocksWithHttpInfo(placeBlocksRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runallocationservice"></a>
## RunAllocationService

> AllocationServiceRunResponse RunAllocationService(List<ResourceId> resourceId, string? allocationAlgorithm = null)

RunAllocationService: Runs the Allocation Service

Allocates Executions for a given list of placements back to their originating orders using one of the LUSID algorithms, creating Allocations to record the results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var resourceId = new List<ResourceId>(); // List<ResourceId>
var allocationAlgorithm = "allocationAlgorithm_example";  // string? (optional)
AllocationServiceRunResponse result = apiInstance.RunAllocationService(resourceId, allocationAlgorithm);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **resourceId** | [List&lt;ResourceId&gt;](ResourceId.md) | body | **required** | The List of Placement IDs for which you wish to allocate Executions. |
| **allocationAlgorithm** | **string?** | query | optional | A string representation of the allocation algorithm you would like to use to allocate shares from executions e.g. \&quot;PR-FIFO\&quot;.  This defaults to \&quot;PR-FIFO\&quot;. |

### Return type

[AllocationServiceRunResponse](AllocationServiceRunResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of Allocations |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunAllocationServiceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationServiceRunResponse> response = apiInstance.RunAllocationServiceWithHttpInfo(resourceId, allocationAlgorithm);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="sweepblocks"></a>
## SweepBlocks

> SweepBlocksResponse SweepBlocks(SweepBlocksRequest sweepBlocksRequest)

[EXPERIMENTAL] SweepBlocks: Sweeps specified blocks, for each block that meets the requirements. The request may be partially successful.

The requirements are:  <list type=\"bullet\"><term>The block exists.</term><term>All orders have state \"Closed\", \"Cancelled\", \"Canceled\" or \"Booked\".</term><term>All placements have state \"Allocated\" or \"Over-allocated\".</term><term>All allocations have state \"Closed\", \"Cancelled\", \"Canceled\" or \"Booked\".</term><term>No execution or allocation has been modified since the passed LatestAllowableModificationTime.</term></list>

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var sweepBlocksRequest = new SweepBlocksRequest(); // SweepBlocksRequest
SweepBlocksResponse result = apiInstance.SweepBlocks(sweepBlocksRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sweepBlocksRequest** | [SweepBlocksRequest](SweepBlocksRequest.md) | body | **required** |  |

### Return type

[SweepBlocksResponse](SweepBlocksResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The results from sweeping blocks. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SweepBlocksWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SweepBlocksResponse> response = apiInstance.SweepBlocksWithHttpInfo(sweepBlocksRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateorders"></a>
## UpdateOrders

> UpdateOrdersResponse UpdateOrders(Dictionary<string, OrderUpdateRequest> requestBody)

[EARLY ACCESS] UpdateOrders: Update existing orders

The response returns both the collection of successfully updated orders, as well as those  that failed. For each failure, a reason is provided. It is important to check the failed set for  unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var requestBody = new Dictionary<string, OrderUpdateRequest>(); // Dictionary<string, OrderUpdateRequest>
UpdateOrdersResponse result = apiInstance.UpdateOrders(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, OrderUpdateRequest&gt;](OrderUpdateRequest.md) | body | **required** | The request containing the orders to be updated. |

### Return type

[UpdateOrdersResponse](UpdateOrdersResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated orders along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpdateOrdersResponse> response = apiInstance.UpdateOrdersWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateplacements"></a>
## UpdatePlacements

> UpdatePlacementsResponse UpdatePlacements(Dictionary<string, PlacementUpdateRequest> requestBody)

[EARLY ACCESS] UpdatePlacements: Update existing placements

The response returns both the collection of successfully updated placements, as well as those  that failed. For each failure, a reason is provided. It is important to check the failed set for  unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<OrderManagementApi>();
var requestBody = new Dictionary<string, PlacementUpdateRequest>(); // Dictionary<string, PlacementUpdateRequest>
UpdatePlacementsResponse result = apiInstance.UpdatePlacements(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, PlacementUpdateRequest&gt;](PlacementUpdateRequest.md) | body | **required** | The request containing the placements to be updated. |

### Return type

[UpdatePlacementsResponse](UpdatePlacementsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated placements along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePlacementsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpdatePlacementsResponse> response = apiInstance.UpdatePlacementsWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

