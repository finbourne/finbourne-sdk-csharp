# Finbourne.Sdk.Lusid.Api.CalendarsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddBusinessDaysToDate**](#addbusinessdaystodate) | **POST** `/api/api/calendars/businessday/{scope}/add` | [EARLY ACCESS] AddBusinessDaysToDate: Adds the requested number of Business Days to the provided date. |
| [**AddDateToCalendar**](#adddatetocalendar) | **PUT** `/api/api/calendars/generic/{scope}/{code}/dates` | AddDateToCalendar: Add a date to a calendar |
| [**BatchUpsertDatesForCalendar**](#batchupsertdatesforcalendar) | **POST** `/api/api/calendars/generic/{scope}/{code}/dates/$batchUpsert` | BatchUpsertDatesForCalendar: Batch upsert dates to a calendar |
| [**CreateCalendar**](#createcalendar) | **POST** `/api/api/calendars/generic` | [EARLY ACCESS] CreateCalendar: Create a calendar in its generic form |
| [**DeleteCalendar**](#deletecalendar) | **DELETE** `/api/api/calendars/generic/{scope}/{code}` | [EARLY ACCESS] DeleteCalendar: Delete a calendar |
| [**DeleteDateFromCalendar**](#deletedatefromcalendar) | **DELETE** `/api/api/calendars/generic/{scope}/{code}/dates/{dateId}` | DeleteDateFromCalendar: Remove a date from a calendar |
| [**DeleteDatesFromCalendar**](#deletedatesfromcalendar) | **POST** `/api/api/calendars/generic/{scope}/{code}/dates/$delete` | DeleteDatesFromCalendar: Delete dates from a calendar |
| [**GenerateSchedule**](#generateschedule) | **POST** `/api/api/calendars/schedule/{scope}` | [EARLY ACCESS] GenerateSchedule: Generate an ordered schedule of dates. |
| [**GetCalendar**](#getcalendar) | **GET** `/api/api/calendars/generic/{scope}/{code}` | GetCalendar: Get a calendar in its generic form |
| [**GetDates**](#getdates) | **GET** `/api/api/calendars/generic/{scope}/{code}/dates` | [EARLY ACCESS] GetDates: Get dates for a specific calendar |
| [**IsBusinessDateTime**](#isbusinessdatetime) | **GET** `/api/api/calendars/businessday/{scope}/{code}` | [EARLY ACCESS] IsBusinessDateTime: Check whether a DateTime is a \&quot;Business DateTime\&quot; |
| [**ListCalendars**](#listcalendars) | **GET** `/api/api/calendars/generic` | [EARLY ACCESS] ListCalendars: List Calendars |
| [**ListCalendarsInScope**](#listcalendarsinscope) | **GET** `/api/api/calendars/generic/{scope}` | ListCalendarsInScope: List all calenders in a specified scope |
| [**UpdateCalendar**](#updatecalendar) | **POST** `/api/api/calendars/generic/{scope}/{code}` | [EARLY ACCESS] UpdateCalendar: Update a calendar |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CalendarsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
```

---

<a id="addbusinessdaystodate"></a>
## AddBusinessDaysToDate

> AddBusinessDaysToDateResponse AddBusinessDaysToDate(string scope, AddBusinessDaysToDateRequest addBusinessDaysToDateRequest)

[EARLY ACCESS] AddBusinessDaysToDate: Adds the requested number of Business Days to the provided date.

A Business day is defined as a point in time that:      * Does not represent a day in the calendar's weekend      * Does not represent a day in the calendar's list of holidays (e.g. Christmas Day in the UK)                 All dates specified must be UTC and the upper bound of a calendar is not inclusive                 e.g. From: 2020-12-24-00-00-00:       Adding 3 business days returns 2020-12-30, assuming Saturday and Sunday are weekends, and the 25th and 28th are holidays.       Adding -2 business days returns 2020-12-22 under the same assumptions.                If the provided number of days to add is zero, returns a failure.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var addBusinessDaysToDateRequest = new AddBusinessDaysToDateRequest(); // AddBusinessDaysToDateRequest
AddBusinessDaysToDateResponse result = apiInstance.AddBusinessDaysToDate(scope, addBusinessDaysToDateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope within which to search for the calendars |
| **addBusinessDaysToDateRequest** | [AddBusinessDaysToDateRequest](AddBusinessDaysToDateRequest.md) | body | **required** | Request Details: start date, number of days to add (which can be negative, but not zero), calendar codes and optionally an AsAt date for searching the calendar store |

### Return type

[AddBusinessDaysToDateResponse](AddBusinessDaysToDateResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The business day that is a number of business days after the given date as determined by the given calendar codes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddBusinessDaysToDateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AddBusinessDaysToDateResponse> response = apiInstance.AddBusinessDaysToDateWithHttpInfo(scope, addBusinessDaysToDateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="adddatetocalendar"></a>
## AddDateToCalendar

> CalendarDate AddDateToCalendar(string scope, string code, CreateDateRequest createDateRequest)

AddDateToCalendar: Add a date to a calendar

Add an event to the calendar. These Events can be a maximum of 24 hours and must be specified in UTC.  A local date will be calculated by the system and applied to the calendar before processing.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createDateRequest = new CreateDateRequest(); // CreateDateRequest
CalendarDate result = apiInstance.AddDateToCalendar(scope, code, createDateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |
| **createDateRequest** | [CreateDateRequest](CreateDateRequest.md) | body | **required** | Add date to calendar request |

### Return type

[CalendarDate](CalendarDate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created date |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddDateToCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CalendarDate> response = apiInstance.AddDateToCalendarWithHttpInfo(scope, code, createDateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchupsertdatesforcalendar"></a>
## BatchUpsertDatesForCalendar

> BatchUpsertDatesForCalendarResponse BatchUpsertDatesForCalendar(string scope, string code, string successMode, Dictionary<string, CreateDateRequest> requestBody)

BatchUpsertDatesForCalendar: Batch upsert dates to a calendar

Create or update events in the calendar. These Events can be a maximum of 24 hours and must be specified in UTC.  A local date will be calculated by the system and applied to the calendar before processing.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var successMode = "\"Partial\"";  // string
var requestBody = new Dictionary<string, CreateDateRequest>(); // Dictionary<string, CreateDateRequest>
BatchUpsertDatesForCalendarResponse result = apiInstance.BatchUpsertDatesForCalendar(scope, code, successMode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial. Default: `&quot;Partial&quot;` |
| **requestBody** | [Dictionary&lt;string, CreateDateRequest&gt;](CreateDateRequest.md) | body | **required** | Create Date Requests of dates to upsert |

### Return type

[BatchUpsertDatesForCalendarResponse](BatchUpsertDatesForCalendarResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully upserted date requests along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertDatesForCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertDatesForCalendarResponse> response = apiInstance.BatchUpsertDatesForCalendarWithHttpInfo(scope, code, successMode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createcalendar"></a>
## CreateCalendar

> Calendar CreateCalendar(CreateCalendarRequest createCalendarRequest)

[EARLY ACCESS] CreateCalendar: Create a calendar in its generic form

Create a calendar in a generic form which can be used to store date events.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var createCalendarRequest = new CreateCalendarRequest(); // CreateCalendarRequest
Calendar result = apiInstance.CreateCalendar(createCalendarRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createCalendarRequest** | [CreateCalendarRequest](CreateCalendarRequest.md) | body | **required** | A request to create the calendar |

### Return type

[Calendar](Calendar.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created calendar |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Calendar> response = apiInstance.CreateCalendarWithHttpInfo(createCalendarRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecalendar"></a>
## DeleteCalendar

> Calendar DeleteCalendar(string scope, string code)

[EARLY ACCESS] DeleteCalendar: Delete a calendar

Delete a calendar and all of its respective dates

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
Calendar result = apiInstance.DeleteCalendar(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |

### Return type

[Calendar](Calendar.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted calendar |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Calendar> response = apiInstance.DeleteCalendarWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletedatefromcalendar"></a>
## DeleteDateFromCalendar

> CalendarDate DeleteDateFromCalendar(string scope, string code, string dateId)

DeleteDateFromCalendar: Remove a date from a calendar

Remove a date from a calendar.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var dateId = "dateId_example";  // string
CalendarDate result = apiInstance.DeleteDateFromCalendar(scope, code, dateId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |
| **dateId** | **string** | path | **required** | Identifier of the date to be removed |

### Return type

[CalendarDate](CalendarDate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted date |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteDateFromCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CalendarDate> response = apiInstance.DeleteDateFromCalendarWithHttpInfo(scope, code, dateId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletedatesfromcalendar"></a>
## DeleteDatesFromCalendar

> Dictionary&lt;string, CalendarDate&gt; DeleteDatesFromCalendar(string scope, string code, List<string> requestBody)

DeleteDatesFromCalendar: Delete dates from a calendar

Delete dates from a calendar.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new List<string>(); // List<string>
Dictionary<string, CalendarDate> result = apiInstance.DeleteDatesFromCalendar(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | Identifiers of the dates to be removed |

### Return type

[Dictionary&lt;string, CalendarDate&gt;](CalendarDate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The dateIds and details of the dates that were deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteDatesFromCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, CalendarDate>> response = apiInstance.DeleteDatesFromCalendarWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="generateschedule"></a>
## GenerateSchedule

> List&lt;DateTimeOffset&gt; GenerateSchedule(string scope, ValuationSchedule valuationSchedule, DateTimeOffset? asAt = null)

[EARLY ACCESS] GenerateSchedule: Generate an ordered schedule of dates.

Returns an ordered array of dates. The dates will only fall on business  days as defined by the scope and calendar codes in the valuation schedule.                Valuations are made at a frequency defined by the valuation schedule's tenor, e.g. every day (\"1D\"),  every other week (\"2W\") etc. These dates will be adjusted onto business days as defined by the schedule's  rollConvention.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var valuationSchedule = new ValuationSchedule(); // ValuationSchedule
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<DateTimeOffset> result = apiInstance.GenerateSchedule(scope, valuationSchedule, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendars to use |
| **valuationSchedule** | [ValuationSchedule](ValuationSchedule.md) | body | **required** | The ValuationSchedule to generate schedule dates from |
| **asAt** | **DateTimeOffset?** | query | optional | Optional AsAt for searching the calendar store. Defaults to Latest. |

### Return type

**List<DateTimeOffset>**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | An array of dates in chronological order. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GenerateScheduleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<DateTimeOffset>> response = apiInstance.GenerateScheduleWithHttpInfo(scope, valuationSchedule, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcalendar"></a>
## GetCalendar

> Calendar GetCalendar(string scope, string code, List<string>? propertyKeys = null, DateTimeOffset? asAt = null)

GetCalendar: Get a calendar in its generic form

Retrieve a generic calendar by a specific ID at a point in AsAt time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>?(); // List<string>? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Calendar result = apiInstance.GetCalendar(scope, code, propertyKeys, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar identifier |
| **code** | **string** | path | **required** | Code of the calendar identifier |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Calendar\&quot; domain to decorate onto the calendar,               These take the format {domain}/{scope}/{code} e.g. \&quot;Calendar/System/Name\&quot;. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the calendar |

### Return type

[Calendar](Calendar.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested calendar |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Calendar> response = apiInstance.GetCalendarWithHttpInfo(scope, code, propertyKeys, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdates"></a>
## GetDates

> ResourceListOfCalendarDate GetDates(string scope, string code, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, DateTimeOffset? asAt = null, List<string>? idFilter = null)

[EARLY ACCESS] GetDates: Get dates for a specific calendar

Get dates from a specific calendar within a specific window of effective time, at a point in AsAt time.  Providing an id filter can further refine the results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var idFilter = new List<string>?(); // List<string>? (optional)
ResourceListOfCalendarDate result = apiInstance.GetDates(scope, code, fromEffectiveAt, toEffectiveAt, asAt, idFilter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | Where the effective window of dates should begin from |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | Where the effective window of dates should end |
| **asAt** | **DateTimeOffset?** | query | optional | AsAt the dates should be retrieved at |
| **idFilter** | [List&lt;string&gt;?](string.md) | query | optional | An additional filter that will filter dates based on their identifer |

### Return type

[ResourceListOfCalendarDate](ResourceListOfCalendarDate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested date |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfCalendarDate> response = apiInstance.GetDatesWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt, idFilter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="isbusinessdatetime"></a>
## IsBusinessDateTime

> IsBusinessDayResponse IsBusinessDateTime(DateTimeOffset dateTime, string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] IsBusinessDateTime: Check whether a DateTime is a \"Business DateTime\"

A Business DateTime is defined as a point in time that:      * Does not represent a day that overlaps with the calendars WeekendMask      * If the calendar is a \"Holiday Calendar\" Does not overlap with any dates in the calendar      * If the calendar is a \"TradingHours Calendar\" Does overlap with a date in the calendar                All dates specified must be UTC and the upper bound of a calendar is not inclusive   e.g. From: 2020-12-25-00-00-00        To: 2020-12-26-00-00-00  IsBusinessDay(2020-12-26-00-00-00) == false

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var dateTime = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
IsBusinessDayResponse result = apiInstance.IsBusinessDateTime(dateTime, scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **dateTime** | **DateTimeOffset** | query | **required** | DateTime to check - This DateTime must be UTC |
| **scope** | **string** | path | **required** | Scope of the calendar |
| **code** | **string** | path | **required** | Code of the calendar |
| **asAt** | **DateTimeOffset?** | query | optional | AsAt for the request |

### Return type

[IsBusinessDayResponse](IsBusinessDayResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Whether or not the requested DateTime is a BusinessDay or not |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the IsBusinessDateTimeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IsBusinessDayResponse> response = apiInstance.IsBusinessDateTimeWithHttpInfo(dateTime, scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcalendars"></a>
## ListCalendars

> PagedResourceListOfCalendar ListCalendars(DateTimeOffset? asAt = null, string? page = null, int? limit = null, List<string>? propertyKeys = null, string? filter = null)

[EARLY ACCESS] ListCalendars: List Calendars

List calendars at a point in AsAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfCalendar result = apiInstance.ListCalendars(asAt, page, limit, propertyKeys, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the calendars |
| **page** | **string?** | query | optional | The pagination token to use to continue listing calendars from a previous call to list calendars.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Calendar\&quot; domain to decorate onto the calendar,               These take the format {domain}/{scope}/{code} e.g. \&quot;Calendar/System/Name\&quot;. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfCalendar](PagedResourceListOfCalendar.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Calendars |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCalendarsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCalendar> response = apiInstance.ListCalendarsWithHttpInfo(asAt, page, limit, propertyKeys, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcalendarsinscope"></a>
## ListCalendarsInScope

> PagedResourceListOfCalendar ListCalendarsInScope(string scope, DateTimeOffset? asAt = null, string? page = null, int? limit = null, List<string>? propertyKeys = null, string? filter = null)

ListCalendarsInScope: List all calenders in a specified scope

List calendars in a Scope at a point in AsAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfCalendar result = apiInstance.ListCalendarsInScope(scope, asAt, page, limit, propertyKeys, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the calendars |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the calendars |
| **page** | **string?** | query | optional | The pagination token to use to continue listing calendars from a previous call to list calendars.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Calendar\&quot; domain to decorate onto the calendar,               These take the format {domain}/{scope}/{code} e.g. \&quot;Calendar/System/Name\&quot;. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfCalendar](PagedResourceListOfCalendar.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Calendars in the requested scope |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCalendarsInScopeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCalendar> response = apiInstance.ListCalendarsInScopeWithHttpInfo(scope, asAt, page, limit, propertyKeys, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecalendar"></a>
## UpdateCalendar

> Calendar UpdateCalendar(string scope, string code, UpdateCalendarRequest updateCalendarRequest)

[EARLY ACCESS] UpdateCalendar: Update a calendar

Update the calendars WeekendMask, SourceProvider or Properties

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CalendarsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateCalendarRequest = new UpdateCalendarRequest(); // UpdateCalendarRequest
Calendar result = apiInstance.UpdateCalendar(scope, code, updateCalendarRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the request |
| **code** | **string** | path | **required** | Code of the request |
| **updateCalendarRequest** | [UpdateCalendarRequest](UpdateCalendarRequest.md) | body | **required** | The new state of the calendar |

### Return type

[Calendar](Calendar.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated calendar |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateCalendarWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Calendar> response = apiInstance.UpdateCalendarWithHttpInfo(scope, code, updateCalendarRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

