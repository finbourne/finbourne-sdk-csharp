# Finbourne.Sdk.Lusid.Api.EligibleCollateralSchedulesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateEligibleCollateralSchedule**](#createeligiblecollateralschedule) | **POST** `/api/api/eligiblecollateralschedules/{scope}` | [EXPERIMENTAL] CreateEligibleCollateralSchedule: Create an Eligible Collateral Schedule. |
| [**DeleteEligibleCollateralSchedule**](#deleteeligiblecollateralschedule) | **DELETE** `/api/api/eligiblecollateralschedules/{scope}/{code}` | [EXPERIMENTAL] DeleteEligibleCollateralSchedule: Delete an Eligible Collateral Schedule. |
| [**GetEligibleCollateralSchedule**](#geteligiblecollateralschedule) | **GET** `/api/api/eligiblecollateralschedules/{scope}/{code}` | [EXPERIMENTAL] GetEligibleCollateralSchedule: Get an Eligible Collateral Schedule. |
| [**ListEligibleCollateralSchedules**](#listeligiblecollateralschedules) | **GET** `/api/api/eligiblecollateralschedules` | [EXPERIMENTAL] ListEligibleCollateralSchedules: List Eligible Collateral Schedules. |
| [**UpsertEligibleCollateralSchedule**](#upserteligiblecollateralschedule) | **PUT** `/api/api/eligiblecollateralschedules/{scope}/{code}` | [EXPERIMENTAL] UpsertEligibleCollateralSchedule: Upsert an Eligible Collateral Schedule. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<EligibleCollateralSchedulesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EligibleCollateralSchedulesApi>();
```

---

<a id="createeligiblecollateralschedule"></a>
## CreateEligibleCollateralSchedule

> EligibleCollateralSchedule CreateEligibleCollateralSchedule(string scope, EligibleCollateralScheduleRequest eligibleCollateralScheduleRequest)

[EXPERIMENTAL] CreateEligibleCollateralSchedule: Create an Eligible Collateral Schedule.

Create a new Eligible Collateral Schedule. The scope of the schedule is in the route and its code is in the request body.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EligibleCollateralSchedulesApi>();
var scope = "scope_example";  // string
var eligibleCollateralScheduleRequest = new EligibleCollateralScheduleRequest(); // EligibleCollateralScheduleRequest
EligibleCollateralSchedule result = apiInstance.CreateEligibleCollateralSchedule(scope, eligibleCollateralScheduleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Eligible Collateral Schedule. |
| **eligibleCollateralScheduleRequest** | [EligibleCollateralScheduleRequest](../Model/EligibleCollateralScheduleRequest.md) | body | **required** | The definition of the Eligible Collateral Schedule. |

### Return type

[EligibleCollateralSchedule](../Model/EligibleCollateralSchedule.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Eligible Collateral Schedule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateEligibleCollateralScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EligibleCollateralSchedule> response = apiInstance.CreateEligibleCollateralScheduleWithHttpInfo(scope, eligibleCollateralScheduleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteeligiblecollateralschedule"></a>
## DeleteEligibleCollateralSchedule

> DeletedEntityResponse DeleteEligibleCollateralSchedule(string scope, string code, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteEligibleCollateralSchedule: Delete an Eligible Collateral Schedule.

Delete an Eligible Collateral Schedule from the given effective datetime. It remains retrievable at earlier effective datetimes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EligibleCollateralSchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteEligibleCollateralSchedule(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Eligible Collateral Schedule to be deleted. |
| **code** | **string** | path | **required** | The code of the Eligible Collateral Schedule to be deleted. Together with the scope this uniquely identifies the Eligible Collateral Schedule. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the Eligible Collateral Schedule is deleted. Defaults to the current LUSID system datetime if not specified. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Eligible Collateral Schedule was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteEligibleCollateralScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteEligibleCollateralScheduleWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="geteligiblecollateralschedule"></a>
## GetEligibleCollateralSchedule

> EligibleCollateralSchedule GetEligibleCollateralSchedule(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetEligibleCollateralSchedule: Get an Eligible Collateral Schedule.

Retrieve the definition of a particular Eligible Collateral Schedule at an effective and asAt datetime.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EligibleCollateralSchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
EligibleCollateralSchedule result = apiInstance.GetEligibleCollateralSchedule(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Eligible Collateral Schedule. |
| **code** | **string** | path | **required** | The code of the Eligible Collateral Schedule. Together with the scope this uniquely identifies the Eligible Collateral Schedule. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Eligible Collateral Schedule. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Eligible Collateral Schedule. Defaults to returning the latest version if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the &#39;EligibleCollateralSchedule&#39; domain to decorate onto the Eligible Collateral Schedule.              These must take the format {domain}/{scope}/{code}, for example &#39;EligibleCollateralSchedule/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[EligibleCollateralSchedule](../Model/EligibleCollateralSchedule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Eligible Collateral Schedule. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetEligibleCollateralScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EligibleCollateralSchedule> response = apiInstance.GetEligibleCollateralScheduleWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listeligiblecollateralschedules"></a>
## ListEligibleCollateralSchedules

> PagedResourceListOfEligibleCollateralSchedule ListEligibleCollateralSchedules(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListEligibleCollateralSchedules: List Eligible Collateral Schedules.

List all the Eligible Collateral Schedules matching the given criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EligibleCollateralSchedulesApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfEligibleCollateralSchedule result = apiInstance.ListEligibleCollateralSchedules(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Eligible Collateral Schedules. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list Eligible Collateral Schedules. Defaults to returning the latest version of each Eligible Collateral Schedule if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Eligible Collateral Schedules; this value is returned from the previous call. If a pagination token is provided, the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are Id.Scope, Id.Code, Description, Properties and Version. The rows can be filtered with a single-condition any expression on Rows over Code, Description, Selector.Kind, Selector.Currency, Selector.InstrumentFilter, ValuationPercentage, FxHaircut, MinResidualMaturityYears or MaxResidualMaturityYears. For example, to filter on the schedule code, specify \&quot;Id.Code eq &#39;UsdCashAndGovies&#39;\&quot;, and to find schedules with a row for a given asset kind, specify \&quot;Rows any (Selector.Kind eq &#39;Cash&#39;)\&quot;. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the &#39;EligibleCollateralSchedule&#39; domain to decorate onto each Eligible Collateral Schedule.              These must take the format {domain}/{scope}/{code}, for example &#39;EligibleCollateralSchedule/Manager/Id&#39;. |

### Return type

[PagedResourceListOfEligibleCollateralSchedule](../Model/PagedResourceListOfEligibleCollateralSchedule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Eligible Collateral Schedules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListEligibleCollateralSchedulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfEligibleCollateralSchedule> response = apiInstance.ListEligibleCollateralSchedulesWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserteligiblecollateralschedule"></a>
## UpsertEligibleCollateralSchedule

> EligibleCollateralSchedule UpsertEligibleCollateralSchedule(string scope, string code, UpsertEligibleCollateralScheduleRequest upsertEligibleCollateralScheduleRequest)

[EXPERIMENTAL] UpsertEligibleCollateralSchedule: Upsert an Eligible Collateral Schedule.

Create or replace the full definition of an Eligible Collateral Schedule from an effective datetime. A change to the  definition becomes a new bitemporal version: the schedule as it was declared at earlier effective datetimes,  and as of earlier asAt datetimes, remains retrievable.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EligibleCollateralSchedulesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertEligibleCollateralScheduleRequest = new UpsertEligibleCollateralScheduleRequest(); // UpsertEligibleCollateralScheduleRequest
EligibleCollateralSchedule result = apiInstance.UpsertEligibleCollateralSchedule(scope, code, upsertEligibleCollateralScheduleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Eligible Collateral Schedule. |
| **code** | **string** | path | **required** | The code of the Eligible Collateral Schedule. Together with the scope this uniquely identifies the Eligible Collateral Schedule. |
| **upsertEligibleCollateralScheduleRequest** | [UpsertEligibleCollateralScheduleRequest](../Model/UpsertEligibleCollateralScheduleRequest.md) | body | **required** | The full definition of the Eligible Collateral Schedule from the effective datetime in the request, or the current LUSID system datetime if not specified. |

### Return type

[EligibleCollateralSchedule](../Model/EligibleCollateralSchedule.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Eligible Collateral Schedule as it stands from the effective datetime. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertEligibleCollateralScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EligibleCollateralSchedule> response = apiInstance.UpsertEligibleCollateralScheduleWithHttpInfo(scope, code, upsertEligibleCollateralScheduleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

