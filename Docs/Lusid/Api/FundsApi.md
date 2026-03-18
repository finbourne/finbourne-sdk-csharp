# Finbourne.Sdk.Lusid.Api.FundsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AcceptEstimateValuationPoint**](#acceptestimatevaluationpoint) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/$acceptestimate` | [EXPERIMENTAL] AcceptEstimateValuationPoint: Accepts an Estimate Valuation Point. |
| [**CreateFee**](#createfee) | **POST** `/api/api/funds/{scope}/{code}/fees` | [EXPERIMENTAL] CreateFee: Create a Fee. |
| [**CreateFund**](#createfund) | **POST** `/api/api/funds/{scope}` | [EXPERIMENTAL] CreateFund: Create a Fund. |
| [**CreateFundV2**](#createfundv2) | **POST** `/api/api/funds/v2/{scope}` | [EXPERIMENTAL] CreateFundV2: Create a Fund V2 (Preview). |
| [**DeactivateNavTypes**](#deactivatenavtypes) | **POST** `/api/api/funds/{scope}/{code}/deactivateNavTypes` | [EXPERIMENTAL] DeactivateNavTypes: Deactivate NAV types on a Fund. |
| [**DeleteBookmark**](#deletebookmark) | **DELETE** `/api/api/funds/{scope}/{code}/bookmarks/{bookmarkCode}` | [EXPERIMENTAL] DeleteBookmark: Delete a Bookmark. |
| [**DeleteFee**](#deletefee) | **DELETE** `/api/api/funds/{scope}/{code}/fees/{feeCode}` | [EXPERIMENTAL] DeleteFee: Delete a Fee. |
| [**DeleteFund**](#deletefund) | **DELETE** `/api/api/funds/{scope}/{code}` | [EXPERIMENTAL] DeleteFund: Delete a Fund. |
| [**DeleteNavActivityAdjustments**](#deletenavactivityadjustments) | **POST** `/api/api/funds/{scope}/{code}/navAdjustment/$delete` | [EXPERIMENTAL] DeleteNavActivityAdjustments: Delete Nav activity adjustments. |
| [**DeleteValuationPoint**](#deletevaluationpoint) | **DELETE** `/api/api/funds/{scope}/{code}/valuationpoints/{diaryEntryCode}` | [EXPERIMENTAL] DeleteValuationPoint: Delete a Valuation Point. |
| [**FinaliseCandidateValuationPoint**](#finalisecandidatevaluationpoint) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/$finalisecandidate` | [EXPERIMENTAL] FinaliseCandidateValuationPoint: Finalise a Candidate Valuation Point. |
| [**GetFee**](#getfee) | **GET** `/api/api/funds/{scope}/{code}/fees/{feeCode}` | [EXPERIMENTAL] GetFee: Get a Fee for a specified Fund. |
| [**GetFeeProperties**](#getfeeproperties) | **GET** `/api/api/funds/{scope}/{code}/fees/{feeCode}/properties` | [EXPERIMENTAL] GetFeeProperties: Get Fee properties. |
| [**GetFund**](#getfund) | **GET** `/api/api/funds/{scope}/{code}` | [EXPERIMENTAL] GetFund: Get a Fund. |
| [**GetFundProperties**](#getfundproperties) | **GET** `/api/api/funds/{scope}/{code}/properties` | [EXPERIMENTAL] GetFundProperties: Get Fund properties. |
| [**GetHoldingContributorsForFund**](#getholdingcontributorsforfund) | **POST** `/api/api/funds/{scope}/{code}/holdings/{holdingId}/contributors` | [EXPERIMENTAL] GetHoldingContributorsForFund: Get holdings contributors for transaction portfolios in a Fund. |
| [**GetHoldingsForFund**](#getholdingsforfund) | **POST** `/api/api/funds/{scope}/{code}/$holdings` | [EXPERIMENTAL] GetHoldingsForFund: Get holdings for transaction portfolios in a Fund. |
| [**GetValuationForFund**](#getvaluationforfund) | **POST** `/api/api/funds/{scope}/{code}/$valuation` | [EXPERIMENTAL] GetValuationForFund: Perform valuation for a Fund. |
| [**GetValuationPointData**](#getvaluationpointdata) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/$query` | [EXPERIMENTAL] GetValuationPointData: Get Valuation Point Data for a Fund. |
| [**GetValuationPointJournalEntryLines**](#getvaluationpointjournalentrylines) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/journalentrylines/$query` | [EXPERIMENTAL] GetValuationPointJournalEntryLines: Get the Journal Entry Lines for the given Fund. |
| [**GetValuationPointPnlSummary**](#getvaluationpointpnlsummary) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/pnlsummary/$query` | [EXPERIMENTAL] GetValuationPointPnlSummary: Get a PnL summary for the given Valuation Point in the Fund. |
| [**GetValuationPointTransactions**](#getvaluationpointtransactions) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/transactions/$query` | [EXPERIMENTAL] GetValuationPointTransactions: Get the Transactions for the given Fund. |
| [**GetValuationPointTrialBalance**](#getvaluationpointtrialbalance) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/trialbalance/$query` | [EXPERIMENTAL] GetValuationPointTrialBalance: Get Trial Balance for the given Fund. |
| [**ListFees**](#listfees) | **GET** `/api/api/funds/{scope}/{code}/fees` | [EXPERIMENTAL] ListFees: List Fees for a specified Fund. |
| [**ListFundCalendar**](#listfundcalendar) | **GET** `/api/api/funds/{scope}/{code}/calendar` | [EXPERIMENTAL] ListFundCalendar: List Fund Calendar. |
| [**ListFundCalendarEntries**](#listfundcalendarentries) | **GET** `/api/api/funds/{scope}/{code}/calendars` | [EXPERIMENTAL] ListFundCalendarEntries: List Fund Calendar Entries. |
| [**ListFunds**](#listfunds) | **GET** `/api/api/funds` | [EXPERIMENTAL] ListFunds: List Funds. |
| [**ListNavActivityAdjustments**](#listnavactivityadjustments) | **GET** `/api/api/funds/{scope}/{code}/navAdjustment` | [EXPERIMENTAL] ListNavActivityAdjustments: List NAV adjustment activities applied to a valuation point |
| [**ListValuationPointOverview**](#listvaluationpointoverview) | **GET** `/api/api/funds/{scope}/{code}/valuationPointOverview` | [EXPERIMENTAL] ListValuationPointOverview: List Valuation Points Overview for a given Fund. |
| [**PatchFee**](#patchfee) | **PATCH** `/api/api/funds/{scope}/{code}/fees/{feeCode}` | [EXPERIMENTAL] PatchFee: Patch Fee. |
| [**PatchFund**](#patchfund) | **PATCH** `/api/api/funds/{scope}/{code}` | [EXPERIMENTAL] PatchFund: Patch a Fund. |
| [**RevertValuationPointToEstimate**](#revertvaluationpointtoestimate) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints/$reverttoestimate` | [EXPERIMENTAL] RevertValuationPointToEstimate: Reverts a Final Valuation Point to Estimate. |
| [**SetShareClassInstruments**](#setshareclassinstruments) | **PUT** `/api/api/funds/{scope}/{code}/shareclasses` | [EXPERIMENTAL] SetShareClassInstruments: Set the ShareClass Instruments on a Fund. |
| [**UpsertBookmark**](#upsertbookmark) | **POST** `/api/api/funds/{scope}/{code}/bookmarks` | [EXPERIMENTAL] UpsertBookmark: Upsert a bookmark. |
| [**UpsertDiaryEntryTypeValuationPoint**](#upsertdiaryentrytypevaluationpoint) | **POST** `/api/api/funds/{scope}/{code}/valuationpoints` | [EXPERIMENTAL] UpsertDiaryEntryTypeValuationPoint: Upsert a Valuation Point. |
| [**UpsertFeeProperties**](#upsertfeeproperties) | **POST** `/api/api/funds/{scope}/{code}/fees/{feeCode}/properties/$upsert` | [EXPERIMENTAL] UpsertFeeProperties: Upsert Fee properties. |
| [**UpsertFundProperties**](#upsertfundproperties) | **POST** `/api/api/funds/{scope}/{code}/properties/$upsert` | [EXPERIMENTAL] UpsertFundProperties: Upsert Fund properties. |
| [**UpsertNavActivityAdjustments**](#upsertnavactivityadjustments) | **POST** `/api/api/funds/{scope}/{code}/navAdjustment` | [EXPERIMENTAL] UpsertNavActivityAdjustments: Upsert NAV adjustment activities to a valuation point |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FundsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
```

---

<a id="acceptestimatevaluationpoint"></a>
## AcceptEstimateValuationPoint

> AcceptEstimateValuationPointResponse AcceptEstimateValuationPoint(string scope, string code, ValuationPointDataRequest valuationPointDataRequest, string? navTypeCode = null)

[EXPERIMENTAL] AcceptEstimateValuationPoint: Accepts an Estimate Valuation Point.

Accepts the specified estimate Valuation Point.  Should the Valuation Point differ since the Valuation Point was last run, both Valuation Points will be returned and status will be marked as 'Candidate',  otherwise it will be marked as 'Final'.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataRequest = new ValuationPointDataRequest(); // ValuationPointDataRequest
var navTypeCode = "navTypeCode_example";  // string? (optional)
AcceptEstimateValuationPointResponse result = apiInstance.AcceptEstimateValuationPoint(scope, code, valuationPointDataRequest, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataRequest** | [ValuationPointDataRequest](ValuationPointDataRequest.md) | body | **required** | The valuationPointDataRequest which contains the Diary Entry code for the Estimate Valuation Point to move to Candidate or Final state. |
| **navTypeCode** | **string?** | query | optional | When provided, accepts the Valuation Point of the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[AcceptEstimateValuationPointResponse](AcceptEstimateValuationPointResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Accepted Estimate point and status after being Accepted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AcceptEstimateValuationPointWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AcceptEstimateValuationPointResponse> response = apiInstance.AcceptEstimateValuationPointWithHttpInfo(scope, code, valuationPointDataRequest, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createfee"></a>
## CreateFee

> Fee CreateFee(string scope, string code, FeeRequest feeRequest, string? navTypeCode = null)

[EXPERIMENTAL] CreateFee: Create a Fee.

Create the given Fee.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var feeRequest = new FeeRequest(); // FeeRequest
var navTypeCode = "navTypeCode_example";  // string? (optional)
Fee result = apiInstance.CreateFee(scope, code, feeRequest, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **feeRequest** | [FeeRequest](FeeRequest.md) | body | **required** | The Fee to create. |
| **navTypeCode** | **string?** | query | optional | When provided, creates the Fee against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[Fee](Fee.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Fee. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fee> response = apiInstance.CreateFeeWithHttpInfo(scope, code, feeRequest, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createfund"></a>
## CreateFund

> Fund CreateFund(string scope, FundRequest fundRequest)

[EXPERIMENTAL] CreateFund: Create a Fund.

Create the given Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var fundRequest = new FundRequest(); // FundRequest
Fund result = apiInstance.CreateFund(scope, fundRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **fundRequest** | [FundRequest](FundRequest.md) | body | **required** | The definition of the Fund. |

### Return type

[Fund](Fund.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fund> response = apiInstance.CreateFundWithHttpInfo(scope, fundRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createfundv2"></a>
## CreateFundV2

> Fund CreateFundV2(string scope, FundDefinitionRequest fundDefinitionRequest)

[EXPERIMENTAL] CreateFundV2: Create a Fund V2 (Preview).

Create the given V2 Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var fundDefinitionRequest = new FundDefinitionRequest(); // FundDefinitionRequest
Fund result = apiInstance.CreateFundV2(scope, fundDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **fundDefinitionRequest** | [FundDefinitionRequest](FundDefinitionRequest.md) | body | **required** | The definition of the Fund. |

### Return type

[Fund](Fund.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateFundV2WithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fund> response = apiInstance.CreateFundV2WithHttpInfo(scope, fundDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deactivatenavtypes"></a>
## DeactivateNavTypes

> Fund DeactivateNavTypes(string scope, string code, List<string> requestBody, string? deleteMode = null)

[EXPERIMENTAL] DeactivateNavTypes: Deactivate NAV types on a Fund.

Deactivate the given NAV types on the Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new List<string>(); // List<string>
var deleteMode = "Soft";  // string? (optional)
Fund result = apiInstance.DeactivateNavTypes(scope, code, requestBody, deleteMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | The codes of the nav types to be deactivated. |
| **deleteMode** | **string?** | query | optional | The delete mode to use (defaults to &#39;Soft&#39;). |

### Return type

[Fund](Fund.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Fund with the specified NAV types deactivated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeactivateNavTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fund> response = apiInstance.DeactivateNavTypesWithHttpInfo(scope, code, requestBody, deleteMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletebookmark"></a>
## DeleteBookmark

> DeletedEntityResponse DeleteBookmark(string scope, string code, string bookmarkCode, string? navTypeCode = null)

[EXPERIMENTAL] DeleteBookmark: Delete a Bookmark.

Deletes the given Bookmark.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var bookmarkCode = "bookmarkCode_example";  // string
var navTypeCode = "navTypeCode_example";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteBookmark(scope, code, bookmarkCode, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **bookmarkCode** | **string** | path | **required** | The bookmark code for the bookmark to be deleted. |
| **navTypeCode** | **string?** | query | optional | When provided, deletes the Bookmark against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Bookmark was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteBookmarkWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteBookmarkWithHttpInfo(scope, code, bookmarkCode, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletefee"></a>
## DeleteFee

> DeletedEntityResponse DeleteFee(string scope, string code, string feeCode)

[EXPERIMENTAL] DeleteFee: Delete a Fee.

Delete the given Fee.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var feeCode = "feeCode_example";  // string
DeletedEntityResponse result = apiInstance.DeleteFee(scope, code, feeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **feeCode** | **string** | path | **required** | The code of the Fee to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Fee was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteFeeWithHttpInfo(scope, code, feeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletefund"></a>
## DeleteFund

> DeletedEntityResponse DeleteFund(string scope, string code)

[EXPERIMENTAL] DeleteFund: Delete a Fund.

Delete the given Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteFund(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund to be deleted. |
| **code** | **string** | path | **required** | The code of the Fund to be deleted. Together with the scope this uniquely identifies the Fund. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Fund was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteFundWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletenavactivityadjustments"></a>
## DeleteNavActivityAdjustments

> DeletedEntityResponse DeleteNavActivityAdjustments(string scope, string code, string valuationPointCode, List<NavActivityAdjustment> navActivityAdjustment, string? navTypeCode = null, string? valuationPointCodeVariant = null)

[EXPERIMENTAL] DeleteNavActivityAdjustments: Delete Nav activity adjustments.

Delete Nav activity adjustments on a Valuation Point.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointCode = "valuationPointCode_example";  // string
var navActivityAdjustment = new List<NavActivityAdjustment>(); // List<NavActivityAdjustment>
var navTypeCode = "navTypeCode_example";  // string? (optional)
var valuationPointCodeVariant = "valuationPointCodeVariant_example";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteNavActivityAdjustments(scope, code, valuationPointCode, navActivityAdjustment, navTypeCode, valuationPointCodeVariant);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope is the unique identifier for the given Fund. |
| **valuationPointCode** | **string** | query | **required** | The valuation point Code to delete the adjustment from |
| **navActivityAdjustment** | [List&lt;NavActivityAdjustment&gt;](NavActivityAdjustment.md) | body | **required** | The request describing the Nav activity adjustments to delete from a specific valuation point and nav type |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **valuationPointCodeVariant** | **string?** | query | optional | The variant of the valuation point used in the request. Together with the valuation point code marks the unique branch for the NavType. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Nav activity adjustments were deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteNavActivityAdjustmentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteNavActivityAdjustmentsWithHttpInfo(scope, code, valuationPointCode, navActivityAdjustment, navTypeCode, valuationPointCodeVariant);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletevaluationpoint"></a>
## DeleteValuationPoint

> DeletedEntityResponse DeleteValuationPoint(string scope, string code, string diaryEntryCode, string? diaryEntryCodeVariant = null, string? navTypeCode = null)

[EXPERIMENTAL] DeleteValuationPoint: Delete a Valuation Point.

Deletes the given Valuation Point.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var diaryEntryCode = "diaryEntryCode_example";  // string
var diaryEntryCodeVariant = "diaryEntryCodeVariant_example";  // string? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteValuationPoint(scope, code, diaryEntryCode, diaryEntryCodeVariant, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **diaryEntryCode** | **string** | path | **required** | The diary entry code for the valuation Point to be deleted. |
| **diaryEntryCodeVariant** | **string?** | query | optional | The variant of the valuation point used in the request. Together with the valuation point code marks the unique branch for the NavType. This is working only for the Estimates. |
| **navTypeCode** | **string?** | query | optional | When provided, deletes the Valuation Point against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Valuation Point was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteValuationPointWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteValuationPointWithHttpInfo(scope, code, diaryEntryCode, diaryEntryCodeVariant, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="finalisecandidatevaluationpoint"></a>
## FinaliseCandidateValuationPoint

> ValuationPointDataResponse FinaliseCandidateValuationPoint(string scope, string code, ValuationPointDataRequest valuationPointDataRequest, string? navTypeCode = null)

[EXPERIMENTAL] FinaliseCandidateValuationPoint: Finalise a Candidate Valuation Point.

Moves a 'Candidate' status Valuation Point to status 'Final'.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataRequest = new ValuationPointDataRequest(); // ValuationPointDataRequest
var navTypeCode = "navTypeCode_example";  // string? (optional)
ValuationPointDataResponse result = apiInstance.FinaliseCandidateValuationPoint(scope, code, valuationPointDataRequest, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataRequest** | [ValuationPointDataRequest](ValuationPointDataRequest.md) | body | **required** | The details of the Valuation Point to mark as final. |
| **navTypeCode** | **string?** | query | optional | When provided, finalises the Valuation Point of the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[ValuationPointDataResponse](ValuationPointDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Valuation Point response as a result of it be marked as Final. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the FinaliseCandidateValuationPointWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointDataResponse> response = apiInstance.FinaliseCandidateValuationPointWithHttpInfo(scope, code, valuationPointDataRequest, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfee"></a>
## GetFee

> Fee GetFee(string scope, string code, string feeCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetFee: Get a Fee for a specified Fund.

Retrieve a fee for a specified Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var feeCode = "feeCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Fee result = apiInstance.GetFee(scope, code, feeCode, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **feeCode** | **string** | path | **required** | The code of the Fee. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Fee properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Fee. Defaults to returning the latest version of the Fee if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Fee&#39; domain to decorate onto the Fee.              These must take the format {domain}/{scope}/{code}, for example &#39;Fee/Account/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[Fee](Fee.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fee definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fee> response = apiInstance.GetFeeWithHttpInfo(scope, code, feeCode, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfeeproperties"></a>
## GetFeeProperties

> FeeProperties GetFeeProperties(string scope, string code, string feeCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetFeeProperties: Get Fee properties.

Get all the properties of a single fee.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var feeCode = "feeCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
FeeProperties result = apiInstance.GetFeeProperties(scope, code, feeCode, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **feeCode** | **string** | path | **required** | The code of the Fee to get the properties for. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Fee&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Fee&#39;s properties. Defaults to return the latest version of each property if not specified. |

### Return type

[FeeProperties](FeeProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified fee |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFeePropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeProperties> response = apiInstance.GetFeePropertiesWithHttpInfo(scope, code, feeCode, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfund"></a>
## GetFund

> Fund GetFund(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetFund: Get a Fund.

Retrieve the definition of a particular Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Fund result = apiInstance.GetFund(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Fund properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Fund definition. Defaults to returning the latest version of the Fund definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Fund&#39; domain to decorate onto the Fund.              These must take the format {domain}/{scope}/{code}, for example &#39;Fund/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[Fund](Fund.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fund definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fund> response = apiInstance.GetFundWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getfundproperties"></a>
## GetFundProperties

> FundProperties GetFundProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetFundProperties: Get Fund properties.

Get all the properties of a single fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
FundProperties result = apiInstance.GetFundProperties(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund to list the properties for. |
| **code** | **string** | path | **required** | The code of the Fund to list the properties for. Together with the scope this uniquely identifies the Fund. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Fund&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Fund&#39;s properties. Defaults to return the latest version of each property if not specified. |

### Return type

[FundProperties](FundProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified fund |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetFundPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundProperties> response = apiInstance.GetFundPropertiesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdingcontributorsforfund"></a>
## GetHoldingContributorsForFund

> VersionedResourceListOfHoldingContributor GetHoldingContributorsForFund(string scope, string code, long holdingId, ValuationPointDataQueryParameters valuationPointDataQueryParameters, string? navTypeCode = null, bool? includeHistoric = null, string? taxLotId = null, bool? includeUnsettledMovements = null, int? limit = null, DateTimeOffset? asAt = null, string? page = null)

[EXPERIMENTAL] GetHoldingContributorsForFund: Get holdings contributors for transaction portfolios in a Fund.

Get the holdings of transaction portfolios in a specified Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var holdingId = 789L;  // long
var valuationPointDataQueryParameters = new ValuationPointDataQueryParameters(); // ValuationPointDataQueryParameters
var navTypeCode = "navTypeCode_example";  // string? (optional)
var includeHistoric = false;  // bool? (optional)
var taxLotId = "taxLotId_example";  // string? (optional)
var includeUnsettledMovements = false;  // bool? (optional)
var limit = 56;  // int? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
VersionedResourceListOfHoldingContributor result = apiInstance.GetHoldingContributorsForFund(scope, code, holdingId, valuationPointDataQueryParameters, navTypeCode, includeHistoric, taxLotId, includeUnsettledMovements, limit, asAt, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **holdingId** | **long** | path | **required** | The unique holding identifier |
| **valuationPointDataQueryParameters** | [ValuationPointDataQueryParameters](ValuationPointDataQueryParameters.md) | body | **required** | The arguments to use for querying the holdings.This can be a date, valuationPoint or a bookmark. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **includeHistoric** | **bool?** | query | optional | If true, transactions from previously closed holdings are returned.              If false, only transactions from last time position is opened. Default: `false` |
| **taxLotId** | **string?** | query | optional | Constrains the Holding Contributors to those which contributed to the specified tax lot. |
| **includeUnsettledMovements** | **bool?** | query | optional | If true, contributing transaction which have not settled yet will also be returned. False by default Default: `false` |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to build the transactions. Defaults to return the latest              version of each transaction if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to GetHoldingContributors. |

### Return type

[VersionedResourceListOfHoldingContributor](VersionedResourceListOfHoldingContributor.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested holding contributors from the specified Fund and NavType. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingContributorsForFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfHoldingContributor> response = apiInstance.GetHoldingContributorsForFundWithHttpInfo(scope, code, holdingId, valuationPointDataQueryParameters, navTypeCode, includeHistoric, taxLotId, includeUnsettledMovements, limit, asAt, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdingsforfund"></a>
## GetHoldingsForFund

> VersionedResourceListOfPortfolioHolding GetHoldingsForFund(string scope, string code, SingleValuationPointQueryParameters singleValuationPointQueryParameters, string? navTypeCode = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, bool? byTaxlots = null, int? includeSettlementEventsAfterDays = null)

[EXPERIMENTAL] GetHoldingsForFund: Get holdings for transaction portfolios in a Fund.

Get the holdings of transaction portfolios in a specified Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var singleValuationPointQueryParameters = new SingleValuationPointQueryParameters(); // SingleValuationPointQueryParameters
var navTypeCode = "navTypeCode_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var byTaxlots = true;  // bool? (optional)
var includeSettlementEventsAfterDays = 56;  // int? (optional)
VersionedResourceListOfPortfolioHolding result = apiInstance.GetHoldingsForFund(scope, code, singleValuationPointQueryParameters, navTypeCode, asAt, filter, propertyKeys, byTaxlots, includeSettlementEventsAfterDays);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **singleValuationPointQueryParameters** | [SingleValuationPointQueryParameters](SingleValuationPointQueryParameters.md) | body | **required** | The arguments to use for querying the holdings. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the holdings of transaction portfolios in the Fund. Defaults              to return the latest version of the holdings if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot;, \&quot;Holding\&quot; or \&quot;Portfolio\&quot; domain to decorate onto              the holdings. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or \&quot;Holding/system/Cost\&quot;. |
| **byTaxlots** | **bool?** | query | optional | Whether to expand the holdings to return the underlying tax-lots. Defaults to False. |
| **includeSettlementEventsAfterDays** | **int?** | query | optional | Number of days ahead to bring back settlements from, in relation to the specified effectiveAt. |

### Return type

[VersionedResourceListOfPortfolioHolding](VersionedResourceListOfPortfolioHolding.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The holdings of transaction portfolios for a Fund |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingsForFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfPortfolioHolding> response = apiInstance.GetHoldingsForFundWithHttpInfo(scope, code, singleValuationPointQueryParameters, navTypeCode, asAt, filter, propertyKeys, byTaxlots, includeSettlementEventsAfterDays);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationforfund"></a>
## GetValuationForFund

> ListAggregationResponse GetValuationForFund(string scope, string code, string? navTypeCode = null, FundValuationRequest? fundValuationRequest = null)

[EXPERIMENTAL] GetValuationForFund: Perform valuation for a Fund.

Perform valuation on a specified Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var navTypeCode = "navTypeCode_example";  // string? (optional)
var fundValuationRequest = new FundValuationRequest?(); // FundValuationRequest? (optional)
ListAggregationResponse result = apiInstance.GetValuationForFund(scope, code, navTypeCode, fundValuationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **fundValuationRequest** | [FundValuationRequest?](FundValuationRequest?.md) | body | optional | The request specifying the dates (or DiaryEntry) on which to calculate a set of valuation metrics. |

### Return type

[ListAggregationResponse](ListAggregationResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationForFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ListAggregationResponse> response = apiInstance.GetValuationForFundWithHttpInfo(scope, code, navTypeCode, fundValuationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationpointdata"></a>
## GetValuationPointData

> ValuationPointDataResponse GetValuationPointData(string scope, string code, ValuationPointDataQueryParameters valuationPointDataQueryParameters, DateTimeOffset? asAt = null, string? navTypeCode = null)

[EXPERIMENTAL] GetValuationPointData: Get Valuation Point Data for a Fund.

Retrieves the Valuation Point data between given dates or Valuation Point codes.  The endpoint will internally extract all 'Assets' and 'Liabilities' from the Fund's Trial balance to produce a GAV.  Start date will be assumed from the last 'official' ValuationPoint and EndDate will be as provided.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataQueryParameters = new ValuationPointDataQueryParameters(); // ValuationPointDataQueryParameters
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
ValuationPointDataResponse result = apiInstance.GetValuationPointData(scope, code, valuationPointDataQueryParameters, asAt, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataQueryParameters** | [ValuationPointDataQueryParameters](ValuationPointDataQueryParameters.md) | body | **required** | The arguments to use for querying the Valuation Point data. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Fund definition. Defaults to returning the latest version of the Fund definition if not specified. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[ValuationPointDataResponse](ValuationPointDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Valuation Point data for the Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationPointDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointDataResponse> response = apiInstance.GetValuationPointDataWithHttpInfo(scope, code, valuationPointDataQueryParameters, asAt, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationpointjournalentrylines"></a>
## GetValuationPointJournalEntryLines

> ValuationPointResourceListOfFundJournalEntryLine GetValuationPointJournalEntryLines(string scope, string code, ValuationPointDataQueryParameters valuationPointDataQueryParameters, string? generalLedgerProfileCode = null, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null, List<string>? propertyKeys = null, string? navTypeCode = null)

[EXPERIMENTAL] GetValuationPointJournalEntryLines: Get the Journal Entry Lines for the given Fund.

Gets the Journal Entry Lines for the given Valuation Point for a Fund.                The Journal Entry Lines have been generated from transactions, translated via posting rules and used in the valuation point.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataQueryParameters = new ValuationPointDataQueryParameters(); // ValuationPointDataQueryParameters
var generalLedgerProfileCode = "generalLedgerProfileCode_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
ValuationPointResourceListOfFundJournalEntryLine result = apiInstance.GetValuationPointJournalEntryLines(scope, code, valuationPointDataQueryParameters, generalLedgerProfileCode, asAt, filter, limit, page, propertyKeys, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataQueryParameters** | [ValuationPointDataQueryParameters](ValuationPointDataQueryParameters.md) | body | **required** | The arguments to use for querying the Journal Entry Lines. |
| **generalLedgerProfileCode** | **string?** | query | optional | The optional code of a General Ledger Profile used to decorate Journal Entry Lines with levels. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve Journal Entry Lines. Defaults to returning the latest version if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Journal Entry Lines from a previous call to GetValuationPointJournalEntryLines. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39;, &#39;Transaction&#39;, &#39;Portfolio&#39;, &#39;Account&#39;, &#39;LegalEntity&#39; or &#39;CustodianAccount&#39;               domain to decorate onto the Journal Entry Lines. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[ValuationPointResourceListOfFundJournalEntryLine](ValuationPointResourceListOfFundJournalEntryLine.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Journal Entry Lines for the specified Valuation Point for a Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationPointJournalEntryLinesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointResourceListOfFundJournalEntryLine> response = apiInstance.GetValuationPointJournalEntryLinesWithHttpInfo(scope, code, valuationPointDataQueryParameters, generalLedgerProfileCode, asAt, filter, limit, page, propertyKeys, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationpointpnlsummary"></a>
## GetValuationPointPnlSummary

> ValuationPointResourceListOfPnlJournalEntryLine GetValuationPointPnlSummary(string scope, string code, ValuationPointDataQueryParameters valuationPointDataQueryParameters, string? generalLedgerProfileCode = null, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null, string? navTypeCode = null)

[EXPERIMENTAL] GetValuationPointPnlSummary: Get a PnL summary for the given Valuation Point in the Fund.

Gets the PnL Summary lines from the Journal Entry Lines produced when calculating the Valuation Point.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataQueryParameters = new ValuationPointDataQueryParameters(); // ValuationPointDataQueryParameters
var generalLedgerProfileCode = "generalLedgerProfileCode_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
ValuationPointResourceListOfPnlJournalEntryLine result = apiInstance.GetValuationPointPnlSummary(scope, code, valuationPointDataQueryParameters, generalLedgerProfileCode, asAt, filter, limit, page, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataQueryParameters** | [ValuationPointDataQueryParameters](ValuationPointDataQueryParameters.md) | body | **required** | The arguments to use for generating the PnL summary. |
| **generalLedgerProfileCode** | **string?** | query | optional | The optional code of a General Ledger Profile used to decorate Journal Entry Lines with levels. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve PnL summary. Defaults to returning the latest version              of each transaction if not specified. |
| **filter** | **string?** | query | optional | \&quot;Expression to filter the result set.\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing results from a previous call to GetValuationPointPnlSummary. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[ValuationPointResourceListOfPnlJournalEntryLine](ValuationPointResourceListOfPnlJournalEntryLine.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested PnL summary for the specified Valuation Point for a Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationPointPnlSummaryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointResourceListOfPnlJournalEntryLine> response = apiInstance.GetValuationPointPnlSummaryWithHttpInfo(scope, code, valuationPointDataQueryParameters, generalLedgerProfileCode, asAt, filter, limit, page, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationpointtransactions"></a>
## GetValuationPointTransactions

> ValuationPointResourceListOfAccountedTransaction GetValuationPointTransactions(string scope, string code, ValuationPointDataQueryParameters valuationPointDataQueryParameters, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null, List<string>? propertyKeys = null, string? navTypeCode = null, string? dataModelScope = null, string? dataModelCode = null, bool? showCancelledTransactions = null, string? membershipType = null)

[EXPERIMENTAL] GetValuationPointTransactions: Get the Transactions for the given Fund.

Gets the Transactions for the given Valuation Point for a Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataQueryParameters = new ValuationPointDataQueryParameters(); // ValuationPointDataQueryParameters
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var showCancelledTransactions = true;  // bool? (optional)
var membershipType = "membershipType_example";  // string? (optional)
ValuationPointResourceListOfAccountedTransaction result = apiInstance.GetValuationPointTransactions(scope, code, valuationPointDataQueryParameters, asAt, filter, limit, page, propertyKeys, navTypeCode, dataModelScope, dataModelCode, showCancelledTransactions, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataQueryParameters** | [ValuationPointDataQueryParameters](ValuationPointDataQueryParameters.md) | body | **required** | The arguments to use for querying the transactions. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve transactions. Defaults to returning the latest version              of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to GetValuationPointTransactions. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39;, &#39;Transaction&#39;, &#39;Portfolio&#39;, &#39;Account&#39;, &#39;LegalEntity&#39; or &#39;CustodianAccount&#39;              domain to decorate onto the transactions. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |
| **showCancelledTransactions** | **bool?** | query | optional | Option to specify whether or not to include cancelled transactions,              including previous versions of transactions which have since been amended.              Defaults to False if not specified. |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[ValuationPointResourceListOfAccountedTransaction](ValuationPointResourceListOfAccountedTransaction.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested transactions for the specified Valuation Point for a Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationPointTransactionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointResourceListOfAccountedTransaction> response = apiInstance.GetValuationPointTransactionsWithHttpInfo(scope, code, valuationPointDataQueryParameters, asAt, filter, limit, page, propertyKeys, navTypeCode, dataModelScope, dataModelCode, showCancelledTransactions, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationpointtrialbalance"></a>
## GetValuationPointTrialBalance

> ValuationPointResourceListOfTrialBalance GetValuationPointTrialBalance(string scope, string code, ValuationPointDataQueryParameters valuationPointDataQueryParameters, string? generalLedgerProfileCode = null, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null, List<string>? propertyKeys = null, string? navTypeCode = null, bool? excludeCleardownModule = null)

[EXPERIMENTAL] GetValuationPointTrialBalance: Get Trial Balance for the given Fund.

Gets the Trial Balance for the given Valuation Point for a Fund.                The Trial Balance has been generated from transactions, translated via Posting Rules  and aggregated based on a General Ledger Profile (where specified).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointDataQueryParameters = new ValuationPointDataQueryParameters(); // ValuationPointDataQueryParameters
var generalLedgerProfileCode = "generalLedgerProfileCode_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
var excludeCleardownModule = false;  // bool? (optional)
ValuationPointResourceListOfTrialBalance result = apiInstance.GetValuationPointTrialBalance(scope, code, valuationPointDataQueryParameters, generalLedgerProfileCode, asAt, filter, limit, page, propertyKeys, navTypeCode, excludeCleardownModule);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **valuationPointDataQueryParameters** | [ValuationPointDataQueryParameters](ValuationPointDataQueryParameters.md) | body | **required** | The arguments to use for generating the Trial Balance. |
| **generalLedgerProfileCode** | **string?** | query | optional | The optional code of a General Ledger Profile used to decorate Journal Entry Lines with levels. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Trial Balance.               Defaults to returning the latest version if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results by.               For more information about filtering results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this number.               Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Trial Balances.               This token is returned from the previous call.               If a pagination token is provided, the filter, effectiveAt and asAt fields               must not have changed since the original request. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39;, &#39;Transaction&#39;, &#39;Portfolio&#39;, &#39;Account&#39;, &#39;LegalEntity&#39; or &#39;CustodianAccount&#39;               domain to decorate onto the TrialBalance. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **excludeCleardownModule** | **bool?** | query | optional | If this is set to true, no Cleardown Module will be applied to the Trial Balance. Defaults to false. Default: `false` |

### Return type

[ValuationPointResourceListOfTrialBalance](ValuationPointResourceListOfTrialBalance.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Trial Balance for the specified Valuation Point for a Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationPointTrialBalanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointResourceListOfTrialBalance> response = apiInstance.GetValuationPointTrialBalanceWithHttpInfo(scope, code, valuationPointDataQueryParameters, generalLedgerProfileCode, asAt, filter, limit, page, propertyKeys, navTypeCode, excludeCleardownModule);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfees"></a>
## ListFees

> PagedResourceListOfFee ListFees(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFees: List Fees for a specified Fund.

List all the Fees matching a particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFee result = apiInstance.ListFees(scope, code, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the Fees. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Fees. Defaults to returning the latest version of each Fee if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing fees; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the treatment, specify \&quot;treatment eq &#39;Monthly&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Fee&#39; domain to decorate onto each Fee.              These must take the format {domain}/{scope}/{code}, for example &#39;Fee/Account/Id&#39;. |

### Return type

[PagedResourceListOfFee](PagedResourceListOfFee.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fees. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFeesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFee> response = apiInstance.ListFeesWithHttpInfo(scope, code, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfundcalendar"></a>
## ListFundCalendar

> PagedResourceListOfFundCalendarEntry ListFundCalendar(string scope, string code, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFundCalendar: List Fund Calendar.

List all the Calendar Entries associated with the Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFundCalendarEntry result = apiInstance.ListFundCalendar(scope, code, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Calendar. Defaults to returning the latest version of each Calendar Entry if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Calendar Entries; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;ClosedPeriod&#39; domain to decorate onto each item. |

### Return type

[PagedResourceListOfFundCalendarEntry](PagedResourceListOfFundCalendarEntry.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fund Calendar Entries. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFundCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFundCalendarEntry> response = apiInstance.ListFundCalendarWithHttpInfo(scope, code, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfundcalendarentries"></a>
## ListFundCalendarEntries

> PagedResourceListOfFundCalendarEntries ListFundCalendarEntries(string scope, string code, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFundCalendarEntries: List Fund Calendar Entries.

List all the Calendar Entries associated with the Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFundCalendarEntries result = apiInstance.ListFundCalendarEntries(scope, code, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Calendar. Defaults to returning the latest version of each Calendar Entry if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Calendar Entries; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;DiaryEntry&#39; domain to decorate onto each item. |

### Return type

[PagedResourceListOfFundCalendarEntries](PagedResourceListOfFundCalendarEntries.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Fund Calendar Entries. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFundCalendarEntriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFundCalendarEntries> response = apiInstance.ListFundCalendarEntriesWithHttpInfo(scope, code, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listfunds"></a>
## ListFunds

> PagedResourceListOfFund ListFunds(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListFunds: List Funds.

List all the Funds matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfFund result = apiInstance.ListFunds(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the Funds. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Funds. Defaults to returning the latest version of each Fund if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Funds; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Fund code, specify \&quot;id.Code eq &#39;Fund1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Fund&#39; domain to decorate onto each Fund.              These must take the format {domain}/{scope}/{code}, for example &#39;Fund/Manager/Id&#39;. |

### Return type

[PagedResourceListOfFund](PagedResourceListOfFund.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Funds. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListFundsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfFund> response = apiInstance.ListFundsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listnavactivityadjustments"></a>
## ListNavActivityAdjustments

> ResourceListOfNavActivityAdjustment ListNavActivityAdjustments(string scope, string code, string valuationPointCode, string? navTypeCode = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, string? valuationPointCodeVariant = null)

[EXPERIMENTAL] ListNavActivityAdjustments: List NAV adjustment activities applied to a valuation point

Lists the NAV adjustment activities applied to the specified valuation point for a Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointCode = "valuationPointCode_example";  // string
var navTypeCode = "navTypeCode_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var valuationPointCodeVariant = "valuationPointCodeVariant_example";  // string? (optional)
ResourceListOfNavActivityAdjustment result = apiInstance.ListNavActivityAdjustments(scope, code, valuationPointCode, navTypeCode, asAt, page, limit, filter, valuationPointCodeVariant);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope is the unique identifier for the given Fund. |
| **valuationPointCode** | **string** | query | **required** | Fetch all NAV adjustment activities for this valuation point. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Nav activity adjustments. Defaults to returning the latest version of each adjustment if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Nav activity adjustments; this              value is returned from the previous call. If a pagination token is provided, the filter,              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **valuationPointCodeVariant** | **string?** | query | optional | The variant of the valuation point used in the request. Together with the valuation point code marks the unique branch for the NavType. |

### Return type

[ResourceListOfNavActivityAdjustment](ResourceListOfNavActivityAdjustment.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested NAV activity adjustments for the specific valuation point and Nav type for the Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListNavActivityAdjustmentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfNavActivityAdjustment> response = apiInstance.ListNavActivityAdjustmentsWithHttpInfo(scope, code, valuationPointCode, navTypeCode, asAt, page, limit, filter, valuationPointCodeVariant);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listvaluationpointoverview"></a>
## ListValuationPointOverview

> PagedResourceListOfValuationPointOverview ListValuationPointOverview(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null, string? navTypeCode = null)

[EXPERIMENTAL] ListValuationPointOverview: List Valuation Points Overview for a given Fund.

List the overview of all the Valuation Points that match the given criteria for a given Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var navTypeCode = "navTypeCode_example";  // string? (optional)
PagedResourceListOfValuationPointOverview result = apiInstance.ListValuationPointOverview(scope, code, effectiveAt, asAt, page, limit, filter, propertyKeys, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the Valuation Points. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Valuation Points. Defaults to returning the latest version of each Valuation Point if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Valuation Points; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results by.              For example, to filter on the NAV, specify \&quot;NAV gt 300\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;DiaryEntry&#39; domain to decorate onto each ValuationPoint.              These must take the format {domain}/{scope}/{code}, for example &#39;DiaryEntry/ValuationPoint/Id&#39;. |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[PagedResourceListOfValuationPointOverview](PagedResourceListOfValuationPointOverview.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The overviews of the requested Valuation Points. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListValuationPointOverviewWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfValuationPointOverview> response = apiInstance.ListValuationPointOverviewWithHttpInfo(scope, code, effectiveAt, asAt, page, limit, filter, propertyKeys, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchfee"></a>
## PatchFee

> Fee PatchFee(string scope, string code, string feeCode, List<Operation> operation)

[EXPERIMENTAL] PatchFee: Patch Fee.

Create or update certain fields for a particular Fee.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: EndDate, ShareClasses.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var feeCode = "feeCode_example";  // string
var operation = new List<Operation>(); // List<Operation>
Fee result = apiInstance.PatchFee(scope, code, feeCode, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **feeCode** | **string** | path | **required** | The code of the Fee. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[Fee](Fee.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched Fee. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchFeeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fee> response = apiInstance.PatchFeeWithHttpInfo(scope, code, feeCode, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchfund"></a>
## PatchFund

> Fund PatchFund(string scope, string code, List<Operation> operation)

[EXPERIMENTAL] PatchFund: Patch a Fund.

Update fields on a Fund.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description, PortfolioIds, FundConfigurationId, ShareClassInstruments, Type, InceptionDate, DecimalPlaces, PrimaryNavType, AdditionalNavTypes, AborId, YearEndDate.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
Fund result = apiInstance.PatchFund(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[Fund](Fund.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Fund. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchFundWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fund> response = apiInstance.PatchFundWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="revertvaluationpointtoestimate"></a>
## RevertValuationPointToEstimate

> ValuationPointDataResponse RevertValuationPointToEstimate(string scope, string code, RevertValuationPointDataRequest revertValuationPointDataRequest, string? navTypeCode = null)

[EXPERIMENTAL] RevertValuationPointToEstimate: Reverts a Final Valuation Point to Estimate.

Moves a 'Final' status Valuation Point to status 'Estimate'.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var revertValuationPointDataRequest = new RevertValuationPointDataRequest(); // RevertValuationPointDataRequest
var navTypeCode = "navTypeCode_example";  // string? (optional)
ValuationPointDataResponse result = apiInstance.RevertValuationPointToEstimate(scope, code, revertValuationPointDataRequest, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **revertValuationPointDataRequest** | [RevertValuationPointDataRequest](RevertValuationPointDataRequest.md) | body | **required** | The revertValuationPointRequest which contains the Diary Entry code for the Final Valuation Point to move to Estimate status. |
| **navTypeCode** | **string?** | query | optional | When provided, sets the status of the Valuation Point of the specified NAV Type to be Estimate.              Otherwise, the Primary NAV Type will be used. |

### Return type

[ValuationPointDataResponse](ValuationPointDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Valuation Point response as a result of it be marked as Estimate. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RevertValuationPointToEstimateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationPointDataResponse> response = apiInstance.RevertValuationPointToEstimateWithHttpInfo(scope, code, revertValuationPointDataRequest, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setshareclassinstruments"></a>
## SetShareClassInstruments

> Fund SetShareClassInstruments(string scope, string code, SetShareClassInstrumentsRequest setShareClassInstrumentsRequest)

[EXPERIMENTAL] SetShareClassInstruments: Set the ShareClass Instruments on a Fund.

Update the ShareClass Instruments on an existing Fund with the set of instruments provided.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var setShareClassInstrumentsRequest = new SetShareClassInstrumentsRequest(); // SetShareClassInstrumentsRequest
Fund result = apiInstance.SetShareClassInstruments(scope, code, setShareClassInstrumentsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **setShareClassInstrumentsRequest** | [SetShareClassInstrumentsRequest](SetShareClassInstrumentsRequest.md) | body | **required** | The scopes and instrument identifiers for the instruments to be set. |

### Return type

[Fund](Fund.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Fund definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetShareClassInstrumentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Fund> response = apiInstance.SetShareClassInstrumentsWithHttpInfo(scope, code, setShareClassInstrumentsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertbookmark"></a>
## UpsertBookmark

> FundCalendarEntry UpsertBookmark(string scope, string code, UpsertFundBookmarkRequest upsertFundBookmarkRequest, string? navTypeCode = null)

[EXPERIMENTAL] UpsertBookmark: Upsert a bookmark.

This method will update or upsert a Bookmark for the Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertFundBookmarkRequest = new UpsertFundBookmarkRequest(); // UpsertFundBookmarkRequest
var navTypeCode = "navTypeCode_example";  // string? (optional)
FundCalendarEntry result = apiInstance.UpsertBookmark(scope, code, upsertFundBookmarkRequest, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **upsertFundBookmarkRequest** | [UpsertFundBookmarkRequest](UpsertFundBookmarkRequest.md) | body | **required** | The bookmark definition to upsert. |
| **navTypeCode** | **string?** | query | optional | When provided, upserts the Valuation Point against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[FundCalendarEntry](FundCalendarEntry.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted Bookmark |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertBookmarkWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundCalendarEntry> response = apiInstance.UpsertBookmarkWithHttpInfo(scope, code, upsertFundBookmarkRequest, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertdiaryentrytypevaluationpoint"></a>
## UpsertDiaryEntryTypeValuationPoint

> DiaryEntry UpsertDiaryEntryTypeValuationPoint(string scope, string code, UpsertValuationPointRequest upsertValuationPointRequest, string? navTypeCode = null)

[EXPERIMENTAL] UpsertDiaryEntryTypeValuationPoint: Upsert a Valuation Point.

Insert the estimate Valuation Point.                If the Valuation Point does not exist, this method will create it in estimate state.                It is not possible to update an existing Valuation Point. As an alternative, the Valuation Point could be deleted and recreated.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertValuationPointRequest = new UpsertValuationPointRequest(); // UpsertValuationPointRequest
var navTypeCode = "navTypeCode_example";  // string? (optional)
DiaryEntry result = apiInstance.UpsertDiaryEntryTypeValuationPoint(scope, code, upsertValuationPointRequest, navTypeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **upsertValuationPointRequest** | [UpsertValuationPointRequest](UpsertValuationPointRequest.md) | body | **required** | The Valuation Point Estimate definition to upsert. |
| **navTypeCode** | **string?** | query | optional | When provided, upserts the Valuation Point against the specified NAV Type, otherwise the Primary NAV Type will be used. |

### Return type

[DiaryEntry](DiaryEntry.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted estimated Valuation Point |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertDiaryEntryTypeValuationPointWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DiaryEntry> response = apiInstance.UpsertDiaryEntryTypeValuationPointWithHttpInfo(scope, code, upsertValuationPointRequest, navTypeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertfeeproperties"></a>
## UpsertFeeProperties

> FeeProperties UpsertFeeProperties(string scope, string code, string feeCode, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertFeeProperties: Upsert Fee properties.

Update or insert one or more properties onto a single Fee. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'Fee'.                Upserting a property that exists for an Fee, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var feeCode = "feeCode_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
FeeProperties result = apiInstance.UpsertFeeProperties(scope, code, feeCode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **feeCode** | **string** | path | **required** | The code of the Fee to update or insert the properties onto. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the Fee. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;Fee/Manager/Id\&quot;. |

### Return type

[FeeProperties](FeeProperties.md)

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
<summary>Using the UpsertFeePropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FeeProperties> response = apiInstance.UpsertFeePropertiesWithHttpInfo(scope, code, feeCode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertfundproperties"></a>
## UpsertFundProperties

> FundProperties UpsertFundProperties(string scope, string code, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertFundProperties: Upsert Fund properties.

Update or insert one or more properties onto a single Fund. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'Fund'.                Upserting a property that exists for an Fund, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
FundProperties result = apiInstance.UpsertFundProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope this uniquely identifies the Fund. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the Fund. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;Fund/Manager/Id\&quot;. |

### Return type

[FundProperties](FundProperties.md)

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
<summary>Using the UpsertFundPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<FundProperties> response = apiInstance.UpsertFundPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertnavactivityadjustments"></a>
## UpsertNavActivityAdjustments

> DateTimeOffset UpsertNavActivityAdjustments(string scope, string code, string valuationPointCode, List<NavActivityAdjustment> navActivityAdjustment, string? navTypeCode = null, string? valuationPointCodeVariant = null)

[EXPERIMENTAL] UpsertNavActivityAdjustments: Upsert NAV adjustment activities to a valuation point

Upserts the NAV adjustment activities to the specified valuation point for a Fund.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var valuationPointCode = "valuationPointCode_example";  // string
var navActivityAdjustment = new List<NavActivityAdjustment>(); // List<NavActivityAdjustment>
var navTypeCode = "navTypeCode_example";  // string? (optional)
var valuationPointCodeVariant = "valuationPointCodeVariant_example";  // string? (optional)
DateTimeOffset result = apiInstance.UpsertNavActivityAdjustments(scope, code, valuationPointCode, navActivityAdjustment, navTypeCode, valuationPointCodeVariant);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Fund. |
| **code** | **string** | path | **required** | The code of the Fund. Together with the scope is the unique identifier for the given Fund. |
| **valuationPointCode** | **string** | query | **required** | The valuation point Code to apply the adjustment to |
| **navActivityAdjustment** | [List&lt;NavActivityAdjustment&gt;](NavActivityAdjustment.md) | body | **required** | The request describing the Nav activity adjustments to apply to a specific valuation point and nav type |
| **navTypeCode** | **string?** | query | optional | When provided, runs against the specified NAV Type, otherwise the Primary NAV Type will be used. |
| **valuationPointCodeVariant** | **string?** | query | optional | The variant of the valuation point used in the request. Together with the valuation point code marks the unique branch for the NavType. |

### Return type

**DateTimeOffset**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The date and time of the successfully applied Nav Activity Adjustments. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertNavActivityAdjustmentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DateTimeOffset> response = apiInstance.UpsertNavActivityAdjustmentsWithHttpInfo(scope, code, valuationPointCode, navActivityAdjustment, navTypeCode, valuationPointCodeVariant);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

