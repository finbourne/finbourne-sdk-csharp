# Finbourne.Sdk.Notifications.Api.NotificationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateNotification**](#createnotification) | **POST** `/notifications/api/subscriptions/{scope}/{code}/notifications` | CreateNotification: Add a Notification to a Subscription. |
| [**DeleteNotification**](#deletenotification) | **DELETE** `/notifications/api/subscriptions/{scope}/{code}/notifications/{id}` | DeleteNotification: Delete a notification for a given subscription. |
| [**GetNotification**](#getnotification) | **GET** `/notifications/api/subscriptions/{scope}/{code}/notifications/{id}` | GetNotification: Get a notification on a subscription. |
| [**ListNotifications**](#listnotifications) | **GET** `/notifications/api/subscriptions/{scope}/{code}/notifications` | ListNotifications: List all notifications on a subscription. |
| [**UpdateNotification**](#updatenotification) | **PUT** `/notifications/api/subscriptions/{scope}/{code}/notifications/{id}` | UpdateNotification: Update a Notification for a Subscription |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<NotificationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NotificationsApi>();
```

---

<a id="createnotification"></a>
## CreateNotification

> Notification CreateNotification(string scope, string code, CreateNotificationRequest createNotificationRequest)

CreateNotification: Add a Notification to a Subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NotificationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createNotificationRequest = new CreateNotificationRequest(); // CreateNotificationRequest
Notification result = apiInstance.CreateNotification(scope, code, createNotificationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |
| **createNotificationRequest** | [CreateNotificationRequest](CreateNotificationRequest.md) | body | **required** | The data to create a notification |

### Return type

[Notification](Notification.md)

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
<summary>Using the CreateNotificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Notification> response = apiInstance.CreateNotificationWithHttpInfo(scope, code, createNotificationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletenotification"></a>
## DeleteNotification

> void DeleteNotification(string scope, string code, string id)

DeleteNotification: Delete a notification for a given subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NotificationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var id = "id_example";  // string
apiInstance.DeleteNotification(scope, code, id);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |
| **id** | **string** | path | **required** | The unique identifier of the notification |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No notification exists in current scope |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteNotificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteNotificationWithHttpInfo(scope, code, id);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getnotification"></a>
## GetNotification

> Notification GetNotification(string scope, string code, string id)

GetNotification: Get a notification on a subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NotificationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var id = "id_example";  // string
Notification result = apiInstance.GetNotification(scope, code, id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |
| **id** | **string** | path | **required** | The unique identifier of the notification |

### Return type

[Notification](Notification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No notification exists in current scope |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetNotificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Notification> response = apiInstance.GetNotificationWithHttpInfo(scope, code, id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listnotifications"></a>
## ListNotifications

> ResourceListOfNotification ListNotifications(string scope, string code)

ListNotifications: List all notifications on a subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NotificationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
ResourceListOfNotification result = apiInstance.ListNotifications(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |

### Return type

[ResourceListOfNotification](ResourceListOfNotification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No notifications exists with the provided filter(s) |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListNotificationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfNotification> response = apiInstance.ListNotificationsWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatenotification"></a>
## UpdateNotification

> Notification UpdateNotification(string scope, string code, string id, UpdateNotificationRequest updateNotificationRequest)

UpdateNotification: Update a Notification for a Subscription

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NotificationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var id = "id_example";  // string
var updateNotificationRequest = new UpdateNotificationRequest(); // UpdateNotificationRequest
Notification result = apiInstance.UpdateNotification(scope, code, id, updateNotificationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |
| **id** | **string** | path | **required** | The unique identifier of the notification |
| **updateNotificationRequest** | [UpdateNotificationRequest](UpdateNotificationRequest.md) | body | **required** | The data to update a notification |

### Return type

[Notification](Notification.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No notification exists in current scope |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateNotificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Notification> response = apiInstance.UpdateNotificationWithHttpInfo(scope, code, id, updateNotificationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

