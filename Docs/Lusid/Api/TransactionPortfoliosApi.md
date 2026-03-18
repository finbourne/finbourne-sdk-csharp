# Finbourne.Sdk.Lusid.Api.TransactionPortfoliosApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AdjustHoldings**](#adjustholdings) | **POST** `/api/api/transactionportfolios/{scope}/{code}/holdings` | AdjustHoldings: Adjust holdings |
| [**BatchAdjustHoldings**](#batchadjustholdings) | **POST** `/api/api/transactionportfolios/{scope}/{code}/holdings/$batchAdjust` | BatchAdjustHoldings: Batch adjust holdings |
| [**BatchAmendSettlementInstructions**](#batchamendsettlementinstructions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/settlementinstructions/$batchAmend` | [EARLY ACCESS] BatchAmendSettlementInstructions: Batch Amend Settlement Instructions. |
| [**BatchCreateTradeTickets**](#batchcreatetradetickets) | **POST** `/api/api/transactionportfolios/{scope}/{code}/$batchtradetickets` | BatchCreateTradeTickets: Batch Create Trade Tickets |
| [**BatchSetHoldings**](#batchsetholdings) | **POST** `/api/api/transactionportfolios/{scope}/{code}/holdings/$batchSet` | BatchSetHoldings: Batch set holdings |
| [**BatchUpsertSettlementInstructions**](#batchupsertsettlementinstructions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/settlementinstructions/$batchUpsert` | [EARLY ACCESS] BatchUpsertSettlementInstructions: Batch Upsert Settlement Instructions. |
| [**BatchUpsertTransactions**](#batchupserttransactions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/transactions/$batchUpsert` | BatchUpsertTransactions: Batch upsert transactions |
| [**BuildSettlementInstructions**](#buildsettlementinstructions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/settlementinstructions/$build` | [EARLY ACCESS] BuildSettlementInstructions: Build Settlement Instructions |
| [**BuildTransactions**](#buildtransactions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/transactions/$build` | BuildTransactions: Build transactions |
| [**CancelAdjustHoldings**](#canceladjustholdings) | **DELETE** `/api/api/transactionportfolios/{scope}/{code}/holdings` | CancelAdjustHoldings: Cancel adjust holdings |
| [**CancelSingleAdjustHolding**](#cancelsingleadjustholding) | **POST** `/api/api/transactionportfolios/{scope}/{code}/holdings/$cancelAdjustment` | CancelSingleAdjustHolding: Cancel single holding adjustment. |
| [**CancelTransactions**](#canceltransactions) | **DELETE** `/api/api/transactionportfolios/{scope}/{code}/transactions` | CancelTransactions: Cancel transactions |
| [**CreatePortfolio**](#createportfolio) | **POST** `/api/api/transactionportfolios/{scope}` | CreatePortfolio: Create portfolio |
| [**CreateTradeTicket**](#createtradeticket) | **POST** `/api/api/transactionportfolios/{scope}/{code}/$tradeticket` | CreateTradeTicket: Create Trade Ticket |
| [**DeleteCustodianAccounts**](#deletecustodianaccounts) | **POST** `/api/api/transactionportfolios/{scope}/{code}/custodianaccounts/$delete` | DeleteCustodianAccounts: Soft or hard delete multiple custodian accounts |
| [**DeletePropertiesFromTransaction**](#deletepropertiesfromtransaction) | **DELETE** `/api/api/transactionportfolios/{scope}/{code}/transactions/{transactionId}/properties` | DeletePropertiesFromTransaction: Delete properties from transaction |
| [**DeleteSettlementInstructions**](#deletesettlementinstructions) | **DELETE** `/api/api/transactionportfolios/{scope}/{code}/settlementinstructions` | [EARLY ACCESS] DeleteSettlementInstructions: Delete Settlement Instructions. |
| [**GetA2BData**](#geta2bdata) | **GET** `/api/api/transactionportfolios/{scope}/{code}/a2b` | GetA2BData: Get A2B data |
| [**GetA2BMovements**](#geta2bmovements) | **GET** `/api/api/transactionportfolios/{scope}/{code}/a2bmovements` | GetA2BMovements: Get an A2B report at the movement level for the given portfolio. |
| [**GetBucketedCashFlows**](#getbucketedcashflows) | **POST** `/api/api/transactionportfolios/{scope}/{code}/bucketedCashFlows` | GetBucketedCashFlows: Get bucketed cash flows from a list of portfolios |
| [**GetCustodianAccount**](#getcustodianaccount) | **GET** `/api/api/transactionportfolios/{scope}/{code}/custodianaccounts/{custodianAccountScope}/{custodianAccountCode}` | GetCustodianAccount: Get Custodian Account |
| [**GetDetails**](#getdetails) | **GET** `/api/api/transactionportfolios/{scope}/{code}/details` | GetDetails: Get details |
| [**GetHoldingContributors**](#getholdingcontributors) | **GET** `/api/api/transactionportfolios/{scope}/{code}/holdings/{holdingId}/contributors` | GetHoldingContributors: Get Holdings Contributors |
| [**GetHoldings**](#getholdings) | **GET** `/api/api/transactionportfolios/{scope}/{code}/holdings` | GetHoldings: Get holdings |
| [**GetHoldingsAdjustment**](#getholdingsadjustment) | **GET** `/api/api/transactionportfolios/{scope}/{code}/holdingsadjustments/{effectiveAt}` | GetHoldingsAdjustment: Get holdings adjustment |
| [**GetHoldingsWithOrders**](#getholdingswithorders) | **GET** `/api/api/transactionportfolios/{scope}/{code}/holdingsWithOrders` | GetHoldingsWithOrders: Get holdings with orders |
| [**GetMultipleHoldingContributors**](#getmultipleholdingcontributors) | **POST** `/api/api/transactionportfolios/{scope}/{code}/holdings/contributors/$get` | GetMultipleHoldingContributors: Get Multiple Holding Contributors |
| [**GetPortfolioCashFlows**](#getportfoliocashflows) | **GET** `/api/api/transactionportfolios/{scope}/{code}/cashflows` | GetPortfolioCashFlows: Get portfolio cash flows |
| [**GetPortfolioCashLadder**](#getportfoliocashladder) | **GET** `/api/api/transactionportfolios/{scope}/{code}/cashladder` | GetPortfolioCashLadder: Get portfolio cash ladder |
| [**GetPortfolioCashStatement**](#getportfoliocashstatement) | **GET** `/api/api/transactionportfolios/{scope}/{code}/cashstatement` | GetPortfolioCashStatement: Get portfolio cash statement |
| [**GetTransactionHistory**](#gettransactionhistory) | **GET** `/api/api/transactionportfolios/{scope}/{code}/transactions/{transactionId}/history` | GetTransactionHistory: Get the history of a transaction |
| [**GetTransactionSettlementStatus**](#gettransactionsettlementstatus) | **GET** `/api/api/transactionportfolios/{scope}/{code}/transactions/{transactionId}/settlementstatus` | [EARLY ACCESS] GetTransactionSettlementStatus: Get transaction settlement status |
| [**GetTransactions**](#gettransactions) | **GET** `/api/api/transactionportfolios/{scope}/{code}/transactions` | GetTransactions: Get transactions |
| [**GetUpsertablePortfolioCashFlows**](#getupsertableportfoliocashflows) | **GET** `/api/api/transactionportfolios/{scope}/{code}/upsertablecashflows` | GetUpsertablePortfolioCashFlows: Get upsertable portfolio cash flows. |
| [**ListCustodianAccounts**](#listcustodianaccounts) | **GET** `/api/api/transactionportfolios/{scope}/{code}/custodianaccounts` | ListCustodianAccounts: List Custodian Accounts |
| [**ListHoldingsAdjustments**](#listholdingsadjustments) | **GET** `/api/api/transactionportfolios/{scope}/{code}/holdingsadjustments` | ListHoldingsAdjustments: List holdings adjustments |
| [**ListSettlementInstructions**](#listsettlementinstructions) | **GET** `/api/api/transactionportfolios/{scope}/{code}/settlementinstructions` | [EARLY ACCESS] ListSettlementInstructions: List Settlement Instructions. |
| [**PatchPortfolioDetails**](#patchportfoliodetails) | **PATCH** `/api/api/transactionportfolios/{scope}/{code}/details` | PatchPortfolioDetails: Patch portfolio details |
| [**PreviewTransaction**](#previewtransaction) | **POST** `/api/api/transactionportfolios/{scope}/{code}/previewTransaction` | PreviewTransaction: Preview a transaction |
| [**ResolveInstrument**](#resolveinstrument) | **POST** `/api/api/transactionportfolios/{scope}/{code}/$resolve` | ResolveInstrument: Resolve instrument |
| [**SetHoldings**](#setholdings) | **PUT** `/api/api/transactionportfolios/{scope}/{code}/holdings` | SetHoldings: Set holdings |
| [**UpsertCustodianAccounts**](#upsertcustodianaccounts) | **POST** `/api/api/transactionportfolios/{scope}/{code}/custodianaccounts` | UpsertCustodianAccounts: Upsert Custodian Accounts |
| [**UpsertCustodianAccountsProperties**](#upsertcustodianaccountsproperties) | **POST** `/api/api/transactionportfolios/{scope}/{code}/custodianaccounts/{custodianAccountScope}/{custodianAccountCode}/properties/$upsert` | UpsertCustodianAccountsProperties: Upsert custodian accounts properties |
| [**UpsertPortfolioDetails**](#upsertportfoliodetails) | **POST** `/api/api/transactionportfolios/{scope}/{code}/details` | UpsertPortfolioDetails: Upsert portfolio details |
| [**UpsertSettlementInstructions**](#upsertsettlementinstructions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/settlementinstructions` | [EARLY ACCESS] UpsertSettlementInstructions: Upsert Settlement Instructions. |
| [**UpsertTransactionProperties**](#upserttransactionproperties) | **POST** `/api/api/transactionportfolios/{scope}/{code}/transactions/{transactionId}/properties` | UpsertTransactionProperties: Upsert transaction properties |
| [**UpsertTransactions**](#upserttransactions) | **POST** `/api/api/transactionportfolios/{scope}/{code}/transactions` | UpsertTransactions: Upsert transactions |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransactionPortfoliosApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
```

---

<a id="adjustholdings"></a>
## AdjustHoldings

> AdjustHolding AdjustHoldings(string scope, string code, DateTimeOrCutLabel effectiveAt, List<AdjustHoldingRequest> adjustHoldingRequest, List<string>? reconciliationMethods = null, string? overrideMovementName = null, string? overrideOffsetMovementName = null)

AdjustHoldings: Adjust holdings

Adjust one or more holdings of the specified transaction portfolio to the provided targets. LUSID will  automatically construct adjustment transactions to ensure that the holdings which have been adjusted are  always set to the provided targets for the specified effective datetime. Read more about the difference between  adjusting and setting holdings here https://support.lusid.com/docs/how-do-i-manually-adjust-or-set-holdings.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var adjustHoldingRequest = new List<AdjustHoldingRequest>(); // List<AdjustHoldingRequest>
var reconciliationMethods = new List<string>?(); // List<string>? (optional)
var overrideMovementName = "overrideMovementName_example";  // string? (optional)
var overrideOffsetMovementName = "overrideOffsetMovementName_example";  // string? (optional)
AdjustHolding result = apiInstance.AdjustHoldings(scope, code, effectiveAt, adjustHoldingRequest, reconciliationMethods, overrideMovementName, overrideOffsetMovementName);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The effective datetime or cut label at which the holdings should be set to the provided targets. |
| **adjustHoldingRequest** | [List&lt;AdjustHoldingRequest&gt;](AdjustHoldingRequest.md) | body | **required** | The selected set of holdings to adjust to the provided targets for the              transaction portfolio. |
| **reconciliationMethods** | [List&lt;string&gt;?](string.md) | query | optional | Optional parameter for specifying a reconciliation method: e.g. FxForward. |
| **overrideMovementName** | **string?** | query | optional | Optional parameter to override movement name for the set holdings. |
| **overrideOffsetMovementName** | **string?** | query | optional | Optional parameter will create an additional offset movement for the set holdings with this new name and transaction type: CarryAsPnl |

### Return type

[AdjustHolding](AdjustHolding.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the transaction portfolio that contains the newly adjusted holdings |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AdjustHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AdjustHolding> response = apiInstance.AdjustHoldingsWithHttpInfo(scope, code, effectiveAt, adjustHoldingRequest, reconciliationMethods, overrideMovementName, overrideOffsetMovementName);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchadjustholdings"></a>
## BatchAdjustHoldings

> BatchAdjustHoldingsResponse BatchAdjustHoldings(string scope, string code, string successMode, Dictionary<string, AdjustHoldingForDateRequest> requestBody, List<string>? reconciliationMethods = null)

BatchAdjustHoldings: Batch adjust holdings

Adjust one or more holdings of the specified transaction portfolio to the provided targets. LUSID will  automatically construct adjustment transactions to ensure that the holdings which have been adjusted are  always set to the provided targets for the specified effective datetime in each request.                Each request must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each adjustment in the response.    Note: If using partial failure modes, then it is important to check the response body for failures as any failures will still return a 200 status code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var successMode = "\"Partial\"";  // string
var requestBody = new Dictionary<string, AdjustHoldingForDateRequest>(); // Dictionary<string, AdjustHoldingForDateRequest>
var reconciliationMethods = new List<string>?(); // List<string>? (optional)
BatchAdjustHoldingsResponse result = apiInstance.BatchAdjustHoldings(scope, code, successMode, requestBody, reconciliationMethods);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies               the transaction portfolio. |
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial Default: `&quot;Partial&quot;` |
| **requestBody** | [Dictionary&lt;string, AdjustHoldingForDateRequest&gt;](AdjustHoldingForDateRequest.md) | body | **required** | The selected set of holdings to adjust to the provided targets for the               transaction portfolio. |
| **reconciliationMethods** | [List&lt;string&gt;?](string.md) | query | optional | Optional parameter for specifying a reconciliation method: e.g. FxForward. |

### Return type

[BatchAdjustHoldingsResponse](BatchAdjustHoldingsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successful AdjustHolding requests along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchAdjustHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchAdjustHoldingsResponse> response = apiInstance.BatchAdjustHoldingsWithHttpInfo(scope, code, successMode, requestBody, reconciliationMethods);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchamendsettlementinstructions"></a>
## BatchAmendSettlementInstructions

> BatchAmendTransactionSettlementInstructionResponse BatchAmendSettlementInstructions(string scope, string code, Dictionary<string, SettlementInstructionAmendRequest> requestBody, string? successMode = null)

[EARLY ACCESS] BatchAmendSettlementInstructions: Batch Amend Settlement Instructions.

Update active state and / or properties of instructions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, SettlementInstructionAmendRequest>(); // Dictionary<string, SettlementInstructionAmendRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchAmendTransactionSettlementInstructionResponse result = apiInstance.BatchAmendSettlementInstructions(scope, code, requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. |
| **requestBody** | [Dictionary&lt;string, SettlementInstructionAmendRequest&gt;](SettlementInstructionAmendRequest.md) | body | **required** | The amendments to make to the settlement instructions. |
| **successMode** | **string?** | query | optional | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial Default: `&quot;Partial&quot;` |

### Return type

[BatchAmendTransactionSettlementInstructionResponse](BatchAmendTransactionSettlementInstructionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly amended Settlement Instructions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchAmendSettlementInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchAmendTransactionSettlementInstructionResponse> response = apiInstance.BatchAmendSettlementInstructionsWithHttpInfo(scope, code, requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchcreatetradetickets"></a>
## BatchCreateTradeTickets

> CreateTradeTicketsResponse BatchCreateTradeTickets(string scope, string code, List<LusidTradeTicket> lusidTradeTicket)

BatchCreateTradeTickets: Batch Create Trade Tickets

Batch create trade tickets. Each ticket is broadly equivalent to a singular call to upsert an instrument, then a counterparty and finally  a transaction that makes use of the two.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var lusidTradeTicket = new List<LusidTradeTicket>(); // List<LusidTradeTicket>
CreateTradeTicketsResponse result = apiInstance.BatchCreateTradeTickets(scope, code, lusidTradeTicket);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **lusidTradeTicket** | [List&lt;LusidTradeTicket&gt;](LusidTradeTicket.md) | body | **required** | the trade tickets to create |

### Return type

[CreateTradeTicketsResponse](CreateTradeTicketsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully created trade ticket requests along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchCreateTradeTicketsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CreateTradeTicketsResponse> response = apiInstance.BatchCreateTradeTicketsWithHttpInfo(scope, code, lusidTradeTicket);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchsetholdings"></a>
## BatchSetHoldings

> BatchAdjustHoldingsResponse BatchSetHoldings(string scope, string code, string successMode, Dictionary<string, AdjustHoldingForDateRequest> requestBody, List<string>? reconciliationMethods = null)

BatchSetHoldings: Batch set holdings

Set the holdings of the specified transaction portfolio to the provided targets. LUSID will automatically  construct adjustment transactions to ensure that the entire set of holdings for the transaction portfolio  are always set to the provided targets for the specified effective datetime. Read more about the difference between  adjusting and setting holdings here https://support.lusid.com/docs/how-do-i-manually-adjust-or-set-holdings.                Each request must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each adjustment in the response.    Note: If using partial failure modes, then it is important to check the response body for failures as any failures will still return a 200 status code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var successMode = "\"Partial\"";  // string
var requestBody = new Dictionary<string, AdjustHoldingForDateRequest>(); // Dictionary<string, AdjustHoldingForDateRequest>
var reconciliationMethods = new List<string>?(); // List<string>? (optional)
BatchAdjustHoldingsResponse result = apiInstance.BatchSetHoldings(scope, code, successMode, requestBody, reconciliationMethods);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies               the transaction portfolio. |
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial Default: `&quot;Partial&quot;` |
| **requestBody** | [Dictionary&lt;string, AdjustHoldingForDateRequest&gt;](AdjustHoldingForDateRequest.md) | body | **required** | The selected set of holdings to adjust to the provided targets for the               transaction portfolio. |
| **reconciliationMethods** | [List&lt;string&gt;?](string.md) | query | optional | Optional parameter for specifying a reconciliation method: e.g. FxForward. |

### Return type

[BatchAdjustHoldingsResponse](BatchAdjustHoldingsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successful SetHolding requests along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchSetHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchAdjustHoldingsResponse> response = apiInstance.BatchSetHoldingsWithHttpInfo(scope, code, successMode, requestBody, reconciliationMethods);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchupsertsettlementinstructions"></a>
## BatchUpsertSettlementInstructions

> BatchUpsertTransactionSettlementInstructionResponse BatchUpsertSettlementInstructions(string scope, string code, Dictionary<string, SettlementInstructionRequest> requestBody, string? successMode = null)

[EARLY ACCESS] BatchUpsertSettlementInstructions: Batch Upsert Settlement Instructions.

Create or update instructions to settle specific transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, SettlementInstructionRequest>(); // Dictionary<string, SettlementInstructionRequest>
var successMode = "\"Partial\"";  // string? (optional)
BatchUpsertTransactionSettlementInstructionResponse result = apiInstance.BatchUpsertSettlementInstructions(scope, code, requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. |
| **requestBody** | [Dictionary&lt;string, SettlementInstructionRequest&gt;](SettlementInstructionRequest.md) | body | **required** | The definition of the settlement instruction. |
| **successMode** | **string?** | query | optional | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial Default: `&quot;Partial&quot;` |

### Return type

[BatchUpsertTransactionSettlementInstructionResponse](BatchUpsertTransactionSettlementInstructionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created or updated Settlement Instructions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertSettlementInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertTransactionSettlementInstructionResponse> response = apiInstance.BatchUpsertSettlementInstructionsWithHttpInfo(scope, code, requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchupserttransactions"></a>
## BatchUpsertTransactions

> BatchUpsertPortfolioTransactionsResponse BatchUpsertTransactions(string scope, string code, string successMode, Dictionary<string, TransactionRequest> requestBody, bool? preserveProperties = null)

BatchUpsertTransactions: Batch upsert transactions

Create or update transactions in the transaction portfolio. A transaction will be updated  if it already exists and created if it does not.    Each request must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each transaction in the response.    Note: If using partial failure modes, then it is important to check the response body for failures as any failures will still return a 200 status code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var successMode = "\"Partial\"";  // string
var requestBody = new Dictionary<string, TransactionRequest>(); // Dictionary<string, TransactionRequest>
var preserveProperties = true;  // bool? (optional)
BatchUpsertPortfolioTransactionsResponse result = apiInstance.BatchUpsertTransactions(scope, code, successMode, requestBody, preserveProperties);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial. Default: `&quot;Partial&quot;` |
| **requestBody** | [Dictionary&lt;string, TransactionRequest&gt;](TransactionRequest.md) | body | **required** | The payload describing the transactions to be created or updated. |
| **preserveProperties** | **bool?** | query | optional | If set to false, the entire property set will be overwritten by the provided properties. If not specified or set to true, only the properties provided will be updated. Default: `true` |

### Return type

[BatchUpsertPortfolioTransactionsResponse](BatchUpsertPortfolioTransactionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully upserted transaction requests along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertPortfolioTransactionsResponse> response = apiInstance.BatchUpsertTransactionsWithHttpInfo(scope, code, successMode, requestBody, preserveProperties);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="buildsettlementinstructions"></a>
## BuildSettlementInstructions

> VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery BuildSettlementInstructions(string scope, string code, SettlementInstructionQuery settlementInstructionQuery)

[EARLY ACCESS] BuildSettlementInstructions: Build Settlement Instructions

Builds and returns all settlement instructions that have been loaded against this portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var settlementInstructionQuery = new SettlementInstructionQuery(); // SettlementInstructionQuery
VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery result = apiInstance.BuildSettlementInstructions(scope, code, settlementInstructionQuery);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **settlementInstructionQuery** | [SettlementInstructionQuery](SettlementInstructionQuery.md) | body | **required** | The queryParameters which control how the settlement instructions are built and returned. |

### Return type

[VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery](VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested settlement instructions from the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BuildSettlementInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListWithPostBodiesOfSettlementInstructionWithTransactionToSettlementInstructionQuery> response = apiInstance.BuildSettlementInstructionsWithHttpInfo(scope, code, settlementInstructionQuery);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="buildtransactions"></a>
## BuildTransactions

> VersionedResourceListOfOutputTransaction BuildTransactions(string scope, string code, TransactionQueryParameters transactionQueryParameters, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, int? limit = null, string? page = null, string? dataModelScope = null, string? dataModelCode = null, string? membershipType = null)

BuildTransactions: Build transactions

Builds and returns all transactions that affect the holdings of a portfolio over a given interval of  effective time into a set of output transactions. This includes transactions automatically generated by  LUSID such as holding adjustments.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionQueryParameters = new TransactionQueryParameters(); // TransactionQueryParameters
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var membershipType = "membershipType_example";  // string? (optional)
VersionedResourceListOfOutputTransaction result = apiInstance.BuildTransactions(scope, code, transactionQueryParameters, asAt, filter, propertyKeys, limit, page, dataModelScope, dataModelCode, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionQueryParameters** | [TransactionQueryParameters](TransactionQueryParameters.md) | body | **required** | The query queryParameters which control how the output transactions are built. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to build the transactions. Defaults to return the latest              version of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;.              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; or \&quot;Transaction\&quot; domain to decorate onto              the transactions. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or              \&quot;Transaction/strategy/quantsignal\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to BuildTransactions. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[VersionedResourceListOfOutputTransaction](VersionedResourceListOfOutputTransaction.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested transactions from the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BuildTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfOutputTransaction> response = apiInstance.BuildTransactionsWithHttpInfo(scope, code, transactionQueryParameters, asAt, filter, propertyKeys, limit, page, dataModelScope, dataModelCode, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="canceladjustholdings"></a>
## CancelAdjustHoldings

> DeletedEntityResponse CancelAdjustHoldings(string scope, string code, DateTimeOrCutLabel effectiveAt)

CancelAdjustHoldings: Cancel adjust holdings

Cancel all previous holding adjustments made on the specified transaction portfolio for a specified effective  datetime. This should be used to undo holding adjustments made via set holdings or adjust holdings.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
DeletedEntityResponse result = apiInstance.CancelAdjustHoldings(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The effective datetime or cut label at which the holding adjustments should be undone. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the holding adjustments were cancelled |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelAdjustHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.CancelAdjustHoldingsWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="cancelsingleadjustholding"></a>
## CancelSingleAdjustHolding

> DeletedEntityResponse CancelSingleAdjustHolding(string scope, string code, DateTimeOrCutLabel effectiveAt, CancelSingleHoldingAdjustmentRequest cancelSingleHoldingAdjustmentRequest)

CancelSingleAdjustHolding: Cancel single holding adjustment.

Cancel one previously sent holding adjustment without affecting the rest of the adjustment in the previous request on the specified effective datetime.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var cancelSingleHoldingAdjustmentRequest = new CancelSingleHoldingAdjustmentRequest(); // CancelSingleHoldingAdjustmentRequest
DeletedEntityResponse result = apiInstance.CancelSingleAdjustHolding(scope, code, effectiveAt, cancelSingleHoldingAdjustmentRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The effective datetime or cut label at which the previous adjustment was made. |
| **cancelSingleHoldingAdjustmentRequest** | [CancelSingleHoldingAdjustmentRequest](CancelSingleHoldingAdjustmentRequest.md) | body | **required** | The selected holding adjustment to be canceled. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the holding adjustment was cancelled |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelSingleAdjustHoldingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.CancelSingleAdjustHoldingWithHttpInfo(scope, code, effectiveAt, cancelSingleHoldingAdjustmentRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="canceltransactions"></a>
## CancelTransactions

> DeletedEntityResponse CancelTransactions(string scope, string code, List<string> transactionIds)

CancelTransactions: Cancel transactions

Cancel one or more transactions from the transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionIds = new List<string>(); // List<string>
DeletedEntityResponse result = apiInstance.CancelTransactions(scope, code, transactionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionIds** | [List&lt;string&gt;](string.md) | query | **required** | The IDs of the transactions to cancel. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the transactions were cancelled |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CancelTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.CancelTransactionsWithHttpInfo(scope, code, transactionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createportfolio"></a>
## CreatePortfolio

> Portfolio CreatePortfolio(string scope, CreateTransactionPortfolioRequest createTransactionPortfolioRequest)

CreatePortfolio: Create portfolio

Create a transaction portfolio in a particular scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var createTransactionPortfolioRequest = new CreateTransactionPortfolioRequest(); // CreateTransactionPortfolioRequest
Portfolio result = apiInstance.CreatePortfolio(scope, createTransactionPortfolioRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create the transaction portfolio. |
| **createTransactionPortfolioRequest** | [CreateTransactionPortfolioRequest](CreateTransactionPortfolioRequest.md) | body | **required** | The definition of the transaction portfolio. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly-created transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.CreatePortfolioWithHttpInfo(scope, createTransactionPortfolioRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createtradeticket"></a>
## CreateTradeTicket

> LusidTradeTicket CreateTradeTicket(string scope, string code, LusidTradeTicket? lusidTradeTicket = null)

CreateTradeTicket: Create Trade Ticket

Upsert a trade ticket. Broadly equivalent to a singular call to upsert an instrument, then a counterparty and finally  a transaction that makes use of the two. It can be viewed as a utility function or part of a workflow more familiar to users  with OTC systems than flow and equity trading ones.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var lusidTradeTicket = new LusidTradeTicket?(); // LusidTradeTicket? (optional)
LusidTradeTicket result = apiInstance.CreateTradeTicket(scope, code, lusidTradeTicket);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **lusidTradeTicket** | [LusidTradeTicket?](LusidTradeTicket?.md) | body | optional | the trade ticket to upsert |

### Return type

[LusidTradeTicket](LusidTradeTicket.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created trade ticket, possibly populated with created LUID and identifiers if missing on the request. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTradeTicketWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LusidTradeTicket> response = apiInstance.CreateTradeTicketWithHttpInfo(scope, code, lusidTradeTicket);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecustodianaccounts"></a>
## DeleteCustodianAccounts

> DeleteCustodianAccountsResponse DeleteCustodianAccounts(string scope, string code, List<ResourceId> resourceId, string? deleteMode = null)

DeleteCustodianAccounts: Soft or hard delete multiple custodian accounts

Delete one or more custodian accounts from the Transaction Portfolios. Soft deletion marks the custodian account as inactive  While the Hard deletion is deleting the custodian account.  The batch limit per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var resourceId = new List<ResourceId>(); // List<ResourceId>
var deleteMode = "Soft";  // string? (optional)
DeleteCustodianAccountsResponse result = apiInstance.DeleteCustodianAccounts(scope, code, resourceId, deleteMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Transaction Portfolios. |
| **code** | **string** | path | **required** | The code of the Transaction Portfolios. Together with the scope this uniquely identifies              the Transaction Portfolios. |
| **resourceId** | [List&lt;ResourceId&gt;](ResourceId.md) | body | **required** | The scope and codes of the custodian accounts to delete. |
| **deleteMode** | **string?** | query | optional | The delete mode to use (defaults to &#39;Soft&#39;). |

### Return type

[DeleteCustodianAccountsResponse](DeleteCustodianAccountsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the custodian accounts were deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCustodianAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeleteCustodianAccountsResponse> response = apiInstance.DeleteCustodianAccountsWithHttpInfo(scope, code, resourceId, deleteMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepropertiesfromtransaction"></a>
## DeletePropertiesFromTransaction

> DeletedEntityResponse DeletePropertiesFromTransaction(string scope, string code, string transactionId, List<string> propertyKeys)

DeletePropertiesFromTransaction: Delete properties from transaction

Delete one or more properties from a single transaction in a transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionId = "transactionId_example";  // string
var propertyKeys = new List<string>(); // List<string>
DeletedEntityResponse result = apiInstance.DeletePropertiesFromTransaction(scope, code, transactionId, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionId** | **string** | path | **required** | The unique ID of the transaction from which to delete properties. |
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | The property keys of the properties to delete.              These must be from the \&quot;Transaction\&quot; domain and have the format {domain}/{scope}/{code}, for example              \&quot;Transaction/strategy/quantsignal\&quot;. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the property was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePropertiesFromTransactionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePropertiesFromTransactionWithHttpInfo(scope, code, transactionId, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletesettlementinstructions"></a>
## DeleteSettlementInstructions

> DeletedEntityResponse DeleteSettlementInstructions(string scope, string code, List<string> settlementInstructionIds)

[EARLY ACCESS] DeleteSettlementInstructions: Delete Settlement Instructions.

Delete the specified settlement instructions

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var settlementInstructionIds = new List<string>(); // List<string>
DeletedEntityResponse result = apiInstance.DeleteSettlementInstructions(scope, code, settlementInstructionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies              the portfolio. |
| **settlementInstructionIds** | [List&lt;string&gt;](string.md) | query | **required** | A list of Ids of settlement instructions to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The ids of the deleted settlement instructions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteSettlementInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteSettlementInstructionsWithHttpInfo(scope, code, settlementInstructionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="geta2bdata"></a>
## GetA2BData

> VersionedResourceListOfA2BDataRecord GetA2BData(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOffset? asAt = null, string? recipeIdScope = null, string? recipeIdCode = null, List<string>? propertyKeys = null, string? filter = null)

GetA2BData: Get A2B data

Get an A2B report for the given portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var filter = "filter_example";  // string? (optional)
VersionedResourceListOfA2BDataRecord result = apiInstance.GetA2BData(scope, code, fromEffectiveAt, toEffectiveAt, asAt, recipeIdScope, recipeIdCode, propertyKeys, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio to retrieve the A2B report for. |
| **code** | **string** | path | **required** | The code of the portfolio to retrieve the A2B report for. Together with the scope this              uniquely identifies the portfolio. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The lower bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no lower bound if this is not specified. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The upper bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio. Defaults to return the latest version              of each transaction if not specified. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeId |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; domain to decorate onto              the results. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot;. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[VersionedResourceListOfA2BDataRecord](VersionedResourceListOfA2BDataRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio A2B data |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetA2BDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfA2BDataRecord> response = apiInstance.GetA2BDataWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt, recipeIdScope, recipeIdCode, propertyKeys, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="geta2bmovements"></a>
## GetA2BMovements

> VersionedResourceListOfA2BMovementRecord GetA2BMovements(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOffset? asAt = null, string? recipeIdScope = null, string? recipeIdCode = null, List<string>? propertyKeys = null, string? filter = null)

GetA2BMovements: Get an A2B report at the movement level for the given portfolio.

Get an A2B report at the movement level for the given portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var filter = "filter_example";  // string? (optional)
VersionedResourceListOfA2BMovementRecord result = apiInstance.GetA2BMovements(scope, code, fromEffectiveAt, toEffectiveAt, asAt, recipeIdScope, recipeIdCode, propertyKeys, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio to retrieve the A2B movement report for. |
| **code** | **string** | path | **required** | The code of the portfolio to retrieve the A2B movement report for. Together with the scope this              uniquely identifies the portfolio. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The lower bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no lower bound if this is not specified. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The upper bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio. Defaults to return the latest version              of each transaction if not specified. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeId |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; domain to decorate onto              the results. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot;. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[VersionedResourceListOfA2BMovementRecord](VersionedResourceListOfA2BMovementRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio A2B movement data |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetA2BMovementsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfA2BMovementRecord> response = apiInstance.GetA2BMovementsWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt, recipeIdScope, recipeIdCode, propertyKeys, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getbucketedcashflows"></a>
## GetBucketedCashFlows

> BucketedCashFlowResponse GetBucketedCashFlows(string scope, string code, BucketedCashFlowRequest? bucketedCashFlowRequest = null)

GetBucketedCashFlows: Get bucketed cash flows from a list of portfolios

We bucket/aggregate a transaction portfolio's instruments by date or tenor specified in the request.  The cashflows are grouped by both instrumentId and currency.                If you want transactional level cashflow, please use the 'GetUpsertableCashFlows' endpoint.  If you want instrument cashflow, please use the 'GetPortfolioCashFlows' endpoint.  Note that these endpoints do not apply bucketing.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var bucketedCashFlowRequest = new BucketedCashFlowRequest?(); // BucketedCashFlowRequest? (optional)
BucketedCashFlowResponse result = apiInstance.GetBucketedCashFlows(scope, code, bucketedCashFlowRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies the portfolio. |
| **bucketedCashFlowRequest** | [BucketedCashFlowRequest?](BucketedCashFlowRequest?.md) | body | optional | Request specifying the bucketing of cashflows |

### Return type

[BucketedCashFlowResponse](BucketedCashFlowResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio instruments&#39; bucketed cash flow data |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetBucketedCashFlowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BucketedCashFlowResponse> response = apiInstance.GetBucketedCashFlowsWithHttpInfo(scope, code, bucketedCashFlowRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcustodianaccount"></a>
## GetCustodianAccount

> CustodianAccount GetCustodianAccount(string scope, string code, string custodianAccountScope, string custodianAccountCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

GetCustodianAccount: Get Custodian Account

Retrieve the definition of a particular Custodian Account which is part of a Transaction Portfolios.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var custodianAccountScope = "custodianAccountScope_example";  // string
var custodianAccountCode = "custodianAccountCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
CustodianAccount result = apiInstance.GetCustodianAccount(scope, code, custodianAccountScope, custodianAccountCode, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Transaction Portfolio. |
| **code** | **string** | path | **required** | The code of the Transaction Portfolio. Together with the scope this uniquely identifies the Transaction Portfolio. |
| **custodianAccountScope** | **string** | path | **required** | The scope of the Custodian Account. |
| **custodianAccountCode** | **string** | path | **required** | The code of the Custodian Account. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Custodian Account properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Custodian Account definition. Defaults to returning the latest version of the Custodian Account definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;CustodianAccount&#39; domain to decorate onto the Custodian Account.              These must take the format {domain}/{scope}/{code}, for example &#39;CustodianAccount/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[CustodianAccount](CustodianAccount.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Custodian Account definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustodianAccountWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustodianAccount> response = apiInstance.GetCustodianAccountWithHttpInfo(scope, code, custodianAccountScope, custodianAccountCode, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdetails"></a>
## GetDetails

> PortfolioDetails GetDetails(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

GetDetails: Get details

Get certain details associated with a transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PortfolioDetails result = apiInstance.GetDetails(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the              scope this uniquely identifies the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the details of the transaction              portfolio. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the details of the transaction portfolio. Defaults              to returning the latest version of the details if not specified. |

### Return type

[PortfolioDetails](PortfolioDetails.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The details of the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioDetails> response = apiInstance.GetDetailsWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdingcontributors"></a>
## GetHoldingContributors

> VersionedResourceListOfHoldingContributor GetHoldingContributors(string scope, string code, long holdingId, DateTimeOrCutLabel? effectiveDate = null, DateTimeOrCutLabel? fromTradeDate = null, DateTimeOrCutLabel? toTradeDate = null, bool? includeHistoric = null, string? taxLotId = null, bool? includeUnsettledMovements = null, int? limit = null, DateTimeOffset? asAt = null, string? page = null, string? timelineScope = null, string? timelineCode = null)

GetHoldingContributors: Get Holdings Contributors

Lists all transactions that affect the holdings of a portfolio over a given effective interval. This includes  transactions automatically generated by LUSID such as holding adjustments.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var holdingId = 789L;  // long
var effectiveDate = "effectiveDate_example";  // DateTimeOrCutLabel? (optional)
var fromTradeDate = "fromTradeDate_example";  // DateTimeOrCutLabel? (optional)
var toTradeDate = "toTradeDate_example";  // DateTimeOrCutLabel? (optional)
var includeHistoric = false;  // bool? (optional)
var taxLotId = "taxLotId_example";  // string? (optional)
var includeUnsettledMovements = false;  // bool? (optional)
var limit = 56;  // int? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var timelineScope = "timelineScope_example";  // string? (optional)
var timelineCode = "timelineCode_example";  // string? (optional)
VersionedResourceListOfHoldingContributor result = apiInstance.GetHoldingContributors(scope, code, holdingId, effectiveDate, fromTradeDate, toTradeDate, includeHistoric, taxLotId, includeUnsettledMovements, limit, asAt, page, timelineScope, timelineCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **holdingId** | **long** | path | **required** | The unique holding identifier |
| **effectiveDate** | **DateTimeOrCutLabel?** | query | optional | Effective date |
| **fromTradeDate** | **DateTimeOrCutLabel?** | query | optional | The from trade date, defaults to first time this holding is opened, lower bound for transactions |
| **toTradeDate** | **DateTimeOrCutLabel?** | query | optional | The to trade date upper bound date, defaults to effectiveDate. upper bound for transactions |
| **includeHistoric** | **bool?** | query | optional | If true, transactions from previously closed holdings are returned.              If false, only transactions from last time position is opened. Default: `false` |
| **taxLotId** | **string?** | query | optional | Constrains the Holding Contributors to those which contributed to the specified tax lot. |
| **includeUnsettledMovements** | **bool?** | query | optional | If true, contributing transaction which have not settled yet will also be returned. False by default Default: `false` |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to build the transactions. Defaults to return the latest              version of each transaction if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to GetHoldingContributors. |
| **timelineScope** | **string?** | query | optional | The scope of the timeline used for evaluation. If provided, you must also provide a timelineCode. |
| **timelineCode** | **string?** | query | optional | The code of the Timeline. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods. |

### Return type

[VersionedResourceListOfHoldingContributor](VersionedResourceListOfHoldingContributor.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested holding contributors from the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingContributorsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfHoldingContributor> response = apiInstance.GetHoldingContributorsWithHttpInfo(scope, code, holdingId, effectiveDate, fromTradeDate, toTradeDate, includeHistoric, taxLotId, includeUnsettledMovements, limit, asAt, page, timelineScope, timelineCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdings"></a>
## GetHoldings

> VersionedResourceListOfPortfolioHolding GetHoldings(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, bool? byTaxlots = null, int? includeSettlementEventsAfterDays = null, string? timelineScope = null, string? timelineCode = null, string? closedPeriodId = null)

GetHoldings: Get holdings

Calculate holdings for a transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var byTaxlots = true;  // bool? (optional)
var includeSettlementEventsAfterDays = 56;  // int? (optional)
var timelineScope = "timelineScope_example";  // string? (optional)
var timelineCode = "timelineCode_example";  // string? (optional)
var closedPeriodId = "closedPeriodId_example";  // string? (optional)
VersionedResourceListOfPortfolioHolding result = apiInstance.GetHoldings(scope, code, effectiveAt, asAt, filter, propertyKeys, byTaxlots, includeSettlementEventsAfterDays, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the holdings of the transaction              portfolio. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the holdings of the transaction portfolio. Defaults              to return the latest version if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Holding Type, use \&quot;holdingType eq &#39;p&#39;\&quot;.              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot;, \&quot;Holding\&quot;, \&quot;Custodian Account\&quot;, \&quot;Legal Entity\&quot; or \&quot;Portfolio\&quot; domain to decorate onto              holdings. These must have the format {domain}/{scope}/{code}, for example \&quot;Instrument/system/Name\&quot; or \&quot;Holding/system/Cost\&quot;. |
| **byTaxlots** | **bool?** | query | optional | Whether or not to expand the holdings to return the underlying tax-lots. Defaults to              False. |
| **includeSettlementEventsAfterDays** | **int?** | query | optional | Number of days ahead to bring back settlements from, in relation to the specified effectiveAt |
| **timelineScope** | **string?** | query | optional | The scope of the Timeline. |
| **timelineCode** | **string?** | query | optional | The code of the Timeline. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods. |
| **closedPeriodId** | **string?** | query | optional | The closed period ID. If this is specified, both timelineScope and timelineCode must be specified. Either closedPeriodId or effectiveAt can be used with a Timeline. |

### Return type

[VersionedResourceListOfPortfolioHolding](VersionedResourceListOfPortfolioHolding.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The holdings and version of the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfPortfolioHolding> response = apiInstance.GetHoldingsWithHttpInfo(scope, code, effectiveAt, asAt, filter, propertyKeys, byTaxlots, includeSettlementEventsAfterDays, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdingsadjustment"></a>
## GetHoldingsAdjustment

> HoldingsAdjustment GetHoldingsAdjustment(string scope, string code, DateTimeOrCutLabel effectiveAt, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

GetHoldingsAdjustment: Get holdings adjustment

Get a holdings adjustment made to a transaction portfolio at a specific effective datetime. Note that a  holdings adjustment will only be returned if one exists for the specified effective datetime.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
HoldingsAdjustment result = apiInstance.GetHoldingsAdjustment(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel** | path | **required** | The effective datetime or cut label of the holdings adjustment. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the holdings adjustment. Defaults to the return the latest              version of the holdings adjustment if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the ‘Instrument&#39; domain to decorate onto holdings adjustments.              These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39;.              Note that properties from the &#39;Holding’ domain are automatically returned. |

### Return type

[HoldingsAdjustment](HoldingsAdjustment.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The details of the requested holdings adjustment |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingsAdjustmentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<HoldingsAdjustment> response = apiInstance.GetHoldingsAdjustmentWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdingswithorders"></a>
## GetHoldingsWithOrders

> VersionedResourceListWithWarningsOfPortfolioHolding GetHoldingsWithOrders(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, bool? byTaxlots = null, string? recipeIdScope = null, string? recipeIdCode = null, int? includeSettlementEventsAfterDays = null)

GetHoldingsWithOrders: Get holdings with orders

Get the holdings of a transaction portfolio. Create virtual holdings for any outstanding orders,  and account for order state/fulfillment; that is, treat outstanding orders (and related records) as  if they had been realised at moment of query.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var byTaxlots = true;  // bool? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var includeSettlementEventsAfterDays = 56;  // int? (optional)
VersionedResourceListWithWarningsOfPortfolioHolding result = apiInstance.GetHoldingsWithOrders(scope, code, effectiveAt, asAt, filter, propertyKeys, byTaxlots, recipeIdScope, recipeIdCode, includeSettlementEventsAfterDays);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the holdings of the transaction              portfolio. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the holdings of the transaction portfolio. Defaults              to return the latest version of the holdings if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Holding Type, use \&quot;holdingType eq &#39;p&#39;\&quot;              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot;, \&quot;Holding\&quot; or \&quot;Portfolio\&quot; domain to decorate onto              the holdings. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or \&quot;Holding/system/Cost\&quot;. |
| **byTaxlots** | **bool?** | query | optional | Whether or not to expand the holdings to return the underlying tax-lots. Defaults to              False. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeId |
| **includeSettlementEventsAfterDays** | **int?** | query | optional | Number of days ahead to bring back settlements from, in relation to the specified effectiveAt |

### Return type

[VersionedResourceListWithWarningsOfPortfolioHolding](VersionedResourceListWithWarningsOfPortfolioHolding.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The holdings and version of the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingsWithOrdersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListWithWarningsOfPortfolioHolding> response = apiInstance.GetHoldingsWithOrdersWithHttpInfo(scope, code, effectiveAt, asAt, filter, propertyKeys, byTaxlots, recipeIdScope, recipeIdCode, includeSettlementEventsAfterDays);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmultipleholdingcontributors"></a>
## GetMultipleHoldingContributors

> VersionedResourceListOfHoldingContributor GetMultipleHoldingContributors(string scope, string code, HoldingIdsRequest holdingIdsRequest, DateTimeOrCutLabel? effectiveDate = null, DateTimeOrCutLabel? fromTransactionDate = null, DateTimeOrCutLabel? toTransactionDate = null, bool? includeHistoric = null, string? taxLotId = null, bool? includeUnsettledMovements = null, int? limit = null, DateTimeOffset? asAt = null, string? page = null, string? timelineScope = null, string? timelineCode = null)

GetMultipleHoldingContributors: Get Multiple Holding Contributors

Lists all transactions that affect multiple specified holdings of a portfolio over a given effective interval. This includes  transactions automatically generated by LUSID such as holding adjustments.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var holdingIdsRequest = new HoldingIdsRequest(); // HoldingIdsRequest
var effectiveDate = "effectiveDate_example";  // DateTimeOrCutLabel? (optional)
var fromTransactionDate = "fromTransactionDate_example";  // DateTimeOrCutLabel? (optional)
var toTransactionDate = "toTransactionDate_example";  // DateTimeOrCutLabel? (optional)
var includeHistoric = false;  // bool? (optional)
var taxLotId = "taxLotId_example";  // string? (optional)
var includeUnsettledMovements = false;  // bool? (optional)
var limit = 56;  // int? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var timelineScope = "timelineScope_example";  // string? (optional)
var timelineCode = "timelineCode_example";  // string? (optional)
VersionedResourceListOfHoldingContributor result = apiInstance.GetMultipleHoldingContributors(scope, code, holdingIdsRequest, effectiveDate, fromTransactionDate, toTransactionDate, includeHistoric, taxLotId, includeUnsettledMovements, limit, asAt, page, timelineScope, timelineCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **holdingIdsRequest** | [HoldingIdsRequest](HoldingIdsRequest.md) | body | **required** | The array of unique holding identifiers |
| **effectiveDate** | **DateTimeOrCutLabel?** | query | optional | Effective date |
| **fromTransactionDate** | **DateTimeOrCutLabel?** | query | optional | The from trade date, defaults to first time this holding is opened, lower bound for transactions |
| **toTransactionDate** | **DateTimeOrCutLabel?** | query | optional | The to trade date upper bound date, defaults to effectiveDate. upper bound for transactions |
| **includeHistoric** | **bool?** | query | optional | If true, transactions from previously closed holdings are returned.              If false, only transactions from last time position is opened. Default: `false` |
| **taxLotId** | **string?** | query | optional | Constrains the Holding Contributors to those which contributed to the specified tax lot. |
| **includeUnsettledMovements** | **bool?** | query | optional | If true, contributing transaction which have not settled yet will also be returned. False by default Default: `false` |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to build the transactions. Defaults to return the latest              version of each transaction if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to GetHoldingContributors. |
| **timelineScope** | **string?** | query | optional | The scope of the timeline used for evaluation. If provided, you must also provide a timelineCode. |
| **timelineCode** | **string?** | query | optional | The code of the Timeline. This can optionally include a colon, followed by the Closed Period Id to use at the head of the timeline, for a timeline with unconfirmed periods. |

### Return type

[VersionedResourceListOfHoldingContributor](VersionedResourceListOfHoldingContributor.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested holding contributors for each specified holding from the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMultipleHoldingContributorsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfHoldingContributor> response = apiInstance.GetMultipleHoldingContributorsWithHttpInfo(scope, code, holdingIdsRequest, effectiveDate, fromTransactionDate, toTransactionDate, includeHistoric, taxLotId, includeUnsettledMovements, limit, asAt, page, timelineScope, timelineCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliocashflows"></a>
## GetPortfolioCashFlows

> ResourceListOfInstrumentCashFlow GetPortfolioCashFlows(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOrCutLabel? windowStart = null, DateTimeOrCutLabel? windowEnd = null, DateTimeOffset? asAt = null, string? filter = null, string? recipeIdScope = null, string? recipeIdCode = null, bool? excludeUnsettledTrades = null)

GetPortfolioCashFlows: Get portfolio cash flows

Get the set of cash flows that occur in a window for the transaction portfolio's instruments.                Note that grouping can affect the quantity of information returned; where a holding is an amalgamation of one or more (e.g. cash) instruments, a unique  transaction identifier will not be available. The same may go for diagnostic information (e.g. multiple sources of an aggregate cash amount on a date that is  not split out. Grouping at the transaction and instrument level is recommended for those seeking to attribute individual flows.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var windowStart = "windowStart_example";  // DateTimeOrCutLabel? (optional)
var windowEnd = "windowEnd_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var excludeUnsettledTrades = false;  // bool? (optional)
ResourceListOfInstrumentCashFlow result = apiInstance.GetPortfolioCashFlows(scope, code, effectiveAt, windowStart, windowEnd, asAt, filter, recipeIdScope, recipeIdCode, excludeUnsettledTrades);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this               uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up.  For example, on a swap if the effectiveAt is in the middle of the window, cashflows before it will be historic and resets assumed to exist where if the effectiveAt  is before the start of the range they are forward looking and will be expectations assuming the model supports that.  There is evidently a presumption here about availability of data and that the effectiveAt is realistically on or before the real-world today. |
| **windowStart** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.               There is no lower bound if this is not specified. i.e. it is the minimum date. |
| **windowEnd** | **DateTimeOrCutLabel?** | query | optional | The upper bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.               The upper bound defaults to &#39;max date&#39; if it is not specified |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the data. Defaults to returning the latest version               of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;.               For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeID |
| **excludeUnsettledTrades** | **bool?** | query | optional | If absent or set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. If set to true, unsettled trades will be excluded from the result set. Default: `false` |

### Return type

[ResourceListOfInstrumentCashFlow](ResourceListOfInstrumentCashFlow.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio instruments&#39; cash flow data |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioCashFlowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfInstrumentCashFlow> response = apiInstance.GetPortfolioCashFlowsWithHttpInfo(scope, code, effectiveAt, windowStart, windowEnd, asAt, filter, recipeIdScope, recipeIdCode, excludeUnsettledTrades);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliocashladder"></a>
## GetPortfolioCashLadder

> ResourceListOfPortfolioCashLadder GetPortfolioCashLadder(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOrCutLabel effectiveAt, DateTimeOffset? asAt = null, string? filter = null, string? recipeIdScope = null, string? recipeIdCode = null, bool? excludeUnsettledTrades = null)

GetPortfolioCashLadder: Get portfolio cash ladder

Get a cash ladder for a transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var excludeUnsettledTrades = false;  // bool? (optional)
ResourceListOfPortfolioCashLadder result = apiInstance.GetPortfolioCashLadder(scope, code, fromEffectiveAt, toEffectiveAt, effectiveAt, asAt, filter, recipeIdScope, recipeIdCode, excludeUnsettledTrades);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this              uniquely identifies the portfolio. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The lower bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no lower bound if this is not specified. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The upper bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no upper bound if this is not specified. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up.  For example, on a swap if the effectiveAt is in the middle of the window, cashflows before it will be historic and resets assumed to exist where if the effectiveAt  is before the start of the range they are forward looking and will be expectations assuming the model supports that.  There is evidently a presumption here about availability of data and that the effectiveAt is realistically on or before the real-world today. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio. Defaults to returning the latest version              of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;.              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeID |
| **excludeUnsettledTrades** | **bool?** | query | optional | If absent or set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. If set to true, unsettled trades will be excluded from the result set. Default: `false` |

### Return type

[ResourceListOfPortfolioCashLadder](ResourceListOfPortfolioCashLadder.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio cash-ladder |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioCashLadderWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPortfolioCashLadder> response = apiInstance.GetPortfolioCashLadderWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, effectiveAt, asAt, filter, recipeIdScope, recipeIdCode, excludeUnsettledTrades);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliocashstatement"></a>
## GetPortfolioCashStatement

> ResourceListOfPortfolioCashFlow GetPortfolioCashStatement(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOffset? asAt = null, string? filter = null, string? recipeIdScope = null, string? recipeIdCode = null, List<string>? propertyKeys = null)

GetPortfolioCashStatement: Get portfolio cash statement

Get a cash statement for a transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ResourceListOfPortfolioCashFlow result = apiInstance.GetPortfolioCashStatement(scope, code, fromEffectiveAt, toEffectiveAt, asAt, filter, recipeIdScope, recipeIdCode, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this              uniquely identifies the portfolio. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The lower bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no lower bound if this is not specified. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The upper bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio. Defaults to returning the latest version              of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;.              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeID |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; or \&quot;Transaction\&quot; domain to decorate onto              the cash flows&#39; transactions. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or              \&quot;Transaction/strategy/quantsignal\&quot;. |

### Return type

[ResourceListOfPortfolioCashFlow](ResourceListOfPortfolioCashFlow.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio cash flow data |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioCashStatementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPortfolioCashFlow> response = apiInstance.GetPortfolioCashStatementWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt, filter, recipeIdScope, recipeIdCode, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionhistory"></a>
## GetTransactionHistory

> ResourceListOfChangeHistory GetTransactionHistory(string scope, string code, string transactionId, DateTimeOffset? asAt = null)

GetTransactionHistory: Get the history of a transaction

Get all of the changes that have happened to a transaction.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionId = "transactionId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfChangeHistory result = apiInstance.GetTransactionHistory(scope, code, transactionId, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionId** | **string** | path | **required** | The unique ID of the transaction to create or update. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the history of the transaction. Defaults              to return the latest version if not specified. |

### Return type

[ResourceListOfChangeHistory](ResourceListOfChangeHistory.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The history of the specified transaction (changes that have been made to it). |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfChangeHistory> response = apiInstance.GetTransactionHistoryWithHttpInfo(scope, code, transactionId, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionsettlementstatus"></a>
## GetTransactionSettlementStatus

> TransactionSettlementStatus GetTransactionSettlementStatus(string scope, string code, string transactionId, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] GetTransactionSettlementStatus: Get transaction settlement status

Gets the Transaction Settlement Status for the requested transaction.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionId = "transactionId_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
TransactionSettlementStatus result = apiInstance.GetTransactionSettlementStatus(scope, code, transactionId, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. This together with the scope uniquely identifies the transaction portfolio. |
| **transactionId** | **string** | path | **required** | The ID of the transaction. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date and time or cut label to get the transaction settlement status.              This defaults to the current LUSID system time if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt date and time to get the transaction settlement status.               This defaults to return the latest status if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;SettlementInstruction&#39;, &#39;Instrument&#39; or &#39;Portfolio&#39; domains to decorate onto              settlement instructions. These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39; or &#39;SettlementInstruction/strategy/quantsignal&#39;. |

### Return type

[TransactionSettlementStatus](TransactionSettlementStatus.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Transaction Settlement Status for the requested transaction. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionSettlementStatusWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TransactionSettlementStatus> response = apiInstance.GetTransactionSettlementStatusWithHttpInfo(scope, code, transactionId, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactions"></a>
## GetTransactions

> VersionedResourceListOfTransaction GetTransactions(string scope, string code, DateTimeOrCutLabel? fromTransactionDate = null, DateTimeOrCutLabel? toTransactionDate = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, string? page = null, int? limit = null, bool? showCancelledTransactions = null, List<string>? sortBy = null, string? dataModelScope = null, string? dataModelCode = null, string? membershipType = null)

GetTransactions: Get transactions

Retrieve all the transactions that occurred during a particular time interval.                If the portfolio is a derived transaction portfolio, the transactions returned are the  union set of all transactions of the parent (and any grandparents, etc.) as well as  those of the derived transaction portfolio itself.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromTransactionDate = "fromTransactionDate_example";  // DateTimeOrCutLabel? (optional)
var toTransactionDate = "toTransactionDate_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var showCancelledTransactions = true;  // bool? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var membershipType = "membershipType_example";  // string? (optional)
VersionedResourceListOfTransaction result = apiInstance.GetTransactions(scope, code, fromTransactionDate, toTransactionDate, asAt, filter, propertyKeys, page, limit, showCancelledTransactions, sortBy, dataModelScope, dataModelCode, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies               the transaction portfolio. |
| **fromTransactionDate** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve transactions.               There is no lower bound if this is not specified. |
| **toTransactionDate** | **DateTimeOrCutLabel?** | query | optional | The upper bound effective datetime or cut label (inclusive) from which to retrieve transactions.               There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve transactions. Defaults to returning the latest version               of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression with which to filter the result set.               For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;               For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39;, &#39;Transaction&#39;, \&quot;LegalEntity\&quot; or \&quot;CustodianAccount\&quot; domain to decorate onto               transactions. These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39; or               &#39;Transaction/strategy/quantsignal&#39;. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to GetTransactions. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. The current behaviour is               to return all transactions if possible, but this will change to defaulting to 1000 if not specified in the future. It is recommended               to populate this field to enable pagination. |
| **showCancelledTransactions** | **bool?** | query | optional | Option to specify whether or not to include cancelled transactions,               including previous versions of transactions which have since been amended.               Defaults to False if not specified. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[VersionedResourceListOfTransaction](VersionedResourceListOfTransaction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested transactions from the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfTransaction> response = apiInstance.GetTransactionsWithHttpInfo(scope, code, fromTransactionDate, toTransactionDate, asAt, filter, propertyKeys, page, limit, showCancelledTransactions, sortBy, dataModelScope, dataModelCode, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getupsertableportfoliocashflows"></a>
## GetUpsertablePortfolioCashFlows

> ResourceListOfTransaction GetUpsertablePortfolioCashFlows(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOrCutLabel? windowStart = null, DateTimeOrCutLabel? windowEnd = null, DateTimeOffset? asAt = null, string? filter = null, string? recipeIdScope = null, string? recipeIdCode = null, bool? excludeUnsettledTrades = null)

GetUpsertablePortfolioCashFlows: Get upsertable portfolio cash flows.

Get the set of cash flows that occur in a window for the given portfolio instruments as a set of upsertable transactions (DTOs).                Note that grouping can affect the quantity of information returned; where a holding is an amalgamation of one or more (e.g. cash) instruments, a unique  transaction identifier will not be available. The same may go for diagnostic information (e.g. multiple sources of an aggregate cash amount on a date that is  not split out. Grouping at the transaction and instrument level is recommended for those seeking to attribute individual flows.                In essence this is identical to the 'GetCashFlows' endpoint but returns the cash flows as a set of transactions suitable for directly putting back into LUSID.  There are a couple of important points:  (1) Internally it can not be fully known where the user wishes to insert these transactions, e.g. portfolio and movement type.      These are therefore defaulted to a sensible option; the user will likely need to change these.  (2) Similarly, knowledge of any properties the user might wish to add to a transaction are unknown and consequently left empty.  (3) The transaction id that is added is simply a concatenation of the original transaction id, instrument id and payment date and direction. The user can happily override this.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var windowStart = "windowStart_example";  // DateTimeOrCutLabel? (optional)
var windowEnd = "windowEnd_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var excludeUnsettledTrades = true;  // bool? (optional)
ResourceListOfTransaction result = apiInstance.GetUpsertablePortfolioCashFlows(scope, code, effectiveAt, windowStart, windowEnd, asAt, filter, recipeIdScope, recipeIdCode, excludeUnsettledTrades);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this               uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The valuation (pricing) effective datetime or cut label (inclusive) at which to evaluate the cashflows.  This determines whether cashflows are evaluated in a historic or forward looking context and will, for certain models, affect where data is looked up.  For example, on a swap if the effectiveAt is in the middle of the window, cashflows before it will be historic and resets assumed to exist where if the effectiveAt  is before the start of the range they are forward looking and will be expectations assuming the model supports that.  There is evidently a presumption here about availability of data and that the effectiveAt is realistically on or before the real-world today. |
| **windowStart** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.               There is no lower bound if this is not specified. i.e. uses minimum date-time |
| **windowEnd** | **DateTimeOrCutLabel?** | query | optional | The upper bound effective datetime or cut label (inclusive) from which to retrieve the cashflows.               The upper bound defaults to &#39;max date&#39; if it is not specified |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio. Defaults to return the latest version               of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;.               For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeID |
| **excludeUnsettledTrades** | **bool?** | query | optional | If absent or set to true, unsettled trades will be excluded from the result set. If set to false, cashflows will returned based on trade date - more specifically, cashflows from any unsettled trades will be included in the results. Default: `true` |

### Return type

[ResourceListOfTransaction](ResourceListOfTransaction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio instruments&#39; cash flow data as a set of upsertable transactions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetUpsertablePortfolioCashFlowsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTransaction> response = apiInstance.GetUpsertablePortfolioCashFlowsWithHttpInfo(scope, code, effectiveAt, windowStart, windowEnd, asAt, filter, recipeIdScope, recipeIdCode, excludeUnsettledTrades);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcustodianaccounts"></a>
## ListCustodianAccounts

> PagedResourceListOfCustodianAccount ListCustodianAccounts(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

ListCustodianAccounts: List Custodian Accounts

List the custodian accounts in a Transaction Portfolios

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfCustodianAccount result = apiInstance.ListCustodianAccounts(scope, code, effectiveAt, asAt, page, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Transaction Portfolio. |
| **code** | **string** | path | **required** | The code of the Transaction Portfolio. Together with the scope this uniquely identifies              the Transaction Portfolios. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties decorated on Custodian Accounts. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument. Defaults to              returning the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing custodian accounts; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Custodian Account type, specify \&quot;code eq &#39;001&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;CustodianAccount&#39; domain to decorate onto the Custodian Account.              These must have the format {domain}/{scope}/{code}, for example &#39;CustodianAccount/system/Name&#39;. |

### Return type

[PagedResourceListOfCustodianAccount](PagedResourceListOfCustodianAccount.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The custodian accounts in the given Transaction Portfolios. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCustodianAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCustodianAccount> response = apiInstance.ListCustodianAccountsWithHttpInfo(scope, code, effectiveAt, asAt, page, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listholdingsadjustments"></a>
## ListHoldingsAdjustments

> ResourceListOfHoldingsAdjustmentHeader ListHoldingsAdjustments(string scope, string code, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, DateTimeOffset? asAt = null)

ListHoldingsAdjustments: List holdings adjustments

List the holdings adjustments made to the specified transaction portfolio over a specified interval of effective time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfHoldingsAdjustmentHeader result = apiInstance.ListHoldingsAdjustments(scope, code, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve the holdings              adjustments. There is no lower bound if this is not specified. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The upper bound effective datetime or cut label (inclusive) from which to retrieve the holdings              adjustments. There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the holdings adjustments. Defaults to return the              latest version of each holding adjustment if not specified. |

### Return type

[ResourceListOfHoldingsAdjustmentHeader](ResourceListOfHoldingsAdjustmentHeader.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The record of holdings adjustments made to the specified transaction portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListHoldingsAdjustmentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfHoldingsAdjustmentHeader> response = apiInstance.ListHoldingsAdjustmentsWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listsettlementinstructions"></a>
## ListSettlementInstructions

> VersionedResourceListOfTransactionSettlementInstruction ListSettlementInstructions(string scope, string code, DateTimeOrCutLabel? fromDate = null, DateTimeOrCutLabel? toDate = null, string? page = null, int? limit = null, string? filter = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EARLY ACCESS] ListSettlementInstructions: List Settlement Instructions.

Display all the Settlement Instructions for a given Portfolio. The transaction Id filter can be ued to return instructions for an individual transaction.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromDate = "fromDate_example";  // DateTimeOrCutLabel? (optional)
var toDate = "toDate_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
VersionedResourceListOfTransactionSettlementInstruction result = apiInstance.ListSettlementInstructions(scope, code, fromDate, toDate, page, limit, filter, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio to retrieve settlement instructions for. |
| **code** | **string** | path | **required** | The code of the portfolio to retrieve settlement instructions for. |
| **fromDate** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve instructions.              There is no lower bound if this is not specified. |
| **toDate** | **DateTimeOrCutLabel?** | query | optional | The upper bound effective datetime or cut label (inclusive) from which to retrieve instructions. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing instructions; this value is returned from the previous call.              If a pagination token is provided, the filter, effectiveAt and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | The expression to filter out settlement instructions |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the settlement instructions. Defaults to return the latest if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;SettlementInstruction&#39;, &#39;Instrument&#39; or &#39;Portfolio&#39; domains to decorate onto              settlement instructions. These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39; or &#39;SettlementInstruction/strategy/quantsignal&#39;. |

### Return type

[VersionedResourceListOfTransactionSettlementInstruction](VersionedResourceListOfTransactionSettlementInstruction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Requested settlement instructions from the specified portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListSettlementInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfTransactionSettlementInstruction> response = apiInstance.ListSettlementInstructionsWithHttpInfo(scope, code, fromDate, toDate, page, limit, filter, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchportfoliodetails"></a>
## PatchPortfolioDetails

> PortfolioDetails PatchPortfolioDetails(string scope, string code, List<Operation> operation, DateTimeOrCutLabel? effectiveAt = null)

PatchPortfolioDetails: Patch portfolio details

Create or update certain details for a particular transaction portfolio.  Note that not all elements of a transaction portfolio definition are  modifiable once it has been created due to the potential implications for data already stored.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: BaseCurrency, AccountingMethod, SubHoldingKeys, AmortisationMethod, TransactionTypeScope, CashGainLossCalculationDate, InstrumentEventConfiguration, AmortisationRuleSetId, TaxRuleSetScope, SettlementConfiguration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
PortfolioDetails result = apiInstance.PatchPortfolioDetails(scope, code, operation, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the              scope this uniquely identifies the transaction portfolio. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The patch document. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the updated or inserted details should become valid.              Defaults to the current LUSID system datetime if not specified.              Note that this will affect all bitemporal fields (eg: SettlementConfiguration) in the request (but will not be used for any              perpetual fields). When patching a bitemporal field, the field will be updated from the              effectiveAt onwards and until the end of effective time. |

### Return type

[PortfolioDetails](PortfolioDetails.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched details |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchPortfolioDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioDetails> response = apiInstance.PatchPortfolioDetailsWithHttpInfo(scope, code, operation, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="previewtransaction"></a>
## PreviewTransaction

> ResourceListOfOutputTransaction PreviewTransaction(string scope, string code, TransactionRequest transactionRequest, List<string>? propertyKeys = null, bool? showCancelledTransactions = null, bool? preserveProperties = null, string? dataModelScope = null, string? dataModelCode = null)

PreviewTransaction: Preview a transaction

Returns the output-transaction(s) - e.g. as returned by BuildTransactions  that would come out of LUSID if the provided TransactionRequest was booked.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionRequest = new TransactionRequest(); // TransactionRequest
var propertyKeys = new List<string>?(); // List<string>? (optional)
var showCancelledTransactions = true;  // bool? (optional)
var preserveProperties = true;  // bool? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
ResourceListOfOutputTransaction result = apiInstance.PreviewTransaction(scope, code, transactionRequest, propertyKeys, showCancelledTransactions, preserveProperties, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionRequest** | [TransactionRequest](TransactionRequest.md) | body | **required** | The transaction to be previewed. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; or \&quot;Transaction\&quot; domain to decorate onto              the transactions. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or              \&quot;Transaction/strategy/quantsignal\&quot;. |
| **showCancelledTransactions** | **bool?** | query | optional | Option to specify whether to include previous versions of an amended transaction in the response.              Defaults to False if not specified. |
| **preserveProperties** | **bool?** | query | optional | If the preview transaction is an amendment to an existing transaction, then setting this to true will carry forward any unmodified properties from the earlier version. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[ResourceListOfOutputTransaction](ResourceListOfOutputTransaction.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The predicted output relating to the Preview Transaction. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PreviewTransactionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfOutputTransaction> response = apiInstance.PreviewTransactionWithHttpInfo(scope, code, transactionRequest, propertyKeys, showCancelledTransactions, preserveProperties, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="resolveinstrument"></a>
## ResolveInstrument

> UpsertPortfolioTransactionsResponse ResolveInstrument(string scope, string code, string instrumentIdentifierType, string instrumentIdentifierValue, DateTimeOrCutLabel? fromEffectiveAt = null, bool? reResolve = null, Dictionary<string, string>? requestBody = null)

ResolveInstrument: Resolve instrument

Try to resolve the instrument for transaction and holdings for a given instrument identifier and a specified  period of time. Also update the instrument identifiers with the given instrument identifiers collection.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var instrumentIdentifierType = "instrumentIdentifierType_example";  // string
var instrumentIdentifierValue = "instrumentIdentifierValue_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var reResolve = false;  // bool? (optional)
var requestBody = new Dictionary<string, string>?(); // Dictionary<string, string>? (optional)
UpsertPortfolioTransactionsResponse result = apiInstance.ResolveInstrument(scope, code, instrumentIdentifierType, instrumentIdentifierValue, fromEffectiveAt, reResolve, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **instrumentIdentifierType** | **string** | query | **required** | The instrument identifier type. |
| **instrumentIdentifierValue** | **string** | query | **required** | The value for the given instrument identifier. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no lower bound if this is not specified. |
| **reResolve** | **bool?** | query | optional | When set to true, instrument resolution will be attempted for all transactions and holdings for the given identifier and date range.              When set to false (default behaviour), instrument resolution will only be attempted for those transactions and holdings that were previously unresolved. Default: `false` |
| **requestBody** | [Dictionary&lt;string, string&gt;?](string.md) | body | optional | The dictionary with the instrument identifiers to be updated on the             transaction and holdings. |

### Return type

[UpsertPortfolioTransactionsResponse](UpsertPortfolioTransactionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the transaction portfolio that contains the newly updated or inserted transactions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ResolveInstrumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertPortfolioTransactionsResponse> response = apiInstance.ResolveInstrumentWithHttpInfo(scope, code, instrumentIdentifierType, instrumentIdentifierValue, fromEffectiveAt, reResolve, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setholdings"></a>
## SetHoldings

> AdjustHolding SetHoldings(string scope, string code, DateTimeOrCutLabel effectiveAt, List<AdjustHoldingRequest> adjustHoldingRequest, List<string>? reconciliationMethods = null, string? overrideMovementName = null, string? overrideOffsetMovementName = null)

SetHoldings: Set holdings

Set the holdings of the specified transaction portfolio to the provided targets. LUSID will automatically  construct adjustment transactions to ensure that the entire set of holdings for the transaction portfolio  are always set to the provided targets for the specified effective datetime. Read more about the difference between  adjusting and setting holdings here https://support.lusid.com/docs/how-do-i-manually-adjust-or-set-holdings.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var adjustHoldingRequest = new List<AdjustHoldingRequest>(); // List<AdjustHoldingRequest>
var reconciliationMethods = new List<string>?(); // List<string>? (optional)
var overrideMovementName = "overrideMovementName_example";  // string? (optional)
var overrideOffsetMovementName = "overrideOffsetMovementName_example";  // string? (optional)
AdjustHolding result = apiInstance.SetHoldings(scope, code, effectiveAt, adjustHoldingRequest, reconciliationMethods, overrideMovementName, overrideOffsetMovementName);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The effective datetime or cut label at which the holdings should be set to the provided targets. |
| **adjustHoldingRequest** | [List&lt;AdjustHoldingRequest&gt;](AdjustHoldingRequest.md) | body | **required** | The complete set of target holdings for the transaction portfolio. |
| **reconciliationMethods** | [List&lt;string&gt;?](string.md) | query | optional | Optional parameter for specifying a reconciliation method: e.g. FxForward. |
| **overrideMovementName** | **string?** | query | optional | Optional parameter to override movement name for the set holdings. |
| **overrideOffsetMovementName** | **string?** | query | optional | Optional parameter will create an additional offset movement for the set holdings with this new name and transaction type: CarryAsPnl |

### Return type

[AdjustHolding](AdjustHolding.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the transaction portfolio that contains the newly set holdings |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetHoldingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AdjustHolding> response = apiInstance.SetHoldingsWithHttpInfo(scope, code, effectiveAt, adjustHoldingRequest, reconciliationMethods, overrideMovementName, overrideOffsetMovementName);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcustodianaccounts"></a>
## UpsertCustodianAccounts

> CustodianAccountsUpsertResponse UpsertCustodianAccounts(string scope, string code, List<CustodianAccountRequest> custodianAccountRequest)

UpsertCustodianAccounts: Upsert Custodian Accounts

Create or update Custodian Accounts in the Transaction Portfolios. A Custodian Account will be updated  if it already exists and created if it does not.  The batch limit per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var custodianAccountRequest = new List<CustodianAccountRequest>(); // List<CustodianAccountRequest>
CustodianAccountsUpsertResponse result = apiInstance.UpsertCustodianAccounts(scope, code, custodianAccountRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Transaction Portfolio. |
| **code** | **string** | path | **required** | The code of the Transaction Portfolio. Together with the scope this uniquely identifies              the Transaction Portfolios. |
| **custodianAccountRequest** | [List&lt;CustodianAccountRequest&gt;](CustodianAccountRequest.md) | body | **required** | A list of Custodian Accounts to be created or updated. |

### Return type

[CustodianAccountsUpsertResponse](CustodianAccountsUpsertResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly upserted custodian accounts. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCustodianAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustodianAccountsUpsertResponse> response = apiInstance.UpsertCustodianAccountsWithHttpInfo(scope, code, custodianAccountRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcustodianaccountsproperties"></a>
## UpsertCustodianAccountsProperties

> CustodianAccountProperties UpsertCustodianAccountsProperties(string scope, string code, string custodianAccountScope, string custodianAccountCode, Dictionary<string, Property>? requestBody = null)

UpsertCustodianAccountsProperties: Upsert custodian accounts properties

Update or insert one or more properties onto a single custodian account. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'CustodianAccount'.                Upserting a property that exists for a Transaction Portfolios, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var custodianAccountScope = "custodianAccountScope_example";  // string
var custodianAccountCode = "custodianAccountCode_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
CustodianAccountProperties result = apiInstance.UpsertCustodianAccountsProperties(scope, code, custodianAccountScope, custodianAccountCode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Transaction Portfolios to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the Transaction Portfolios to update or insert the properties onto. Together with the scope this uniquely identifies the Transaction Portfolios. |
| **custodianAccountScope** | **string** | path | **required** | The scope of the Custodian Account to update or insert the properties onto. |
| **custodianAccountCode** | **string** | path | **required** | The unique ID of the custodian account to create or update properties for. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the Transaction Portfolio. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;CustodianAccount/Manager/Id\&quot;. |

### Return type

[CustodianAccountProperties](CustodianAccountProperties.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted properties |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCustodianAccountsPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustodianAccountProperties> response = apiInstance.UpsertCustodianAccountsPropertiesWithHttpInfo(scope, code, custodianAccountScope, custodianAccountCode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertportfoliodetails"></a>
## UpsertPortfolioDetails

> PortfolioDetails UpsertPortfolioDetails(string scope, string code, CreatePortfolioDetails createPortfolioDetails, DateTimeOrCutLabel? effectiveAt = null)

UpsertPortfolioDetails: Upsert portfolio details

Create or update certain details for a particular transaction portfolio. The details are updated if they already exist, and inserted if they do not.                Note that not all elements of a transaction portfolio definition are  modifiable once it has been created due to the potential implications for data already stored.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createPortfolioDetails = new CreatePortfolioDetails(); // CreatePortfolioDetails
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
PortfolioDetails result = apiInstance.UpsertPortfolioDetails(scope, code, createPortfolioDetails, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the               scope this uniquely identifies the transaction portfolio. |
| **createPortfolioDetails** | [CreatePortfolioDetails](CreatePortfolioDetails.md) | body | **required** | The details to create or update for the specified transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the updated or inserted details should become valid.               Defaults to the current LUSID system datetime if not specified. |

### Return type

[PortfolioDetails](PortfolioDetails.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly updated or inserted details |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPortfolioDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioDetails> response = apiInstance.UpsertPortfolioDetailsWithHttpInfo(scope, code, createPortfolioDetails, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertsettlementinstructions"></a>
## UpsertSettlementInstructions

> ResourceListOfTransactionSettlementInstruction UpsertSettlementInstructions(string scope, string code, List<SettlementInstructionRequest> settlementInstructionRequest)

[EARLY ACCESS] UpsertSettlementInstructions: Upsert Settlement Instructions.

Create or update instructions to settle specific transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var settlementInstructionRequest = new List<SettlementInstructionRequest>(); // List<SettlementInstructionRequest>
ResourceListOfTransactionSettlementInstruction result = apiInstance.UpsertSettlementInstructions(scope, code, settlementInstructionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. |
| **settlementInstructionRequest** | [List&lt;SettlementInstructionRequest&gt;](SettlementInstructionRequest.md) | body | **required** | The definition of the settlement instruction. |

### Return type

[ResourceListOfTransactionSettlementInstruction](ResourceListOfTransactionSettlementInstruction.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created or undated Settlement Instructions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertSettlementInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTransactionSettlementInstruction> response = apiInstance.UpsertSettlementInstructionsWithHttpInfo(scope, code, settlementInstructionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttransactionproperties"></a>
## UpsertTransactionProperties

> UpsertTransactionPropertiesResponse UpsertTransactionProperties(string scope, string code, string transactionId, Dictionary<string, PerpetualProperty> requestBody)

UpsertTransactionProperties: Upsert transaction properties

Create or update one or more transaction properties for a single transaction in the transaction portfolio.  Each property will be updated if it already exists and created if it does not.  Both transaction and portfolio must exist at the time when properties are created or updated.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionId = "transactionId_example";  // string
var requestBody = new Dictionary<string, PerpetualProperty>(); // Dictionary<string, PerpetualProperty>
UpsertTransactionPropertiesResponse result = apiInstance.UpsertTransactionProperties(scope, code, transactionId, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionId** | **string** | path | **required** | The unique ID of the transaction to create or update properties for. |
| **requestBody** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | body | **required** | The properties and their associated values to create or update. |

### Return type

[UpsertTransactionPropertiesResponse](UpsertTransactionPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the transaction portfolio that contains the newly updated or inserted transaction property |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTransactionPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertTransactionPropertiesResponse> response = apiInstance.UpsertTransactionPropertiesWithHttpInfo(scope, code, transactionId, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttransactions"></a>
## UpsertTransactions

> UpsertPortfolioTransactionsResponse UpsertTransactions(string scope, string code, List<TransactionRequest> transactionRequest, bool? preserveProperties = null, string? dataModelScope = null, string? dataModelCode = null)

UpsertTransactions: Upsert transactions

Create or update transactions in the transaction portfolio. A transaction will be updated  if it already exists and created if it does not.  The maximum number of transactions that this method can upsert per request is 10,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionRequest = new List<TransactionRequest>(); // List<TransactionRequest>
var preserveProperties = true;  // bool? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
UpsertPortfolioTransactionsResponse result = apiInstance.UpsertTransactions(scope, code, transactionRequest, preserveProperties, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the transaction portfolio. |
| **code** | **string** | path | **required** | The code of the transaction portfolio. Together with the scope this uniquely identifies              the transaction portfolio. |
| **transactionRequest** | [List&lt;TransactionRequest&gt;](TransactionRequest.md) | body | **required** | A list of transactions to be created or updated. |
| **preserveProperties** | **bool?** | query | optional | If set to false, the entire property set will be overwritten by the provided properties. If not specified or set to true, only the properties provided will be updated. Default: `true` |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[UpsertPortfolioTransactionsResponse](UpsertPortfolioTransactionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the transaction portfolio that contains the newly updated or inserted transactions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertPortfolioTransactionsResponse> response = apiInstance.UpsertTransactionsWithHttpInfo(scope, code, transactionRequest, preserveProperties, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

