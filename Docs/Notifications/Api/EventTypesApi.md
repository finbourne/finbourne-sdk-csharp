# Finbourne.Sdk.Notifications.Api.EventTypesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetEventType**](#geteventtype) | **GET** `/notifications/api/eventtypes/{eventType}` | GetEventType: Gets the specified event type schema. |
| [**ListEventTypes**](#listeventtypes) | **GET** `/notifications/api/eventtypes` | ListEventTypes: Lists all of the available event types. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Notifications.Api;
using Finbourne.Sdk.Notifications.Client;
using Finbourne.Sdk.Notifications.Extensions;
using Finbourne.Sdk.Services.Notifications.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<EventTypesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventTypesApi>();
```

---

<a id="geteventtype"></a>
## GetEventType

> EventTypeSchema GetEventType(string eventType)

GetEventType: Gets the specified event type schema.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventTypesApi>();
var eventType = "eventType_example";  // string
EventTypeSchema result = apiInstance.GetEventType(eventType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **eventType** | **string** | path | **required** | The event type to retrieve schema for. |

### Return type

[EventTypeSchema](EventTypeSchema.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No event type exists with the specified type |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetEventTypeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EventTypeSchema> response = apiInstance.GetEventTypeWithHttpInfo(eventType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listeventtypes"></a>
## ListEventTypes

> ResourceListOfEventTypeSchema ListEventTypes()

ListEventTypes: Lists all of the available event types.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EventTypesApi>();
ResourceListOfEventTypeSchema result = apiInstance.ListEventTypes();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfEventTypeSchema](ResourceListOfEventTypeSchema.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **404** | No event types found |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListEventTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfEventTypeSchema> response = apiInstance.ListEventTypesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

