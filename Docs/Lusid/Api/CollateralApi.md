# Finbourne.Sdk.Lusid.Api.CollateralApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AcceptMarginCall**](#acceptmargincall) | **POST** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$accept` | [EXPERIMENTAL] AcceptMarginCall: Accept a margin call. |
| [**BatchAcceptMarginCalls**](#batchacceptmargincalls) | **POST** `/api/api/collateral/margincalls/$batchAccept` | [EXPERIMENTAL] BatchAcceptMarginCalls: Accept several margin calls. |
| [**DisputeMarginCall**](#disputemargincall) | **POST** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$dispute` | [EXPERIMENTAL] DisputeMarginCall: Dispute a margin call. |
| [**GetMarginCall**](#getmargincall) | **GET** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}` | [EXPERIMENTAL] GetMarginCall: Get a margin call. |
| [**GetMarginRun**](#getmarginrun) | **GET** `/api/api/collateral/runs/{runId}` | [EXPERIMENTAL] GetMarginRun: Get a margin run. |
| [**ListMarginCallLines**](#listmargincalllines) | **GET** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/lines` | [EXPERIMENTAL] ListMarginCallLines: List the margin lines of a call. |
| [**ListMarginCalls**](#listmargincalls) | **GET** `/api/api/collateral/margincalls` | [EXPERIMENTAL] ListMarginCalls: List margin calls. |
| [**ListMarginLines**](#listmarginlines) | **GET** `/api/api/collateral/runs/{runId}/lines` | [EXPERIMENTAL] ListMarginLines: List the margin lines of a run. |
| [**ListMarginRuns**](#listmarginruns) | **GET** `/api/api/collateral/runs` | [EXPERIMENTAL] ListMarginRuns: List margin runs. |
| [**RecordCounterpartyDemand**](#recordcounterpartydemand) | **POST** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$recordCounterpartyDemand` | [EXPERIMENTAL] RecordCounterpartyDemand: Record the counterparty&#39;s demand against a margin call. |
| [**RetryMarginRun**](#retrymarginrun) | **POST** `/api/api/collateral/runs/{runId}/$retry` | [EXPERIMENTAL] RetryMarginRun: Retry a margin run. |
| [**RunMarginCalculation**](#runmargincalculation) | **POST** `/api/api/collateral/$run` | [EXPERIMENTAL] RunMarginCalculation: Run the margin calculation. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CollateralApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
```

---

<a id="acceptmargincall"></a>
## AcceptMarginCall

> MarginCall AcceptMarginCall(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction, AcceptMarginCallRequest? acceptMarginCallRequest = null)

[EXPERIMENTAL] AcceptMarginCall: Accept a margin call.

Accept a margin call at the agreed amount: our figure when matched, the counterparty's when within tolerance, or  the amount given, which is required when the demand breaks tolerance or has not been recorded. Allowed from the  calculated and disputed states.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
var acceptMarginCallRequest = new AcceptMarginCallRequest?(); // AcceptMarginCallRequest? (optional)
MarginCall result = apiInstance.AcceptMarginCall(runId, agreementScope, agreementCode, item, marginType, direction, acceptMarginCallRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. Currently VariationMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |
| **acceptMarginCallRequest** | [AcceptMarginCallRequest?](../Model/AcceptMarginCallRequest?.md) | body | optional | The amount to accept, when the default does not apply. |

### Return type

[MarginCall](../Model/MarginCall.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The accepted margin call. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AcceptMarginCallWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginCall> response = apiInstance.AcceptMarginCallWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction, acceptMarginCallRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchacceptmargincalls"></a>
## BatchAcceptMarginCalls

> BatchAcceptMarginCallsResponse BatchAcceptMarginCalls(BatchAcceptMarginCallsRequest batchAcceptMarginCallsRequest)

[EXPERIMENTAL] BatchAcceptMarginCalls: Accept several margin calls.

Accept each of the given margin calls at its default agreed amount. A call that cannot be accepted is reported  in the response and does not stop the others.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var batchAcceptMarginCallsRequest = new BatchAcceptMarginCallsRequest(); // BatchAcceptMarginCallsRequest
BatchAcceptMarginCallsResponse result = apiInstance.BatchAcceptMarginCalls(batchAcceptMarginCallsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **batchAcceptMarginCallsRequest** | [BatchAcceptMarginCallsRequest](../Model/BatchAcceptMarginCallsRequest.md) | body | **required** | The margin calls to accept. |

### Return type

[BatchAcceptMarginCallsResponse](../Model/BatchAcceptMarginCallsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The calls accepted, and those that could not be. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchAcceptMarginCallsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchAcceptMarginCallsResponse> response = apiInstance.BatchAcceptMarginCallsWithHttpInfo(batchAcceptMarginCallsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="disputemargincall"></a>
## DisputeMarginCall

> MarginCall DisputeMarginCall(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction, DisputeMarginCallRequest disputeMarginCallRequest)

[EXPERIMENTAL] DisputeMarginCall: Dispute a margin call.

Dispute a margin call: move the agreed amount now and leave the rest of the counterparty's demand in dispute,  with a reason and an owner. Allowed from the calculated and accepted states.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
var disputeMarginCallRequest = new DisputeMarginCallRequest(); // DisputeMarginCallRequest
MarginCall result = apiInstance.DisputeMarginCall(runId, agreementScope, agreementCode, item, marginType, direction, disputeMarginCallRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. Currently VariationMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |
| **disputeMarginCallRequest** | [DisputeMarginCallRequest](../Model/DisputeMarginCallRequest.md) | body | **required** | The amount to move now, the reason and the owner. |

### Return type

[MarginCall](../Model/MarginCall.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The disputed margin call. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DisputeMarginCallWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginCall> response = apiInstance.DisputeMarginCallWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction, disputeMarginCallRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmargincall"></a>
## GetMarginCall

> MarginCall GetMarginCall(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction)

[EXPERIMENTAL] GetMarginCall: Get a margin call.

Retrieve one margin call of a run by its business key.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
MarginCall result = apiInstance.GetMarginCall(runId, agreementScope, agreementCode, item, marginType, direction);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. Currently VariationMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |

### Return type

[MarginCall](../Model/MarginCall.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested margin call. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMarginCallWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginCall> response = apiInstance.GetMarginCallWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmarginrun"></a>
## GetMarginRun

> MarginRun GetMarginRun(string runId)

[EXPERIMENTAL] GetMarginRun: Get a margin run.

Retrieve a margin run with its progress: the status of each shard, the calls and lines published so far, and  anything it could not value.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
MarginRun result = apiInstance.GetMarginRun(runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |

### Return type

[MarginRun](../Model/MarginRun.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested margin run. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMarginRunWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginRun> response = apiInstance.GetMarginRunWithHttpInfo(runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmargincalllines"></a>
## ListMarginCallLines

> PagedResourceListOfMarginLine ListMarginCallLines(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListMarginCallLines: List the margin lines of a call.

List the holding lines behind one margin call: our side of the figure the counterparty's statement is matched against.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfMarginLine result = apiInstance.ListMarginCallLines(runId, agreementScope, agreementCode, item, marginType, direction, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. Currently VariationMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing margin lines; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are PortfolioId.Scope, PortfolioId.Code, HoldingId, CustodianAccountScope, CustodianAccountCode, CustodianAccountName, Units, Pv, VariationMargin and CollateralValue. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |

### Return type

[PagedResourceListOfMarginLine](../Model/PagedResourceListOfMarginLine.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested margin lines. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMarginCallLinesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfMarginLine> response = apiInstance.ListMarginCallLinesWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmargincalls"></a>
## ListMarginCalls

> PagedResourceListOfMarginCall ListMarginCalls(DateTimeOrCutLabel? effectiveAt = null, string? runId = null, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListMarginCalls: List margin calls.

List the margin calls of one run when a run id is given. Otherwise list the current calls for a business date:  those of the latest run for the date, with an agreement that run could not value served from the most recent run  that did. Restricted to the agreements the caller may read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var runId = "runId_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfMarginCall result = apiInstance.ListMarginCalls(effectiveAt, runId, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The business date, datetime or cut label to list the current margin calls for. Defaults to today if not specified. Ignored when a run id is given. |
| **runId** | **string?** | query | optional | The identifier of the margin run to list the calls of. Lists the current calls for the business date if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing margin calls; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are RunId, AgreementId.Scope, AgreementId.Code, Counterparty.Code, Counterparty.IdTypeScope, Counterparty.IdTypeCode, Item, MarginType, Method, Settlement, Direction, Currency, Required, Held, Call, CounterpartyDemand, Difference, MatchStatus, AgreedAmount, DisputedAmount, DisputeOwner, State and Deadline. For example, to find the breaks, specify \&quot;MatchStatus eq &#39;Break&#39;\&quot;. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |

### Return type

[PagedResourceListOfMarginCall](../Model/PagedResourceListOfMarginCall.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested margin calls. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMarginCallsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfMarginCall> response = apiInstance.ListMarginCallsWithHttpInfo(effectiveAt, runId, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmarginlines"></a>
## ListMarginLines

> PagedResourceListOfMarginLine ListMarginLines(string runId, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListMarginLines: List the margin lines of a run.

List the holding lines behind every margin call of a run, restricted to the agreements the caller may read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfMarginLine result = apiInstance.ListMarginLines(runId, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing margin lines; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are AgreementId.Scope, AgreementId.Code, Item, PortfolioId.Scope, PortfolioId.Code, HoldingId, CustodianAccountScope, CustodianAccountCode, CustodianAccountName, Units, Pv, VariationMargin and CollateralValue. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |

### Return type

[PagedResourceListOfMarginLine](../Model/PagedResourceListOfMarginLine.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested margin lines. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMarginLinesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfMarginLine> response = apiInstance.ListMarginLinesWithHttpInfo(runId, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmarginruns"></a>
## ListMarginRuns

> PagedResourceListOfMarginRun ListMarginRuns(string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListMarginRuns: List margin runs.

List the margin runs on record, most recent first.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfMarginRun result = apiInstance.ListMarginRuns(page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing margin runs; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are Id, EffectiveAt, AsAt, Status, CallCount and LineCount. For example, to find the runs for a business date, specify \&quot;EffectiveAt eq 2026-09-04\&quot;. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |

### Return type

[PagedResourceListOfMarginRun](../Model/PagedResourceListOfMarginRun.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested margin runs. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMarginRunsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfMarginRun> response = apiInstance.ListMarginRunsWithHttpInfo(page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="recordcounterpartydemand"></a>
## RecordCounterpartyDemand

> MarginCall RecordCounterpartyDemand(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction, RecordCounterpartyDemandRequest recordCounterpartyDemandRequest)

[EXPERIMENTAL] RecordCounterpartyDemand: Record the counterparty's demand against a margin call.

Record the counterparty's figure for a margin call and match it to ours: equal is matched, a difference within the  agreement's tolerance is within tolerance, and a larger difference is a break. The call's state is not changed,  except that a call already accepted or disputed returns to calculated when its demand changes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
var recordCounterpartyDemandRequest = new RecordCounterpartyDemandRequest(); // RecordCounterpartyDemandRequest
MarginCall result = apiInstance.RecordCounterpartyDemand(runId, agreementScope, agreementCode, item, marginType, direction, recordCounterpartyDemandRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. Currently VariationMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |
| **recordCounterpartyDemandRequest** | [RecordCounterpartyDemandRequest](../Model/RecordCounterpartyDemandRequest.md) | body | **required** | The counterparty&#39;s demand. |

### Return type

[MarginCall](../Model/MarginCall.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The margin call with the demand matched against it. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RecordCounterpartyDemandWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginCall> response = apiInstance.RecordCounterpartyDemandWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction, recordCounterpartyDemandRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="retrymarginrun"></a>
## RetryMarginRun

> MarginRun RetryMarginRun(string runId)

[EXPERIMENTAL] RetryMarginRun: Retry a margin run.

Value the failed shards of a completed margin run again, at the run's asAt. Refused while the run is in progress  or when no shard failed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
MarginRun result = apiInstance.RetryMarginRun(runId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |

### Return type

[MarginRun](../Model/MarginRun.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The margin run with its failed shards pending again. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RetryMarginRunWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginRun> response = apiInstance.RetryMarginRunWithHttpInfo(runId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="runmargincalculation"></a>
## RunMarginCalculation

> MarginRun RunMarginCalculation(MarginRunRequest marginRunRequest)

[EXPERIMENTAL] RunMarginCalculation: Run the margin calculation.

Value the collateral agreements for a business date in the background and publish their margin calls as a run.  The run is returned as planned; poll GetMarginRun for its progress, and list its calls as they are published.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var marginRunRequest = new MarginRunRequest(); // MarginRunRequest
MarginRun result = apiInstance.RunMarginCalculation(marginRunRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **marginRunRequest** | [MarginRunRequest](../Model/MarginRunRequest.md) | body | **required** | The business date to value, and optionally the asAt and the agreements to include. |

### Return type

[MarginRun](../Model/MarginRun.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The margin run as planned. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunMarginCalculationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginRun> response = apiInstance.RunMarginCalculationWithHttpInfo(marginRunRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

