# Finbourne.Sdk.Horizon.Api.TradePublicationFrameworkApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetTpfTransactionHistorySearch**](#gettpftransactionhistorysearch) | **GET** `/horizon/api/trade-publication-framework/transactions/search` | [EXPERIMENTAL] GetTpfTransactionHistorySearch: Endpoint to search TPF transaction by transaction ID and/or instrument identifier, with filtering by instance and date range |
| [**GetTransactionPayload**](#gettransactionpayload) | **GET** `/horizon/api/trade-publication-framework/instances/{instanceId}/runs/{runId}/transactions/{transactionId}/payload` | [EXPERIMENTAL] GetTransactionPayload: Transaction payload detail |
| [**ListInstanceRunHistory**](#listinstancerunhistory) | **GET** `/horizon/api/trade-publication-framework/instances/{instanceId}/runs` | [EXPERIMENTAL] ListInstanceRunHistory: List run history for a given TPF instance, with pagination support. |
| [**ListInstancesWithStatus**](#listinstanceswithstatus) | **GET** `/horizon/api/trade-publication-framework/instances` | [EXPERIMENTAL] ListInstancesWithStatus: Lists all instances of the Trade Publication Framework (TPF). |
| [**ListRunFiles**](#listrunfiles) | **GET** `/horizon/api/trade-publication-framework/instances/{instanceId}/runs/{runId}/files` | [EXPERIMENTAL] ListRunFiles: List Files in a run |
| [**ListRunTransactions**](#listruntransactions) | **GET** `/horizon/api/trade-publication-framework/instances/{instanceId}/runs/{runId}/transactions` | [EXPERIMENTAL] ListRunTransactions: List Transactions in a run. |
| [**ReplayTransactions**](#replaytransactions) | **POST** `/horizon/api/trade-publication-framework/instances/{instanceId}/replay` | [EXPERIMENTAL] ReplayTransactions: Replay one or more transactions through a TPF instance |
| [**RetryTpfSftpDelivery**](#retrytpfsftpdelivery) | **POST** `/horizon/api/trade-publication-framework/instances/{instanceId}/files/{fileId}/retry-sftp` | [EXPERIMENTAL] RetryTpfSftpDelivery: Retry SFTP delivery for a previously sent TPF file |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TradePublicationFrameworkApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
```

---

<a id="gettpftransactionhistorysearch"></a>
## GetTpfTransactionHistorySearch

> PagedResourceListOfTpfTransactionSearchResponse GetTpfTransactionHistorySearch(string? transactionId = null, string? instrumentId = null, string? dateFrom = null, string? dateTo = null, string? status = null, string? instanceId = null, int? pageSize = null, string? pageToken = null)

[EXPERIMENTAL] GetTpfTransactionHistorySearch: Endpoint to search TPF transaction by transaction ID and/or instrument identifier, with filtering by instance and date range

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var transactionId = "transactionId_example";  // string? (optional)
var instrumentId = "instrumentId_example";  // string? (optional)
var dateFrom = "dateFrom_example";  // string? (optional)
var dateTo = "dateTo_example";  // string? (optional)
var status = "status_example";  // string? (optional)
var instanceId = "instanceId_example";  // string? (optional)
var pageSize = 400;  // int? (optional)
var pageToken = "\"\"";  // string? (optional)
PagedResourceListOfTpfTransactionSearchResponse result = apiInstance.GetTpfTransactionHistorySearch(transactionId, instrumentId, dateFrom, dateTo, status, instanceId, pageSize, pageToken);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **transactionId** | **string?** | query | optional |  |
| **instrumentId** | **string?** | query | optional |  |
| **dateFrom** | **string?** | query | optional |  |
| **dateTo** | **string?** | query | optional |  |
| **status** | **string?** | query | optional |  |
| **instanceId** | **string?** | query | optional |  |
| **pageSize** | **int?** | query | optional |  Default: `400` |
| **pageToken** | **string?** | query | optional |  Default: `&quot;&quot;` |

### Return type

[PagedResourceListOfTpfTransactionSearchResponse](PagedResourceListOfTpfTransactionSearchResponse.md)

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
<summary>Using the GetTpfTransactionHistorySearchWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTpfTransactionSearchResponse> response = apiInstance.GetTpfTransactionHistorySearchWithHttpInfo(transactionId, instrumentId, dateFrom, dateTo, status, instanceId, pageSize, pageToken);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionpayload"></a>
## GetTransactionPayload

> TransactionPayloadResponse GetTransactionPayload(string instanceId, string runId, string transactionId)

[EXPERIMENTAL] GetTransactionPayload: Transaction payload detail

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var instanceId = "instanceId_example";  // string
var runId = "runId_example";  // string
var transactionId = "transactionId_example";  // string
TransactionPayloadResponse result = apiInstance.GetTransactionPayload(instanceId, runId, transactionId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |
| **runId** | **string** | path | **required** |  |
| **transactionId** | **string** | path | **required** |  |

### Return type

[TransactionPayloadResponse](TransactionPayloadResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested TPF instance, run, or transaction payload does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionPayloadWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionPayloadResponse> response = apiInstance.GetTransactionPayloadWithHttpInfo(instanceId, runId, transactionId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listinstancerunhistory"></a>
## ListInstanceRunHistory

> PagedResourceListOfInstanceRunResponse ListInstanceRunHistory(string instanceId, string? page = null, int? pageSize = null)

[EXPERIMENTAL] ListInstanceRunHistory: List run history for a given TPF instance, with pagination support.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var instanceId = "instanceId_example";  // string
var page = "\"\"";  // string? (optional)
var pageSize = 100;  // int? (optional)
PagedResourceListOfInstanceRunResponse result = apiInstance.ListInstanceRunHistory(instanceId, page, pageSize);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |
| **page** | **string?** | query | optional |  Default: `&quot;&quot;` |
| **pageSize** | **int?** | query | optional |  Default: `100` |

### Return type

[PagedResourceListOfInstanceRunResponse](PagedResourceListOfInstanceRunResponse.md)

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
<summary>Using the ListInstanceRunHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfInstanceRunResponse> response = apiInstance.ListInstanceRunHistoryWithHttpInfo(instanceId, page, pageSize);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listinstanceswithstatus"></a>
## ListInstancesWithStatus

> InstancesResponse ListInstancesWithStatus()

[EXPERIMENTAL] ListInstancesWithStatus: Lists all instances of the Trade Publication Framework (TPF).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
InstancesResponse result = apiInstance.ListInstancesWithStatus();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[InstancesResponse](InstancesResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListInstancesWithStatusWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstancesResponse> response = apiInstance.ListInstancesWithStatusWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listrunfiles"></a>
## ListRunFiles

> PagedResourceListOfRunFileResponse ListRunFiles(string instanceId, string runId, string? page = null, int? pageSize = null)

[EXPERIMENTAL] ListRunFiles: List Files in a run

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var instanceId = "instanceId_example";  // string
var runId = "runId_example";  // string
var page = "\"\"";  // string? (optional)
var pageSize = 100;  // int? (optional)
PagedResourceListOfRunFileResponse result = apiInstance.ListRunFiles(instanceId, runId, page, pageSize);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |
| **runId** | **string** | path | **required** |  |
| **page** | **string?** | query | optional |  Default: `&quot;&quot;` |
| **pageSize** | **int?** | query | optional |  Default: `100` |

### Return type

[PagedResourceListOfRunFileResponse](PagedResourceListOfRunFileResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested TPF instance or run does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRunFilesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfRunFileResponse> response = apiInstance.ListRunFilesWithHttpInfo(instanceId, runId, page, pageSize);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listruntransactions"></a>
## ListRunTransactions

> PagedResourceListOfTransactionResponse ListRunTransactions(string instanceId, string runId, string? status = null, string? page = null, int? pageSize = null)

[EXPERIMENTAL] ListRunTransactions: List Transactions in a run.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var instanceId = "instanceId_example";  // string
var runId = "runId_example";  // string
var status = "status_example";  // string? (optional)
var page = "\"\"";  // string? (optional)
var pageSize = 100;  // int? (optional)
PagedResourceListOfTransactionResponse result = apiInstance.ListRunTransactions(instanceId, runId, status, page, pageSize);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |
| **runId** | **string** | path | **required** |  |
| **status** | **string?** | query | optional |  |
| **page** | **string?** | query | optional |  Default: `&quot;&quot;` |
| **pageSize** | **int?** | query | optional |  Default: `100` |

### Return type

[PagedResourceListOfTransactionResponse](PagedResourceListOfTransactionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested TPF instance or run does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListRunTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTransactionResponse> response = apiInstance.ListRunTransactionsWithHttpInfo(instanceId, runId, status, page, pageSize);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="replaytransactions"></a>
## ReplayTransactions

> ReplayTransactionsResponse ReplayTransactions(string instanceId, ReplayTransactionsRequest replayTransactionsRequest)

[EXPERIMENTAL] ReplayTransactions: Replay one or more transactions through a TPF instance

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var instanceId = "instanceId_example";  // string
var replayTransactionsRequest = new ReplayTransactionsRequest(); // ReplayTransactionsRequest
ReplayTransactionsResponse result = apiInstance.ReplayTransactions(instanceId, replayTransactionsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |
| **replayTransactionsRequest** | [ReplayTransactionsRequest](ReplayTransactionsRequest.md) | body | **required** |  |

### Return type

[ReplayTransactionsResponse](ReplayTransactionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested TPF instance does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReplayTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReplayTransactionsResponse> response = apiInstance.ReplayTransactionsWithHttpInfo(instanceId, replayTransactionsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="retrytpfsftpdelivery"></a>
## RetryTpfSftpDelivery

> TpfRetrySftpResponse RetryTpfSftpDelivery(string instanceId, long fileId)

[EXPERIMENTAL] RetryTpfSftpDelivery: Retry SFTP delivery for a previously sent TPF file

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TradePublicationFrameworkApi>();
var instanceId = "instanceId_example";  // string
var fileId = 789L;  // long
TpfRetrySftpResponse result = apiInstance.RetryTpfSftpDelivery(instanceId, fileId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Integration instance ID |
| **fileId** | **long** | path | **required** | File delivery ID to retry |

### Return type

[TpfRetrySftpResponse](TpfRetrySftpResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Retry succeeded - file re-sent to SFTP |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | File delivery record not found |  -  |
| **409** | Duplicate file detected - same hash already delivered to destination |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RetryTpfSftpDeliveryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TpfRetrySftpResponse> response = apiInstance.RetryTpfSftpDeliveryWithHttpInfo(instanceId, fileId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

