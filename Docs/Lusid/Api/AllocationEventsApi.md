# Finbourne.Sdk.Lusid.Api.AllocationEventsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BookAllocationEvent**](#bookallocationevent) | **POST** `/api/api/allocationevents/{scope}/{code}/book` | [EXPERIMENTAL] BookAllocationEvent: Book an Allocation Event. |
| [**CreateAllocationEvent**](#createallocationevent) | **POST** `/api/api/allocationevents/{scope}` | [EXPERIMENTAL] CreateAllocationEvent: Create an Allocation Event. |
| [**DeleteAllocationEvent**](#deleteallocationevent) | **DELETE** `/api/api/allocationevents/{scope}/{code}` | [EXPERIMENTAL] DeleteAllocationEvent: Delete an Allocation Event. |
| [**GetAllocationEvent**](#getallocationevent) | **GET** `/api/api/allocationevents/{scope}/{code}` | [EXPERIMENTAL] GetAllocationEvent: Get an Allocation Event. |
| [**GetAllocationEventNotices**](#getallocationeventnotices) | **GET** `/api/api/allocationevents/{scope}/{code}/notices` | [EARLY ACCESS] GetAllocationEventNotices: [EARLY ACCESS] GetAllocationEventNotices: Get the notices an allocation event issues to its partners. |
| [**GetAllocationEventReceivables**](#getallocationeventreceivables) | **GET** `/api/api/allocationevents/{scope}/{code}/receivables` | [EXPERIMENTAL] GetAllocationEventReceivables: Get the receivables of an Allocation Event. |
| [**ListAllocationEvents**](#listallocationevents) | **GET** `/api/api/allocationevents` | [EXPERIMENTAL] ListAllocationEvents: List Allocation Events. |
| [**ListAllocationPaymentHolds**](#listallocationpaymentholds) | **GET** `/api/api/allocationevents/{scope}/{code}/allocations/{investorRecordId}/holds` | [EARLY ACCESS] ListAllocationPaymentHolds: [EARLY ACCESS] ListAllocationPaymentHolds: List the holds placed on a partner&#39;s payment. |
| [**PlanAllocationEventBooking**](#planallocationeventbooking) | **POST** `/api/api/allocationevents/{scope}/{code}/plan` | [EXPERIMENTAL] PlanAllocationEventBooking: Plan the booking of an Allocation Event. |
| [**PutAllocationPaymentHold**](#putallocationpaymenthold) | **PUT** `/api/api/allocationevents/{scope}/{code}/allocations/{investorRecordId}/hold` | [EARLY ACCESS] PutAllocationPaymentHold: [EARLY ACCESS] PutAllocationPaymentHold: Place, move or release a hold on a partner&#39;s payment. |
| [**ReallocateAllocationEvent**](#reallocateallocationevent) | **POST** `/api/api/allocationevents/{scope}/{code}/reallocate` | [EXPERIMENTAL] ReallocateAllocationEvent: Reallocate an Allocation Event. |
| [**ReceiveAllocationEvent**](#receiveallocationevent) | **POST** `/api/api/allocationevents/{scope}/{code}/receipts` | [EXPERIMENTAL] ReceiveAllocationEvent: Record a receipt against an Allocation Event. |
| [**ReverseAllocationEvent**](#reverseallocationevent) | **POST** `/api/api/allocationevents/{scope}/{code}/reverse` | [EXPERIMENTAL] ReverseAllocationEvent: Reverse an Allocation Event. |
| [**UnbookAllocationEvent**](#unbookallocationevent) | **POST** `/api/api/allocationevents/{scope}/{code}/unbook` | [EXPERIMENTAL] UnbookAllocationEvent: Unbook an Allocation Event. |
| [**UpsertAllocationEvent**](#upsertallocationevent) | **PUT** `/api/api/allocationevents/{scope}/{code}` | [EXPERIMENTAL] UpsertAllocationEvent: Upsert an Allocation Event. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AllocationEventsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
```

---

<a id="bookallocationevent"></a>
## BookAllocationEvent

> AllocationEvent BookAllocationEvent(string scope, string code, AllocationEventBookRequest allocationEventBookRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] BookAllocationEvent: Book an Allocation Event.

Freeze a computed Allocation Event under a booking reference, from an effective datetime. Once booked the  event can no longer be replaced or reallocated. Booking again under the same reference returns the event  unchanged; booking under a different reference is refused.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventBookRequest = new AllocationEventBookRequest(); // AllocationEventBookRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationEvent result = apiInstance.BookAllocationEvent(scope, code, allocationEventBookRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventBookRequest** | [AllocationEventBookRequest](../Model/AllocationEventBookRequest.md) | body | **required** | The booking reference to freeze the event under. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to read the Allocation Event to book. The booking is recorded on the version in force at that time, from that version&#39;s own effective date. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The booked Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BookAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.BookAllocationEventWithHttpInfo(scope, code, allocationEventBookRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createallocationevent"></a>
## CreateAllocationEvent

> AllocationEvent CreateAllocationEvent(string scope, AllocationEventRequest allocationEventRequest)

[EXPERIMENTAL] CreateAllocationEvent: Create an Allocation Event.

Raise a new Allocation Event. The scope is provided in the route and the code in the request body. The event  names the Allocation Map it is shared by, the kind of event, the amount and the date. Its per-investor shares  are computed on creation from the map as it stood on the event date, so the response comes back Computed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var allocationEventRequest = new AllocationEventRequest(); // AllocationEventRequest
AllocationEvent result = apiInstance.CreateAllocationEvent(scope, allocationEventRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **allocationEventRequest** | [AllocationEventRequest](../Model/AllocationEventRequest.md) | body | **required** | The definition of the Allocation Event. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.CreateAllocationEventWithHttpInfo(scope, allocationEventRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteallocationevent"></a>
## DeleteAllocationEvent

> DeletedEntityResponse DeleteAllocationEvent(string scope, string code, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteAllocationEvent: Delete an Allocation Event.

Delete an Allocation Event. Given an effective datetime, the Allocation Event is deleted from that datetime  and remains retrievable at earlier effective datetimes. Given none, an Allocation Event that was created  without an effective datetime is removed from the beginning of time, so that its code can be reused;  this includes an event first created without an effective datetime and later upserted with dated versions,  whose dated versions are removed with it. Otherwise it is deleted from the current LUSID system datetime.  Only an Allocation Event that has not been booked can be deleted.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteAllocationEvent(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which to delete the Allocation Event. If not specified, an Allocation Event created without an effective datetime is removed from the beginning of time, dated versions upserted since included; any other is deleted from the current LUSID system datetime. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Allocation Event was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteAllocationEventWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallocationevent"></a>
## GetAllocationEvent

> AllocationEvent GetAllocationEvent(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAllocationEvent: Get an Allocation Event.

Retrieve a particular Allocation Event at an effective and asAt datetime, including its computed  per-investor shares and, once booked, its booking reference.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AllocationEvent result = apiInstance.GetAllocationEvent(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Allocation Event. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Allocation Event. Defaults to returning the latest version if not specified. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.GetAllocationEventWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallocationeventnotices"></a>
## GetAllocationEventNotices

> ResourceListOfAllocationEventNotice GetAllocationEventNotices(string scope, string code, string? investorRecordId = null, bool? includeZero = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetAllocationEventNotices: [EARLY ACCESS] GetAllocationEventNotices: Get the notices an allocation event issues to its partners.

One notice per partner allocation, listing the ILPA transaction lines, the net amount due, the partner's  unfunded commitment reconciliation across the event and their cumulative position alongside the general  partner's. Notices carry a DRAFT watermark until the event is booked.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var investorRecordId = "investorRecordId_example";  // string? (optional)
var includeZero = false;  // bool? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfAllocationEventNotice result = apiInstance.GetAllocationEventNotices(scope, code, investorRecordId, includeZero, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **investorRecordId** | **string?** | query | optional | Restrict the notices to this partner&#39;s investor record. |
| **includeZero** | **bool?** | query | optional | Whether to include notices whose every line is zero. Defaults to false. Default: `false` |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to read the event. Defaults to returning the latest version if not specified. |

### Return type

[ResourceListOfAllocationEventNotice](../Model/ResourceListOfAllocationEventNotice.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The notices the allocation event issues. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllocationEventNoticesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAllocationEventNotice> response = apiInstance.GetAllocationEventNoticesWithHttpInfo(scope, code, investorRecordId, includeZero, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallocationeventreceivables"></a>
## GetAllocationEventReceivables

> AllocationReceivablesAgeing GetAllocationEventReceivables(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAllocationEventReceivables: Get the receivables of an Allocation Event.

What each investor still owes on a booked capital call as of the effective datetime, with how many days past  due it is and the ageing bucket that puts it in.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AllocationReceivablesAgeing result = apiInstance.GetAllocationEventReceivables(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label as of which to age the receivables. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to read the Allocation Event. Defaults to returning the latest version if not specified. |

### Return type

[AllocationReceivablesAgeing](../Model/AllocationReceivablesAgeing.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The aged receivables of the Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllocationEventReceivablesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationReceivablesAgeing> response = apiInstance.GetAllocationEventReceivablesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listallocationevents"></a>
## ListAllocationEvents

> PagedResourceListOfAllocationEvent ListAllocationEvents(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListAllocationEvents: List Allocation Events.

List all the Allocation Events matching a particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfAllocationEvent result = apiInstance.ListAllocationEvents(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Allocation Events. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Allocation Events. Defaults to returning the latest version of each Allocation Event if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Allocation Events; this value is returned from the previous call.              If a pagination token is provided, the filter, effectiveAt and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the Allocation Event status, specify \&quot;status eq &#39;Booked&#39;\&quot;.              For more information about filtering LUSID results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfAllocationEvent](../Model/PagedResourceListOfAllocationEvent.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Allocation Events. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAllocationEventsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAllocationEvent> response = apiInstance.ListAllocationEventsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listallocationpaymentholds"></a>
## ListAllocationPaymentHolds

> ResourceListOfAllocationPaymentHold ListAllocationPaymentHolds(string scope, string code, string investorRecordId)

[EARLY ACCESS] ListAllocationPaymentHolds: [EARLY ACCESS] ListAllocationPaymentHolds: List the holds placed on a partner's payment.

Every hold placed on the partner's payment against the event, newest first, including released ones.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var investorRecordId = "investorRecordId_example";  // string
ResourceListOfAllocationPaymentHold result = apiInstance.ListAllocationPaymentHolds(scope, code, investorRecordId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **investorRecordId** | **string** | path | **required** | The investor record of the partner whose holds are listed. |

### Return type

[ResourceListOfAllocationPaymentHold](../Model/ResourceListOfAllocationPaymentHold.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The holds placed on the partner&#39;s payment. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAllocationPaymentHoldsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAllocationPaymentHold> response = apiInstance.ListAllocationPaymentHoldsWithHttpInfo(scope, code, investorRecordId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="planallocationeventbooking"></a>
## PlanAllocationEventBooking

> AllocationPostingPlan PlanAllocationEventBooking(string scope, string code, AllocationEventBookRequest allocationEventBookRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] PlanAllocationEventBooking: Plan the booking of an Allocation Event.

Show everything booking a computed Allocation Event under a booking reference would write, validated as the  booking itself would be, without writing any of it: the investors' lines, the roll-ups above them through the  fund structure and the fund-side transactions. A booking that would be refused fails here with every problem  listed; warnings the map's policy lets through come back on the plan.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventBookRequest = new AllocationEventBookRequest(); // AllocationEventBookRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationPostingPlan result = apiInstance.PlanAllocationEventBooking(scope, code, allocationEventBookRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventBookRequest** | [AllocationEventBookRequest](../Model/AllocationEventBookRequest.md) | body | **required** | The booking reference the plan is drawn up under. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to plan the booking. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationPostingPlan](../Model/AllocationPostingPlan.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The postings the booking would write. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PlanAllocationEventBookingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationPostingPlan> response = apiInstance.PlanAllocationEventBookingWithHttpInfo(scope, code, allocationEventBookRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="putallocationpaymenthold"></a>
## PutAllocationPaymentHold

> AllocationPaymentHold PutAllocationPaymentHold(string scope, string code, string investorRecordId, AllocationPaymentHoldRequest allocationPaymentHoldRequest)

[EARLY ACCESS] PutAllocationPaymentHold: [EARLY ACCESS] PutAllocationPaymentHold: Place, move or release a hold on a partner's payment.

A Blocked or Escrow hold stops the partner's allocation being received against the event until it is  Released. A hold may only be released by a user other than the one who placed it.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var investorRecordId = "investorRecordId_example";  // string
var allocationPaymentHoldRequest = new AllocationPaymentHoldRequest(); // AllocationPaymentHoldRequest
AllocationPaymentHold result = apiInstance.PutAllocationPaymentHold(scope, code, investorRecordId, allocationPaymentHoldRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **investorRecordId** | **string** | path | **required** | The investor record of the partner whose payment is held. |
| **allocationPaymentHoldRequest** | [AllocationPaymentHoldRequest](../Model/AllocationPaymentHoldRequest.md) | body | **required** | The hold to record: its status, and optionally a reason and an external reference. |

### Return type

[AllocationPaymentHold](../Model/AllocationPaymentHold.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The hold as recorded. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PutAllocationPaymentHoldWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationPaymentHold> response = apiInstance.PutAllocationPaymentHoldWithHttpInfo(scope, code, investorRecordId, allocationPaymentHoldRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reallocateallocationevent"></a>
## ReallocateAllocationEvent

> AllocationEvent ReallocateAllocationEvent(string scope, string code, AllocationEventReallocateRequest allocationEventReallocateRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] ReallocateAllocationEvent: Reallocate an Allocation Event.

Recompute the per-investor shares of an unbooked Allocation Event against its map, from an effective  datetime, recording the reason. Any basis values supplied replace those used before. A booked Allocation  Event cannot be reallocated.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventReallocateRequest = new AllocationEventReallocateRequest(); // AllocationEventReallocateRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationEvent result = apiInstance.ReallocateAllocationEvent(scope, code, allocationEventReallocateRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventReallocateRequest** | [AllocationEventReallocateRequest](../Model/AllocationEventReallocateRequest.md) | body | **required** | The reason for the reallocation and any basis values to use. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the reallocation applies. If not specified, the version in force now is recomputed in place from its own effective date. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The reallocated Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReallocateAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.ReallocateAllocationEventWithHttpInfo(scope, code, allocationEventReallocateRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="receiveallocationevent"></a>
## ReceiveAllocationEvent

> AllocationEvent ReceiveAllocationEvent(string scope, string code, AllocationEventReceiptRequest allocationEventReceiptRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] ReceiveAllocationEvent: Record a receipt against an Allocation Event.

Record cash received from an investor against a booked capital call. The receipt is applied to what the  investor owes on the call; anything over is recorded as a refund payable, so the outstanding amount never  goes negative. A bank charge is borne by the partner or the fund as the map's policy says, and a receipt in  another currency is converted at the rate given.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventReceiptRequest = new AllocationEventReceiptRequest(); // AllocationEventReceiptRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationEvent result = apiInstance.ReceiveAllocationEvent(scope, code, allocationEventReceiptRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventReceiptRequest** | [AllocationEventReceiptRequest](../Model/AllocationEventReceiptRequest.md) | body | **required** | The investor, amount and date of the receipt. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to read the Allocation Event receiving cash. The receipt is recorded on the version in force at that time, from that version&#39;s own effective date; the receipt postings are dated by the request. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Allocation Event with the receipt recorded. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReceiveAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.ReceiveAllocationEventWithHttpInfo(scope, code, allocationEventReceiptRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="reverseallocationevent"></a>
## ReverseAllocationEvent

> AllocationEvent ReverseAllocationEvent(string scope, string code, AllocationEventReverseRequest allocationEventReverseRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] ReverseAllocationEvent: Reverse an Allocation Event.

Reverse a booked Allocation Event: every posting the booking wrote is mirrored under the reversal reference and  the event is left Reversed. A reversal falling in a closed period posts in the current period unless it is  marked backdated. A reversal cannot itself be reversed; raise a new event naming the reversed one in its  replaces field to put corrected shares in the books.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventReverseRequest = new AllocationEventReverseRequest(); // AllocationEventReverseRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationEvent result = apiInstance.ReverseAllocationEvent(scope, code, allocationEventReverseRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventReverseRequest** | [AllocationEventReverseRequest](../Model/AllocationEventReverseRequest.md) | body | **required** | The reason for the reversal and, optionally, when it should take effect. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to read the Allocation Event to reverse. The reversed status is recorded on the version in force at that time, from that version&#39;s own effective date; the mirror postings are dated by the request. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The reversed Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ReverseAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.ReverseAllocationEventWithHttpInfo(scope, code, allocationEventReverseRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="unbookallocationevent"></a>
## UnbookAllocationEvent

> AllocationEvent UnbookAllocationEvent(string scope, string code, AllocationEventUnbookRequest allocationEventUnbookRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] UnbookAllocationEvent: Unbook an Allocation Event.

Take an Allocation Event whose booking stopped half way back to Computed, cancelling every posting the  booking wrote, and record why. Only an event in the Booking status can be unbooked: one that is Booked is  reversed instead.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventUnbookRequest = new AllocationEventUnbookRequest(); // AllocationEventUnbookRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
AllocationEvent result = apiInstance.UnbookAllocationEvent(scope, code, allocationEventUnbookRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventUnbookRequest** | [AllocationEventUnbookRequest](../Model/AllocationEventUnbookRequest.md) | body | **required** | The reason the booking is being taken back. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to read the Allocation Event to unbook. The unbooking is recorded on the version in force at that time, from that version&#39;s own effective date. Defaults to the current LUSID system datetime if not specified. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Allocation Event, back at Computed. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UnbookAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.UnbookAllocationEventWithHttpInfo(scope, code, allocationEventUnbookRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertallocationevent"></a>
## UpsertAllocationEvent

> AllocationEvent UpsertAllocationEvent(string scope, string code, AllocationEventRequest allocationEventRequest)

[EXPERIMENTAL] UpsertAllocationEvent: Upsert an Allocation Event.

Update or insert an Allocation Event. If the Allocation Event does not exist it is created, otherwise it is  replaced and its shares recomputed. The code in the request body must match the code in the route. A booked  Allocation Event is frozen and cannot be replaced.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AllocationEventsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var allocationEventRequest = new AllocationEventRequest(); // AllocationEventRequest
AllocationEvent result = apiInstance.UpsertAllocationEvent(scope, code, allocationEventRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Allocation Event. |
| **code** | **string** | path | **required** | The code of the Allocation Event. Together with the scope this uniquely identifies the Allocation Event. |
| **allocationEventRequest** | [AllocationEventRequest](../Model/AllocationEventRequest.md) | body | **required** | The definition of the Allocation Event. |

### Return type

[AllocationEvent](../Model/AllocationEvent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted Allocation Event. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertAllocationEventWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AllocationEvent> response = apiInstance.UpsertAllocationEventWithHttpInfo(scope, code, allocationEventRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

