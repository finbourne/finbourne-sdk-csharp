# Finbourne.Sdk.Lusid.Api.TransferAgencyApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CalculateOrderDates**](#calculateorderdates) | **POST** `/api/api/transferagency/orderdates` | [EXPERIMENTAL] CalculateOrderDates: Calculate the key dates associated with transfer agency orders |
| [**DeleteTransferAgencyOrders**](#deletetransferagencyorders) | **POST** `/api/api/transferagency/orders/$delete` | [EXPERIMENTAL] DeleteTransferAgencyOrders: Delete transfer agency orders |
| [**EstimateTransferAgencyOrders**](#estimatetransferagencyorders) | **POST** `/api/api/transferagency/orders/$estimate` | [EXPERIMENTAL] EstimateTransferAgencyOrders: Estimate the values of transfer agency orders |
| [**UpsertTransferAgencyOrders**](#upserttransferagencyorders) | **POST** `/api/api/transferagency/orders` | [EXPERIMENTAL] UpsertTransferAgencyOrders: Upsert transfer agency orders |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransferAgencyApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
```

---

<a id="calculateorderdates"></a>
## CalculateOrderDates

> CalculateOrderDatesResponse CalculateOrderDates(Dictionary<string, CalculateOrderDatesRequest> requestBody)

[EXPERIMENTAL] CalculateOrderDates: Calculate the key dates associated with transfer agency orders

The response contains both the collection of successfully calculated dates and any failed calculations,  each in the form of a dictionary keyed by the request's keys.  For each failure, a reason is provided. It is important to check the failed set for unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
var requestBody = new Dictionary<string, CalculateOrderDatesRequest>(); // Dictionary<string, CalculateOrderDatesRequest>
CalculateOrderDatesResponse result = apiInstance.CalculateOrderDates(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, CalculateOrderDatesRequest&gt;](../Model/CalculateOrderDatesRequest.md) | body | **required** | The request containing the dates used for calculation |

### Return type

[CalculateOrderDatesResponse](../Model/CalculateOrderDatesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully calculated dates and any failed calculations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CalculateOrderDatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CalculateOrderDatesResponse> response = apiInstance.CalculateOrderDatesWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletetransferagencyorders"></a>
## DeleteTransferAgencyOrders

> DeleteTransferAgencyOrdersResponse DeleteTransferAgencyOrders(Dictionary<string, DeleteTransferAgencyOrderRequest> requestBody)

[EXPERIMENTAL] DeleteTransferAgencyOrders: Delete transfer agency orders

Deletes each order supplied, cancelling any cash transaction(s) already booked for it. Only an order in  'New' or 'Pending' can be deleted. A priced order must be un-priced first. An order with no cash transaction  booked against it is deleted successfully and reports no cancelled transactions. Transaction staging rules are not applied to these  cancellations.  The response contains both successfully deleted orders and any failures, each in the form of a  dictionary keyed by the request's keys. For each failure, a reason is provided. It is important to  check the failed set for unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
var requestBody = new Dictionary<string, DeleteTransferAgencyOrderRequest>(); // Dictionary<string, DeleteTransferAgencyOrderRequest>
DeleteTransferAgencyOrdersResponse result = apiInstance.DeleteTransferAgencyOrders(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, DeleteTransferAgencyOrderRequest&gt;](../Model/DeleteTransferAgencyOrderRequest.md) | body | **required** | The transfer agency orders to delete, keyed by a unique request identifier. |

### Return type

[DeleteTransferAgencyOrdersResponse](../Model/DeleteTransferAgencyOrdersResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully deleted orders and any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteTransferAgencyOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeleteTransferAgencyOrdersResponse> response = apiInstance.DeleteTransferAgencyOrdersWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="estimatetransferagencyorders"></a>
## EstimateTransferAgencyOrders

> EstimateTransferAgencyOrdersResponse EstimateTransferAgencyOrders(Dictionary<string, EstimateTransferAgencyOrderRequest> requestBody)

[EXPERIMENTAL] EstimateTransferAgencyOrders: Estimate the values of transfer agency orders

Estimates the units and the cash each order supplied would move, from the share class's most recent price.  Nothing is written.                An order may be named by its identifier, to estimate it as it stands, or supplied whole, to estimate values  that have not been saved yet. Both forms may appear in the same request. Where an order is supplied whole,  those values are estimated in place of the saved order's.                A switch or a transfer is two orders, and each leg is estimated independently.                The price is reported in the currency the share class is quoted in, which is not necessarily the order's  currency, so it is returned alongside that currency and the rate used.                The response contains both the successful estimates and any failures, each in the form of a dictionary  keyed by the request's keys. A share class with no price available fails only its own orders. It is  important to check the failed set for unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
var requestBody = new Dictionary<string, EstimateTransferAgencyOrderRequest>(); // Dictionary<string, EstimateTransferAgencyOrderRequest>
EstimateTransferAgencyOrdersResponse result = apiInstance.EstimateTransferAgencyOrders(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, EstimateTransferAgencyOrderRequest&gt;](../Model/EstimateTransferAgencyOrderRequest.md) | body | **required** | The transfer agency orders to estimate, keyed by a unique request identifier. |

### Return type

[EstimateTransferAgencyOrdersResponse](../Model/EstimateTransferAgencyOrdersResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully estimated orders and any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the EstimateTransferAgencyOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EstimateTransferAgencyOrdersResponse> response = apiInstance.EstimateTransferAgencyOrdersWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttransferagencyorders"></a>
## UpsertTransferAgencyOrders

> TransferAgencyOrdersResponse UpsertTransferAgencyOrders(Dictionary<string, UpsertTransferAgencyOrderRequest> requestBody)

[EXPERIMENTAL] UpsertTransferAgencyOrders: Upsert transfer agency orders

Creates a transaction and updates the relevant order for each order supplied.  The response contains both successfully processed orders and any failures, each in the form of a  dictionary keyed by the request's keys. For each failure, a reason is provided. It is important to  check the failed set for unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
var requestBody = new Dictionary<string, UpsertTransferAgencyOrderRequest>(); // Dictionary<string, UpsertTransferAgencyOrderRequest>
TransferAgencyOrdersResponse result = apiInstance.UpsertTransferAgencyOrders(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, UpsertTransferAgencyOrderRequest&gt;](../Model/UpsertTransferAgencyOrderRequest.md) | body | **required** | The transfer agency orders to upsert, keyed by a unique request identifier. |

### Return type

[TransferAgencyOrdersResponse](../Model/TransferAgencyOrdersResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully processed orders and any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTransferAgencyOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransferAgencyOrdersResponse> response = apiInstance.UpsertTransferAgencyOrdersWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

