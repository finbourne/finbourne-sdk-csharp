# Finbourne.Sdk.Lusid.Api.AborApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddDiaryEntry**](#adddiaryentry) | **POST** `/api/api/abor/{scope}/{code}/accountingdiary` | [EXPERIMENTAL] AddDiaryEntry: Add a diary entry to the specified Abor. This would be type &#39;Other&#39;. |
| [**ClosePeriod**](#closeperiod) | **POST** `/api/api/abor/{scope}/{code}/accountingdiary/$closeperiod` | [EXPERIMENTAL] ClosePeriod: Closes or locks the current period for the given Abor. |
| [**CreateAbor**](#createabor) | **POST** `/api/api/abor/{scope}` | [EXPERIMENTAL] CreateAbor: Create an Abor. |
| [**DeleteAbor**](#deleteabor) | **DELETE** `/api/api/abor/{scope}/{code}` | [EXPERIMENTAL] DeleteAbor: Delete an Abor. |
| [**DeleteDiaryEntry**](#deletediaryentry) | **DELETE** `/api/api/abor/{scope}/{code}/accountingdiary/{diaryEntryCode}` | [EXPERIMENTAL] DeleteDiaryEntry: Delete a diary entry type &#39;Other&#39; from the specified Abor. |
| [**GetAbor**](#getabor) | **GET** `/api/api/abor/{scope}/{code}` | [EXPERIMENTAL] GetAbor: Get Abor. |
| [**GetAborProperties**](#getaborproperties) | **GET** `/api/api/abor/{scope}/{code}/properties` | [EXPERIMENTAL] GetAborProperties: Get Abor properties |
| [**GetJournalEntryLines**](#getjournalentrylines) | **POST** `/api/api/abor/{scope}/{code}/journalentrylines/$query` | [EXPERIMENTAL] GetJournalEntryLines: Get the Journal Entry lines for the given Abor. |
| [**GetTrialBalance**](#gettrialbalance) | **POST** `/api/api/abor/{scope}/{code}/trialbalance/$query` | [EXPERIMENTAL] GetTrialBalance: Get the Trial Balance for the given Abor. |
| [**ListAbors**](#listabors) | **GET** `/api/api/abor` | [EXPERIMENTAL] ListAbors: List Abors. |
| [**ListDiaryEntries**](#listdiaryentries) | **GET** `/api/api/abor/{scope}/{code}/accountingdiary` | [EXPERIMENTAL] ListDiaryEntries: List diary entries. |
| [**LockPeriod**](#lockperiod) | **POST** `/api/api/abor/{scope}/{code}/accountingdiary/$lockperiod` | [EXPERIMENTAL] LockPeriod: Locks the last Closed or given Closed Period. |
| [**PatchAbor**](#patchabor) | **PATCH** `/api/api/abor/{scope}/{code}` | [EXPERIMENTAL] PatchAbor: Patch Abor. |
| [**ReOpenPeriods**](#reopenperiods) | **POST** `/api/api/abor/{scope}/{code}/accountingdiary/$reopenperiods` | [EXPERIMENTAL] ReOpenPeriods: Reopen periods from a seed Diary Entry Code or when not specified, the last Closed Period for the given Abor. |
| [**UpsertAborProperties**](#upsertaborproperties) | **POST** `/api/api/abor/{scope}/{code}/properties/$upsert` | [EXPERIMENTAL] UpsertAborProperties: Upsert Abor properties |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AborApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
```

---

<a id="adddiaryentry"></a>
## AddDiaryEntry

> DiaryEntry AddDiaryEntry(string scope, string code, DiaryEntryRequest diaryEntryRequest)

[EXPERIMENTAL] AddDiaryEntry: Add a diary entry to the specified Abor. This would be type 'Other'.

Adds a new diary entry to the specified Abor

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var diaryEntryRequest = new DiaryEntryRequest(); // DiaryEntryRequest
DiaryEntry result = apiInstance.AddDiaryEntry(scope, code, diaryEntryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. |
| **diaryEntryRequest** | [DiaryEntryRequest](DiaryEntryRequest.md) | body | **required** | The diary entry to add. |

### Return type

[DiaryEntry](DiaryEntry.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly added diary entry. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddDiaryEntryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DiaryEntry> response = apiInstance.AddDiaryEntryWithHttpInfo(scope, code, diaryEntryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="closeperiod"></a>
## ClosePeriod

> DiaryEntry ClosePeriod(string scope, string code, ClosePeriodDiaryEntryRequest closePeriodDiaryEntryRequest)

[EXPERIMENTAL] ClosePeriod: Closes or locks the current period for the given Abor.

Closes or Locks the current open period for the given Abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var closePeriodDiaryEntryRequest = new ClosePeriodDiaryEntryRequest(); // ClosePeriodDiaryEntryRequest
DiaryEntry result = apiInstance.ClosePeriod(scope, code, closePeriodDiaryEntryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. |
| **closePeriodDiaryEntryRequest** | [ClosePeriodDiaryEntryRequest](ClosePeriodDiaryEntryRequest.md) | body | **required** | The request body, containing details to apply to the closing/locking period. |

### Return type

[DiaryEntry](DiaryEntry.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The DiaryEntry created as a result of the closing of the Period. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ClosePeriodWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DiaryEntry> response = apiInstance.ClosePeriodWithHttpInfo(scope, code, closePeriodDiaryEntryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createabor"></a>
## CreateAbor

> Abor CreateAbor(string scope, AborRequest aborRequest)

[EXPERIMENTAL] CreateAbor: Create an Abor.

Create the given Abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var aborRequest = new AborRequest(); // AborRequest
Abor result = apiInstance.CreateAbor(scope, aborRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **aborRequest** | [AborRequest](AborRequest.md) | body | **required** | The definition of the Abor. |

### Return type

[Abor](Abor.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created abor. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateAborWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Abor> response = apiInstance.CreateAborWithHttpInfo(scope, aborRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteabor"></a>
## DeleteAbor

> DeletedEntityResponse DeleteAbor(string scope, string code)

[EXPERIMENTAL] DeleteAbor: Delete an Abor.

Delete the given Abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteAbor(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor to be deleted. |
| **code** | **string** | path | **required** | The code of the Abor to be deleted. Together with the scope this uniquely identifies the Abor. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Abor was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteAborWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteAborWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletediaryentry"></a>
## DeleteDiaryEntry

> DeletedEntityResponse DeleteDiaryEntry(string scope, string code, string diaryEntryCode)

[EXPERIMENTAL] DeleteDiaryEntry: Delete a diary entry type 'Other' from the specified Abor.

Delete a diary entry type 'Other' from the specified Abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var diaryEntryCode = "diaryEntryCode_example";  // string
DeletedEntityResponse result = apiInstance.DeleteDiaryEntry(scope, code, diaryEntryCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. |
| **diaryEntryCode** | **string** | path | **required** | The diary entry code to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Cleardown Module was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteDiaryEntryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteDiaryEntryWithHttpInfo(scope, code, diaryEntryCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getabor"></a>
## GetAbor

> Abor GetAbor(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetAbor: Get Abor.

Retrieve the definition of a particular Abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Abor result = apiInstance.GetAbor(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. Together with the scope this uniquely identifies the Abor. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Abor properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Abor definition. Defaults to returning the latest version of the Abor definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Abor&#39; domain to decorate onto the Abor.              These must take the format {domain}/{scope}/{code}, for example &#39;Abor/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[Abor](Abor.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Abor definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAborWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Abor> response = apiInstance.GetAborWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaborproperties"></a>
## GetAborProperties

> AborProperties GetAborProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAborProperties: Get Abor properties

Get all the properties of a single abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AborProperties result = apiInstance.GetAborProperties(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor to list the properties for. |
| **code** | **string** | path | **required** | The code of the Abor to list the properties for. Together with the scope this uniquely identifies the Abor. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Abor&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Abor&#39;s properties. Defaults to return the latest version of each property if not specified. |

### Return type

[AborProperties](AborProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified abor |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAborPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborProperties> response = apiInstance.GetAborPropertiesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getjournalentrylines"></a>
## GetJournalEntryLines

> VersionedResourceListOfJournalEntryLine GetJournalEntryLines(string scope, string code, JournalEntryLinesQueryParameters journalEntryLinesQueryParameters, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EXPERIMENTAL] GetJournalEntryLines: Get the Journal Entry lines for the given Abor.

Gets the Journal Entry lines for the given Abor                The Journal Entry lines have been generated from transactions and translated via posting rules

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var journalEntryLinesQueryParameters = new JournalEntryLinesQueryParameters(); // JournalEntryLinesQueryParameters
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
VersionedResourceListOfJournalEntryLine result = apiInstance.GetJournalEntryLines(scope, code, journalEntryLinesQueryParameters, asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. Together with the scope is creating the unique identifier for the given Abor. |
| **journalEntryLinesQueryParameters** | [JournalEntryLinesQueryParameters](JournalEntryLinesQueryParameters.md) | body | **required** | The query parameters used in running the generation of the Journal Entry lines. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve Journal Entry lines. Defaults to returning the latest version               of each transaction if not specified. |
| **filter** | **string?** | query | optional | \&quot;Expression to filter the result set.\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Journal Entry lines from a previous call to GetJournalEntryLines. |

### Return type

[VersionedResourceListOfJournalEntryLine](VersionedResourceListOfJournalEntryLine.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Journal Entry lines for the specified Abor. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetJournalEntryLinesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfJournalEntryLine> response = apiInstance.GetJournalEntryLinesWithHttpInfo(scope, code, journalEntryLinesQueryParameters, asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettrialbalance"></a>
## GetTrialBalance

> VersionedResourceListOfTrialBalance GetTrialBalance(string scope, string code, TrialBalanceQueryParameters trialBalanceQueryParameters, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EXPERIMENTAL] GetTrialBalance: Get the Trial Balance for the given Abor.

Gets the Trial Balance for the given Abor.    The Trial Balance has been generated from transactions, translated via Posting Rules  and aggregated based on a General Ledger Profile (where specified).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var trialBalanceQueryParameters = new TrialBalanceQueryParameters(); // TrialBalanceQueryParameters
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
VersionedResourceListOfTrialBalance result = apiInstance.GetTrialBalance(scope, code, trialBalanceQueryParameters, asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. Together with the scope this uniquely identifies the Abor. |
| **trialBalanceQueryParameters** | [TrialBalanceQueryParameters](TrialBalanceQueryParameters.md) | body | **required** | The query parameters used in running the generation of the Trial Balance. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Trial Balance.              Defaults to returning the latest version if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results by.              For more information about filtering results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many.              Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Trial Balances.              This token is returned from the previous call.              If a pagination token is provided, the filter, effectiveAt and asAt fields              must not have changed since the original request. |

### Return type

[VersionedResourceListOfTrialBalance](VersionedResourceListOfTrialBalance.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Trial Balance for the specified Abor. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTrialBalanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfTrialBalance> response = apiInstance.GetTrialBalanceWithHttpInfo(scope, code, trialBalanceQueryParameters, asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listabors"></a>
## ListAbors

> PagedResourceListOfAbor ListAbors(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListAbors: List Abors.

List all the Abors matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfAbor result = apiInstance.ListAbors(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the Abor. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Abor. Defaults to returning the latest version of each Abor if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Abor; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Abor type, specify \&quot;id.Code eq &#39;Abor1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Abor&#39; domain to decorate onto each Abor.              These must take the format {domain}/{scope}/{code}, for example &#39;Abor/Manager/Id&#39;. |

### Return type

[PagedResourceListOfAbor](PagedResourceListOfAbor.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested abors. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAborsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAbor> response = apiInstance.ListAborsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listdiaryentries"></a>
## ListDiaryEntries

> PagedResourceListOfDiaryEntry ListDiaryEntries(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListDiaryEntries: List diary entries.

List all the diary entries matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfDiaryEntry result = apiInstance.ListDiaryEntries(scope, code, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the Diary Entries. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the DiaryEntry. Defaults to returning the latest version of each DiaryEntry if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing diary entries; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the DiaryEntry type, specify \&quot;type eq &#39;PeriodBoundary&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;DiaryEntry&#39; domain to decorate onto each DiaryEntry.              These must take the format {domain}/{scope}/{code}, for example &#39;DiaryEntry/Report/Id&#39;. |

### Return type

[PagedResourceListOfDiaryEntry](PagedResourceListOfDiaryEntry.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested diary entries. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListDiaryEntriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfDiaryEntry> response = apiInstance.ListDiaryEntriesWithHttpInfo(scope, code, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="lockperiod"></a>
## LockPeriod

> DiaryEntry LockPeriod(string scope, string code, LockPeriodDiaryEntryRequest? lockPeriodDiaryEntryRequest = null)

[EXPERIMENTAL] LockPeriod: Locks the last Closed or given Closed Period.

Locks the specified or last locked period for the given Abor.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var lockPeriodDiaryEntryRequest = new LockPeriodDiaryEntryRequest?(); // LockPeriodDiaryEntryRequest? (optional)
DiaryEntry result = apiInstance.LockPeriod(scope, code, lockPeriodDiaryEntryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. |
| **lockPeriodDiaryEntryRequest** | [LockPeriodDiaryEntryRequest?](LockPeriodDiaryEntryRequest?.md) | body | optional | The request body, detailing lock details |

### Return type

[DiaryEntry](DiaryEntry.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated DiaryEntry as a result of the locking of the Period. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the LockPeriodWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DiaryEntry> response = apiInstance.LockPeriodWithHttpInfo(scope, code, lockPeriodDiaryEntryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchabor"></a>
## PatchAbor

> Abor PatchAbor(string scope, string code, List<Operation> operation)

[EXPERIMENTAL] PatchAbor: Patch Abor.

Create or update certain fields for a particular Abor.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: PortfolioIds.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
Abor result = apiInstance.PatchAbor(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. Together with the              scope this uniquely identifies the Abor. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[Abor](Abor.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched Abor |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchAborWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Abor> response = apiInstance.PatchAborWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reopenperiods"></a>
## ReOpenPeriods

> PeriodDiaryEntriesReopenedResponse ReOpenPeriods(string scope, string code, ReOpenPeriodDiaryEntryRequest? reOpenPeriodDiaryEntryRequest = null)

[EXPERIMENTAL] ReOpenPeriods: Reopen periods from a seed Diary Entry Code or when not specified, the last Closed Period for the given Abor.

Reopens one or more periods.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var reOpenPeriodDiaryEntryRequest = new ReOpenPeriodDiaryEntryRequest?(); // ReOpenPeriodDiaryEntryRequest? (optional)
PeriodDiaryEntriesReopenedResponse result = apiInstance.ReOpenPeriods(scope, code, reOpenPeriodDiaryEntryRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor. |
| **code** | **string** | path | **required** | The code of the Abor. Together with the scope this uniquely identifies the Abor. |
| **reOpenPeriodDiaryEntryRequest** | [ReOpenPeriodDiaryEntryRequest?](ReOpenPeriodDiaryEntryRequest?.md) | body | optional | The request body, containing details about the period to be re-opened. |

### Return type

[PeriodDiaryEntriesReopenedResponse](PeriodDiaryEntriesReopenedResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the DiaryEntryCodes were deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReOpenPeriodsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PeriodDiaryEntriesReopenedResponse> response = apiInstance.ReOpenPeriodsWithHttpInfo(scope, code, reOpenPeriodDiaryEntryRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertaborproperties"></a>
## UpsertAborProperties

> AborProperties UpsertAborProperties(string scope, string code, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertAborProperties: Upsert Abor properties

Update or insert one or more properties onto a single Abor. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'Abor'.                Upserting a property that exists for an Abor, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AborApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
AborProperties result = apiInstance.UpsertAborProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Abor to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the Abor to update or insert the properties onto. Together with the scope this uniquely identifies the Abor. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the Abor. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;Abor/Manager/Id\&quot;. |

### Return type

[AborProperties](AborProperties.md)

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
<summary>Using the UpsertAborPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AborProperties> response = apiInstance.UpsertAborPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

