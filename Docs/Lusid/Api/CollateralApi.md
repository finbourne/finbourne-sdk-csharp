# Finbourne.Sdk.Lusid.Api.CollateralApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AcceptMarginCall**](#acceptmargincall) | **POST** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$accept` | [EXPERIMENTAL] AcceptMarginCall: Accept a margin call. |
| [**BatchAcceptMarginCalls**](#batchacceptmargincalls) | **POST** `/api/api/collateral/margincalls/$batchAccept` | [EXPERIMENTAL] BatchAcceptMarginCalls: Accept several margin calls. |
| [**DisputeMarginCall**](#disputemargincall) | **POST** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$dispute` | [EXPERIMENTAL] DisputeMarginCall: Dispute a margin call. |
| [**GetMarginCall**](#getmargincall) | **GET** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}` | [EXPERIMENTAL] GetMarginCall: Get a margin call. |
| [**GetMarginCallAllocation**](#getmargincallallocation) | **GET** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$allocation` | [EXPERIMENTAL] GetMarginCallAllocation: [EXPERIMENTAL] GetMarginCallAllocation: Get the collateral proposed for a margin call. |
| [**GetMarginCallExplanation**](#getmargincallexplanation) | **GET** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$explain` | [EXPERIMENTAL] GetMarginCallExplanation: Explain a margin call. |
| [**GetMarginLineExplanation**](#getmarginlineexplanation) | **GET** `/api/api/collateral/runs/{runId}/lines/{lineKey}/$explain` | [EXPERIMENTAL] GetMarginLineExplanation: Explain a margin line. |
| [**GetMarginRun**](#getmarginrun) | **GET** `/api/api/collateral/runs/{runId}` | [EXPERIMENTAL] GetMarginRun: Get a margin run. |
| [**ListMarginCallLines**](#listmargincalllines) | **GET** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/lines` | [EXPERIMENTAL] ListMarginCallLines: List the margin lines of a call. |
| [**ListMarginCalls**](#listmargincalls) | **GET** `/api/api/collateral/margincalls` | [EXPERIMENTAL] ListMarginCalls: List margin calls. |
| [**ListMarginLines**](#listmarginlines) | **GET** `/api/api/collateral/runs/{runId}/lines` | [EXPERIMENTAL] ListMarginLines: List the margin lines of a run. |
| [**ListMarginRunRecommendations**](#listmarginrunrecommendations) | **GET** `/api/api/collateral/runs/{runId}/recommendations` | [EXPERIMENTAL] ListMarginRunRecommendations: List a margin run&#39;s netting recommendations. |
| [**ListMarginRuns**](#listmarginruns) | **GET** `/api/api/collateral/runs` | [EXPERIMENTAL] ListMarginRuns: List margin runs. |
| [**ListNettingRecommendations**](#listnettingrecommendations) | **GET** `/api/api/collateral/recommendations` | [EXPERIMENTAL] ListNettingRecommendations: List the current netting recommendations. |
| [**RankMarginCall**](#rankmargincall) | **POST** `/api/api/collateral/margincalls/{runId}/{agreementScope}/{agreementCode}/{item}/{marginType}/{direction}/$rank` | [EXPERIMENTAL] RankMarginCall: [EXPERIMENTAL] RankMarginCall: Rank the collateral for a margin call again, with the caller&#39;s choices. |
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

<a id="getmargincallallocation"></a>
## GetMarginCallAllocation

> CollateralAllocation GetMarginCallAllocation(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction)

[EXPERIMENTAL] GetMarginCallAllocation: [EXPERIMENTAL] GetMarginCallAllocation: Get the collateral proposed for a margin call.

Retrieve the assets the run's allocation pass proposes to deliver for the call, or to take back for a return, with  every holding it considered and either its rank or the constraint that excluded it. Each line carries what a  transaction moving it needs: the instrument, the portfolio and custodian account, the units, the price and the  consideration. Not found until the run's allocation pass has completed, or when the call moves no collateral of ours.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
CollateralAllocation result = apiInstance.GetMarginCallAllocation(runId, agreementScope, agreementCode, item, marginType, direction);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. One of VariationMargin or InitialMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |

### Return type

[CollateralAllocation](../Model/CollateralAllocation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The collateral proposed for the margin call. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMarginCallAllocationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CollateralAllocation> response = apiInstance.GetMarginCallAllocationWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmargincallexplanation"></a>
## GetMarginCallExplanation

> MarginExplanation GetMarginCallExplanation(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction)

[EXPERIMENTAL] GetMarginCallExplanation: Explain a margin call.

Show how the required amount of one initial-margin call of a run was arrived at, as a tree of components. Only an  initial-margin call whose run stored its working can be explained, as the call's ExplainAvailable says. The working  of portfolios the caller may not read is replaced by a single redacted component that keeps its parent adding up.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
MarginExplanation result = apiInstance.GetMarginCallExplanation(runId, agreementScope, agreementCode, item, marginType, direction);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. Only InitialMargin calls can be explained. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |

### Return type

[MarginExplanation](../Model/MarginExplanation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | How the call&#39;s required amount was arrived at. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMarginCallExplanationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginExplanation> response = apiInstance.GetMarginCallExplanationWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmarginlineexplanation"></a>
## GetMarginLineExplanation

> MarginExplanation GetMarginLineExplanation(string runId, string lineKey, string? figure = null)

[EXPERIMENTAL] GetMarginLineExplanation: Explain a margin line.

Show how the figures of one margin line of a run were arrived at, as a tree of components for each figure. The run  must have stored its working, as its lines' ExplainAvailable says. The working of portfolios the caller may not  read is replaced by a single redacted component that keeps its parent adding up. A line the caller may not read is  reported as not found.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var lineKey = "lineKey_example";  // string
var figure = "figure_example";  // string? (optional)
MarginExplanation result = apiInstance.GetMarginLineExplanation(runId, lineKey, figure);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **lineKey** | **string** | path | **required** | The key of the margin line, as listed in the line&#39;s LineKey. |
| **figure** | **string?** | query | optional | The figure of the line to explain: VariationMargin or InitialMargin. Explains every figure of the line that the run explained if not specified. Available values: VariationMargin, InitialMargin. |

### Return type

[MarginExplanation](../Model/MarginExplanation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | How the line&#39;s figures were arrived at. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMarginLineExplanationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarginExplanation> response = apiInstance.GetMarginLineExplanationWithHttpInfo(runId, lineKey, figure);
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

> PagedResourceListOfMarginCall ListMarginCalls(DateTimeOrCutLabel? effectiveAt = null, string? runId = null, string? page = null, int? limit = null, string? filter = null, List<string>? scenarios = null, DateTimeOrCutLabel? effectiveFrom = null)

[EXPERIMENTAL] ListMarginCalls: List margin calls.

List the margin calls of one run when a run id is given. Otherwise list the current calls for a business date:  those of the latest run for the date, with an agreement that run could not value served from the most recent run  that did. With an effectiveFrom the current calls of each date from it to effectiveAt are listed, in date order.  Restricted to the agreements the caller may read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var runId = "runId_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var scenarios = new List<string>?(); // List<string>? (optional)
var effectiveFrom = "effectiveFrom_example";  // DateTimeOrCutLabel? (optional)
PagedResourceListOfMarginCall result = apiInstance.ListMarginCalls(effectiveAt, runId, page, limit, filter, scenarios, effectiveFrom);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The business date, datetime or cut label to list the current margin calls for, or the last date of the range when effectiveFrom is given. Defaults to today if not specified. Ignored when a run id is given. |
| **runId** | **string?** | query | optional | The identifier of the margin run to list the calls of. Lists the current calls for the business date if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing margin calls; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are RunId, AgreementId.Scope, AgreementId.Code, Counterparty.Code, Counterparty.IdTypeScope, Counterparty.IdTypeCode, Item, MarginType, Method, Settlement, Direction, Currency, Required, Held, Call, CounterpartyDemand, Difference, MatchStatus, AgreedAmount, DisputedAmount, DisputeOwner, State and Deadline. For example, to find the breaks, specify \&quot;MatchStatus eq &#39;Break&#39;\&quot;. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **scenarios** | [List&lt;string&gt;?](../Model/string.md) | query | optional | The scenarios, each as scope/code, whose calls are listed beside the base case calls, which are always listed. Lists the base case calls only if not specified. |
| **effectiveFrom** | **DateTimeOrCutLabel?** | query | optional | The first business date, datetime or cut label of a range ending at effectiveAt, for a time series of calls. Lists the one business date if not specified. Ignored when a run id is given. |

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
ApiResponse<PagedResourceListOfMarginCall> response = apiInstance.ListMarginCallsWithHttpInfo(effectiveAt, runId, page, limit, filter, scenarios, effectiveFrom);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmarginlines"></a>
## ListMarginLines

> PagedResourceListOfMarginLine ListMarginLines(string runId, string? page = null, int? limit = null, string? filter = null, List<string>? scenarios = null)

[EXPERIMENTAL] ListMarginLines: List the margin lines of a run.

List the holding lines behind every margin call of a run, restricted to the agreements the caller may read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var scenarios = new List<string>?(); // List<string>? (optional)
PagedResourceListOfMarginLine result = apiInstance.ListMarginLines(runId, page, limit, filter, scenarios);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing margin lines; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are AgreementId.Scope, AgreementId.Code, Item, PortfolioId.Scope, PortfolioId.Code, HoldingId, CustodianAccountScope, CustodianAccountCode, CustodianAccountName, Units, Pv, VariationMargin and CollateralValue. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **scenarios** | [List&lt;string&gt;?](../Model/string.md) | query | optional | The scenarios, each as scope/code, whose lines are listed beside the base case lines, which are always listed. Lists the base case lines only if not specified. |

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
ApiResponse<PagedResourceListOfMarginLine> response = apiInstance.ListMarginLinesWithHttpInfo(runId, page, limit, filter, scenarios);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listmarginrunrecommendations"></a>
## ListMarginRunRecommendations

> PagedResourceListOfNettingRecommendation ListMarginRunRecommendations(string runId, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListMarginRunRecommendations: List a margin run's netting recommendations.

List the trades a run's optimisation pass found would attract less initial margin in another netting set of the  run, with both sets' initial margin before and after the move. Empty until the run's optimisation pass has  completed. Restricted to recommendations whose source and target agreements the caller may read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfNettingRecommendation result = apiInstance.ListMarginRunRecommendations(runId, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing recommendations; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are RunId, SourceAgreementId.Scope, SourceAgreementId.Code, SourceItem, TargetAgreementId.Scope, TargetAgreementId.Code, TargetItem, Transfer, InstrumentType, Currency, MaturityBucket, SavingPerDay, OneOffCost, PaybackDays and InitialMarginChange. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |

### Return type

[PagedResourceListOfNettingRecommendation](../Model/PagedResourceListOfNettingRecommendation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested recommendations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListMarginRunRecommendationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfNettingRecommendation> response = apiInstance.ListMarginRunRecommendationsWithHttpInfo(runId, page, limit, filter);
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

<a id="listnettingrecommendations"></a>
## ListNettingRecommendations

> PagedResourceListOfNettingRecommendation ListNettingRecommendations(DateTimeOrCutLabel? effectiveAt = null, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListNettingRecommendations: List the current netting recommendations.

List the netting recommendations in force for a business date: those of the latest run for the date whose  optimisation pass completed, with an agreement that run could not value served from the most recent run that  did. Restricted to recommendations whose source and target agreements the caller may read.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfNettingRecommendation result = apiInstance.ListNettingRecommendations(effectiveAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The business date, datetime or cut label to list the current recommendations for. Defaults to today if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing recommendations; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are RunId, SourceAgreementId.Scope, SourceAgreementId.Code, SourceItem, TargetAgreementId.Scope, TargetAgreementId.Code, TargetItem, Transfer, InstrumentType, Currency, MaturityBucket, SavingPerDay, OneOffCost, PaybackDays and InitialMarginChange. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |

### Return type

[PagedResourceListOfNettingRecommendation](../Model/PagedResourceListOfNettingRecommendation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested recommendations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListNettingRecommendationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfNettingRecommendation> response = apiInstance.ListNettingRecommendationsWithHttpInfo(effectiveAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="rankmargincall"></a>
## RankMarginCall

> CollateralAllocation RankMarginCall(string runId, string agreementScope, string agreementCode, string item, string marginType, string direction, RankMarginCallRequest? rankMarginCallRequest = null)

[EXPERIMENTAL] RankMarginCall: [EXPERIMENTAL] RankMarginCall: Rank the collateral for a margin call again, with the caller's choices.

Value the call's agreement as of now for the run's business date and rank its free, eligible holdings for the  call again, keeping the assets and units the caller chose. Each choice is validated against the agreement's  constraints and kept with its reason when it fails one; the rest of the call is filled from the ranking, cheapest  first, unless fillRemainder is false. Nothing is stored: the result is what to book, for the caller to decide on.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var runId = "runId_example";  // string
var agreementScope = "agreementScope_example";  // string
var agreementCode = "agreementCode_example";  // string
var item = "item_example";  // string
var marginType = "marginType_example";  // string
var direction = "direction_example";  // string
var rankMarginCallRequest = new RankMarginCallRequest?(); // RankMarginCallRequest? (optional)
CollateralAllocation result = apiInstance.RankMarginCall(runId, agreementScope, agreementCode, item, marginType, direction, rankMarginCallRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **runId** | **string** | path | **required** | The identifier of the margin run. |
| **agreementScope** | **string** | path | **required** | The scope of the call&#39;s collateral agreement. |
| **agreementCode** | **string** | path | **required** | The code of the call&#39;s collateral agreement. |
| **item** | **string** | path | **required** | The margin item of the call. |
| **marginType** | **string** | path | **required** | The margin type of the call. One of VariationMargin or InitialMargin. |
| **direction** | **string** | path | **required** | Who posts under the call. One of WePost, TheyPost or None. |
| **rankMarginCallRequest** | [RankMarginCallRequest?](../Model/RankMarginCallRequest?.md) | body | optional | The assets the caller chose, and whether to fill the rest. |

### Return type

[CollateralAllocation](../Model/CollateralAllocation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The collateral ranked for the margin call. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RankMarginCallWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CollateralAllocation> response = apiInstance.RankMarginCallWithHttpInfo(runId, agreementScope, agreementCode, item, marginType, direction, rankMarginCallRequest);
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

> PagedResourceListOfMarginRun RunMarginCalculation(MarginRunRequest marginRunRequest)

[EXPERIMENTAL] RunMarginCalculation: Run the margin calculation.

Value the collateral agreements for a business date, or for each weekday of a span, in the background and publish  their margin calls as a run for each date. The base case is always valued, with each scenario named in the request  valued beside it as a case of the same run. A date after the asAt is a projection on the market as at the asAt.  The runs are returned as planned, in date order; poll GetMarginRun for the progress of each, and list the calls as they are published.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralApi>();
var marginRunRequest = new MarginRunRequest(); // MarginRunRequest
PagedResourceListOfMarginRun result = apiInstance.RunMarginCalculation(marginRunRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **marginRunRequest** | [MarginRunRequest](../Model/MarginRunRequest.md) | body | **required** | The business date to value, or the span of dates ending at it, and optionally the asAt, the agreements to include and the scenarios to value beside the base case. |

### Return type

[PagedResourceListOfMarginRun](../Model/PagedResourceListOfMarginRun.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The margin runs as planned, one for each date valued. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RunMarginCalculationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfMarginRun> response = apiInstance.RunMarginCalculationWithHttpInfo(marginRunRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

