# Finbourne.Sdk.Lusid.Api.InstrumentEventsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**QueryApplicableInstrumentEvents**](#queryapplicableinstrumentevents) | **POST** `/api/api/instrumentevents/$queryApplicableInstrumentEvents` | QueryApplicableInstrumentEvents: Returns a list of applicable instrument events based on the holdings of the portfolios and date range specified in the query. |
| [**QueryBucketCashFlowDrillDown**](#querybucketcashflowdrilldown) | **POST** `/api/api/instrumentevents/$queryBucketCashFlowDrillDown` | QueryBucketCashFlowDrillDown: Returns the individual cashflows that make up a single cashflow bucket, with their source lineage. |
| [**QueryBucketedCashFlows**](#querybucketedcashflows) | **POST** `/api/api/instrumentevents/$queryBucketedCashFlows` | QueryBucketedCashFlows: Returns bucketed cashflows based on the holdings of the portfolios and date range specified in the query. |
| [**QueryCashFlows**](#querycashflows) | **POST** `/api/api/instrumentevents/$queryCashFlows` | QueryCashFlows: Returns a list of cashflows based on the holdings of the portfolios and date range specified in the query. |
| [**QueryInstrumentEvents**](#queryinstrumentevents) | **POST** `/api/api/instrumentevents/$query` | QueryInstrumentEvents: Returns a list of instrument events based on the holdings of the portfolios and date range specified in the query. |
| [**QueryTradeTickets**](#querytradetickets) | **POST** `/api/api/instrumentevents/$queryTradeTickets` | QueryTradeTickets: Returns a list of trade tickets based on the holdings of the portfolios and date range specified in the query. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<InstrumentEventsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
```

---

<a id="queryapplicableinstrumentevents"></a>
## QueryApplicableInstrumentEvents

> ResourceListOfApplicableInstrumentEvent QueryApplicableInstrumentEvents(DateTimeOffset? asAt = null, int? limit = null, string? page = null, QueryApplicableInstrumentEventsRequest? queryApplicableInstrumentEventsRequest = null)

QueryApplicableInstrumentEvents: Returns a list of applicable instrument events based on the holdings of the portfolios and date range specified in the query.

Returns a list of applicable instrument events based on the holdings of the portfolios and date range specified in the query.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 100;  // int? (optional)
var page = "page_example";  // string? (optional)
var queryApplicableInstrumentEventsRequest = new QueryApplicableInstrumentEventsRequest?(); // QueryApplicableInstrumentEventsRequest? (optional)
ResourceListOfApplicableInstrumentEvent result = apiInstance.QueryApplicableInstrumentEvents(asAt, limit, page, queryApplicableInstrumentEventsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The as at time to use. |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. If not specified, a default  of 100 is used. Default: `100` |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing items from a previous call. Page values are  return from list calls, and must be supplied exactly as returned. Additionally, when specifying this |
| **queryApplicableInstrumentEventsRequest** | [QueryApplicableInstrumentEventsRequest?](../Model/QueryApplicableInstrumentEventsRequest?.md) | body | optional | The filter parameters used to retrieve applicable instrument events. |

### Return type

[ResourceListOfApplicableInstrumentEvent](../Model/ResourceListOfApplicableInstrumentEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Applicable Instrument Events |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryApplicableInstrumentEventsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfApplicableInstrumentEvent> response = apiInstance.QueryApplicableInstrumentEventsWithHttpInfo(asAt, limit, page, queryApplicableInstrumentEventsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="querybucketcashflowdrilldown"></a>
## QueryBucketCashFlowDrillDown

> ResourceListOfCashFlowDetail QueryBucketCashFlowDrillDown(QueryBucketCashFlowDrillDownRequest? queryBucketCashFlowDrillDownRequest = null)

QueryBucketCashFlowDrillDown: Returns the individual cashflows that make up a single cashflow bucket, with their source lineage.

Returns the individual cashflows inside the requested bucket window for the holdings of the specified  portfolios, annotated with the source (Instrument, Transaction or SRS) that produced each cashflow.                The drill-down returns the complete resolved stream, including transaction-sourced cashflows, which  bucketed responses using the (default) InstrumentCashFlow representation exclude. To reconcile the  drill-down against such a bucketed response, first exclude rows with a sourceType of 'Transaction'.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
var queryBucketCashFlowDrillDownRequest = new QueryBucketCashFlowDrillDownRequest?(); // QueryBucketCashFlowDrillDownRequest? (optional)
ResourceListOfCashFlowDetail result = apiInstance.QueryBucketCashFlowDrillDown(queryBucketCashFlowDrillDownRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **queryBucketCashFlowDrillDownRequest** | [QueryBucketCashFlowDrillDownRequest?](../Model/QueryBucketCashFlowDrillDownRequest?.md) | body | optional | The Query Information. |

### Return type

[ResourceListOfCashFlowDetail](../Model/ResourceListOfCashFlowDetail.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The individual cashflows inside the requested bucket. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryBucketCashFlowDrillDownWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfCashFlowDetail> response = apiInstance.QueryBucketCashFlowDrillDownWithHttpInfo(queryBucketCashFlowDrillDownRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="querybucketedcashflows"></a>
## QueryBucketedCashFlows

> BucketedCashFlowResponse QueryBucketedCashFlows(QueryBucketedCashFlowsRequest? queryBucketedCashFlowsRequest = null)

QueryBucketedCashFlows: Returns bucketed cashflows based on the holdings of the portfolios and date range specified in the query.

Returns bucketed cashflows based on the holdings of the portfolios and date range specified in the query.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
var queryBucketedCashFlowsRequest = new QueryBucketedCashFlowsRequest?(); // QueryBucketedCashFlowsRequest? (optional)
BucketedCashFlowResponse result = apiInstance.QueryBucketedCashFlows(queryBucketedCashFlowsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **queryBucketedCashFlowsRequest** | [QueryBucketedCashFlowsRequest?](../Model/QueryBucketedCashFlowsRequest?.md) | body | optional | The Query Information. |

### Return type

[BucketedCashFlowResponse](../Model/BucketedCashFlowResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Query bucketed cashflows across portfolios. |  * Deprecation - Only present when the request resolved to cashFlowCalculationVersion&#x3D;1 (explicitly or by default): an RFC 9745 structured-field date marking when version 1 was deprecated. Set cashFlowCalculationVersion&#x3D;2, its successor. <br>  * Link - Only present when the request resolved to cashFlowCalculationVersion&#x3D;1: an RFC 8288 link with rel&#x3D;\&quot;deprecation\&quot; pointing at the version 1 to version 2 migration documentation. <br>  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryBucketedCashFlowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BucketedCashFlowResponse> response = apiInstance.QueryBucketedCashFlowsWithHttpInfo(queryBucketedCashFlowsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="querycashflows"></a>
## QueryCashFlows

> ResourceListOfInstrumentCashFlow QueryCashFlows(int? limit = null, string? page = null, QueryCashFlowsRequest? queryCashFlowsRequest = null)

QueryCashFlows: Returns a list of cashflows based on the holdings of the portfolios and date range specified in the query.

Returns a list of cashflows based on the holdings of the portfolios and date range specified in the query.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
var limit = 1000;  // int? (optional)
var page = "page_example";  // string? (optional)
var queryCashFlowsRequest = new QueryCashFlowsRequest?(); // QueryCashFlowsRequest? (optional)
ResourceListOfInstrumentCashFlow result = apiInstance.QueryCashFlows(limit, page, queryCashFlowsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. If not specified, a default  of 1000 is used. Default: `1000` |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing items from a previous call. Page values are  return from list calls, and must be supplied exactly as returned. Additionally, when specifying this  value, queryBody, and limit must not  be modified. |
| **queryCashFlowsRequest** | [QueryCashFlowsRequest?](../Model/QueryCashFlowsRequest?.md) | body | optional | The filter parameters used to retrieve instrument events. |

### Return type

[ResourceListOfInstrumentCashFlow](../Model/ResourceListOfInstrumentCashFlow.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instrument Events as Cashflows. |  * Deprecation - Only present when the request resolved to cashFlowCalculationVersion&#x3D;1 (explicitly or by default): an RFC 9745 structured-field date marking when version 1 was deprecated. Set cashFlowCalculationVersion&#x3D;2, its successor. <br>  * Link - Only present when the request resolved to cashFlowCalculationVersion&#x3D;1: an RFC 8288 link with rel&#x3D;\&quot;deprecation\&quot; pointing at the version 1 to version 2 migration documentation. <br>  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryCashFlowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfInstrumentCashFlow> response = apiInstance.QueryCashFlowsWithHttpInfo(limit, page, queryCashFlowsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="queryinstrumentevents"></a>
## QueryInstrumentEvents

> ResourceListOfInstrumentEventHolder QueryInstrumentEvents(int? limit = null, string? page = null, QueryInstrumentEventsRequest? queryInstrumentEventsRequest = null)

QueryInstrumentEvents: Returns a list of instrument events based on the holdings of the portfolios and date range specified in the query.

Returns a list of instrument events based on the holdings of the portfolios and date range specified in the query.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
var limit = 1000;  // int? (optional)
var page = "page_example";  // string? (optional)
var queryInstrumentEventsRequest = new QueryInstrumentEventsRequest?(); // QueryInstrumentEventsRequest? (optional)
ResourceListOfInstrumentEventHolder result = apiInstance.QueryInstrumentEvents(limit, page, queryInstrumentEventsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. If not specified, a default  of 1000 is used. Default: `1000` |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing items from a previous call. Page values are  return from list calls, and must be supplied exactly as returned. Additionally, when specifying this  value, queryBody, and limit must not  be modified. |
| **queryInstrumentEventsRequest** | [QueryInstrumentEventsRequest?](../Model/QueryInstrumentEventsRequest?.md) | body | optional | The filter parameters used to retrieve instrument events. |

### Return type

[ResourceListOfInstrumentEventHolder](../Model/ResourceListOfInstrumentEventHolder.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instrument Events |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryInstrumentEventsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfInstrumentEventHolder> response = apiInstance.QueryInstrumentEventsWithHttpInfo(limit, page, queryInstrumentEventsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="querytradetickets"></a>
## QueryTradeTickets

> ResourceListOfPortfolioTradeTicket QueryTradeTickets(int? limit = null, string? page = null, QueryTradeTicketsRequest? queryTradeTicketsRequest = null)

QueryTradeTickets: Returns a list of trade tickets based on the holdings of the portfolios and date range specified in the query.

Returns a list of trade tickets based on the holdings of the portfolios and date range specified in the query.    These trade tickets are derived from events that involve transition of instrument states, such as transitions  on exercise or default of an instrument. The trade tickets are to allow the new position to be created given the  existing portfolio configuration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentEventsApi>();
var limit = 1000;  // int? (optional)
var page = "page_example";  // string? (optional)
var queryTradeTicketsRequest = new QueryTradeTicketsRequest?(); // QueryTradeTicketsRequest? (optional)
ResourceListOfPortfolioTradeTicket result = apiInstance.QueryTradeTickets(limit, page, queryTradeTicketsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. If not specified, a default  of 1000 is used. Default: `1000` |
| **page** | **string?** | query | optional | Optional. The pagination token to use to continue listing items from a previous call. Page values are  return from list calls, and must be supplied exactly as returned. Additionally, when specifying this  value, queryBody, and limit must not  be modified. |
| **queryTradeTicketsRequest** | [QueryTradeTicketsRequest?](../Model/QueryTradeTicketsRequest?.md) | body | optional | The filter parameters used to retrieve instrument events. |

### Return type

[ResourceListOfPortfolioTradeTicket](../Model/ResourceListOfPortfolioTradeTicket.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Instrument Events as Upsertable TradeTickets. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryTradeTicketsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPortfolioTradeTicket> response = apiInstance.QueryTradeTicketsWithHttpInfo(limit, page, queryTradeTicketsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

