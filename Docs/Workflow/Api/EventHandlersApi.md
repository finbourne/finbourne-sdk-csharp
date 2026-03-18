# Finbourne.Sdk.Workflow.Api.EventHandlersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateEventHandler**](#createeventhandler) | **POST** `/workflow/api/eventhandlers` | CreateEventHandler: Create a new Event Handler |
| [**DeleteEventHandler**](#deleteeventhandler) | **DELETE** `/workflow/api/eventhandlers/{scope}/{code}` | DeleteEventHandler: Delete an Event Handler |
| [**GetEventHandler**](#geteventhandler) | **GET** `/workflow/api/eventhandlers/{scope}/{code}` | GetEventHandler: Get an Event Handler |
| [**ListEventHandlers**](#listeventhandlers) | **GET** `/workflow/api/eventhandlers` | ListEventHandlers: List Event Handlers |
| [**UpdateEventHandler**](#updateeventhandler) | **PUT** `/workflow/api/eventhandlers/{scope}/{code}` | UpdateEventHandler: Update an existing Event handler |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Workflow.Api;
using Finbourne.Sdk.Workflow.Client;
using Finbourne.Sdk.Workflow.Extensions;
using Finbourne.Sdk.Services.Workflow.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<EventHandlersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventHandlersApi>();
```

---

<a id="createeventhandler"></a>
## CreateEventHandler

> EventHandler CreateEventHandler(CreateEventHandlerRequest createEventHandlerRequest)

CreateEventHandler: Create a new Event Handler

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventHandlersApi>();
var createEventHandlerRequest = new CreateEventHandlerRequest(); // CreateEventHandlerRequest
EventHandler result = apiInstance.CreateEventHandler(createEventHandlerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createEventHandlerRequest** | [CreateEventHandlerRequest](CreateEventHandlerRequest.md) | body | **required** | The data to create an Event Handler |

### Return type

[EventHandler](EventHandler.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateEventHandlerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EventHandler> response = apiInstance.CreateEventHandlerWithHttpInfo(createEventHandlerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteeventhandler"></a>
## DeleteEventHandler

> DeletedEntityResponse DeleteEventHandler(string scope, string code)

DeleteEventHandler: Delete an Event Handler

If the Event Handler does not exist a failure will be returned

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventHandlersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteEventHandler(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the event handler to be deleted |
| **code** | **string** | path | **required** | Code of the event handler to be deleted |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Event Handler not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteEventHandlerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteEventHandlerWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="geteventhandler"></a>
## GetEventHandler

> EventHandler GetEventHandler(string scope, string code, DateTimeOffset? asAt = null)

GetEventHandler: Get an Event Handler

Will return a NotFound failure if the event handler does not exist

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventHandlersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
EventHandler result = apiInstance.GetEventHandler(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the event handler |
| **code** | **string** | path | **required** | Code of the event handler |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the event handler. Defaults to returning the latest version of the event handler if not specified. |

### Return type

[EventHandler](EventHandler.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetEventHandlerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EventHandler> response = apiInstance.GetEventHandlerWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listeventhandlers"></a>
## ListEventHandlers

> PagedResourceListOfEventHandler ListEventHandlers(DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

ListEventHandlers: List Event Handlers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventHandlersApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 10;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfEventHandler result = apiInstance.ListEventHandlers(asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Event Handlers. Defaults to return the latest version of each Event Handler if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here: https://support.lusid.com/filtering-results-from-lusid. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Default: `10` |
| **page** | **string?** | query | optional | The pagination token to use to continue listing event handlers from a previous call to list event handlers. This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields must not have changed since the original request. |

### Return type

[PagedResourceListOfEventHandler](PagedResourceListOfEventHandler.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of Event Handlers |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListEventHandlersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfEventHandler> response = apiInstance.ListEventHandlersWithHttpInfo(asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateeventhandler"></a>
## UpdateEventHandler

> EventHandler UpdateEventHandler(string scope, string code, UpdateEventHandlerRequest updateEventHandlerRequest)

UpdateEventHandler: Update an existing Event handler

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventHandlersApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateEventHandlerRequest = new UpdateEventHandlerRequest(); // UpdateEventHandlerRequest
EventHandler result = apiInstance.UpdateEventHandler(scope, code, updateEventHandlerRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies an Event Handler |
| **code** | **string** | path | **required** | The code that identifies an Event Handler |
| **updateEventHandlerRequest** | [UpdateEventHandlerRequest](UpdateEventHandlerRequest.md) | body | **required** | The data to update an Event Handler |

### Return type

[EventHandler](EventHandler.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | Event Handler not found. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateEventHandlerWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EventHandler> response = apiInstance.UpdateEventHandlerWithHttpInfo(scope, code, updateEventHandlerRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

