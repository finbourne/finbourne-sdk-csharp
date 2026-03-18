# Finbourne.Sdk.Notifications.Api.SubscriptionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateSubscription**](#createsubscription) | **POST** `/notifications/api/subscriptions` | CreateSubscription: Create a new subscription. |
| [**DeleteSubscription**](#deletesubscription) | **DELETE** `/notifications/api/subscriptions/{scope}/{code}` | DeleteSubscription: Delete a subscription. |
| [**GetSubscription**](#getsubscription) | **GET** `/notifications/api/subscriptions/{scope}/{code}` | GetSubscription: Get a subscription. |
| [**ListSubscriptions**](#listsubscriptions) | **GET** `/notifications/api/subscriptions` | ListSubscriptions: List subscriptions. |
| [**UpdateSubscription**](#updatesubscription) | **PUT** `/notifications/api/subscriptions/{scope}/{code}` | UpdateSubscription: Update an existing subscription. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SubscriptionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
```

---

<a id="createsubscription"></a>
## CreateSubscription

> Subscription CreateSubscription(CreateSubscription createSubscription)

CreateSubscription: Create a new subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var createSubscription = new CreateSubscription(); // CreateSubscription
Subscription result = apiInstance.CreateSubscription(createSubscription);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createSubscription** | [CreateSubscription](CreateSubscription.md) | body | **required** | The data to create a subscription |

### Return type

[Subscription](Subscription.md)

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
<summary>Using the CreateSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Subscription> response = apiInstance.CreateSubscriptionWithHttpInfo(createSubscription);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletesubscription"></a>
## DeleteSubscription

> void DeleteSubscription(string scope, string code)

DeleteSubscription: Delete a subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
apiInstance.DeleteSubscription(scope, code);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |

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
| **404** | No subscription exists in current scope |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteSubscriptionWithHttpInfo(scope, code);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsubscription"></a>
## GetSubscription

> Subscription GetSubscription(string scope, string code)

GetSubscription: Get a subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
Subscription result = apiInstance.GetSubscription(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |

### Return type

[Subscription](Subscription.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No subscription exists in current scope |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Subscription> response = apiInstance.GetSubscriptionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listsubscriptions"></a>
## ListSubscriptions

> ResourceListOfSubscription ListSubscriptions(string? filter = null, string? sortBy = null, string? page = null, int? limit = null)

ListSubscriptions: List subscriptions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var filter = "filter_example";  // string? (optional)
var sortBy = "sortBy_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfSubscription result = apiInstance.ListSubscriptions(filter, sortBy, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about &lt;a href&#x3D;\&quot;https://support.lusid.com/filtering-results-from-lusid\&quot;&gt; filtering results from LUSID&lt;/a&gt;. |
| **sortBy** | **string?** | query | optional | Fields to order the result set. Read more about &lt;a href&#x3D;\&quot;https://support.lusid.com/filtering-results-from-lusid\&quot;&gt; filtering results from LUSID&lt;/a&gt; |
| **page** | **string?** | query | optional | Encoded page string returned from a previous search result that will retrieve the next page of data. When this field is supplied the filter  field should not be supplied. |
| **limit** | **int?** | query | optional | The maximum number of subscriptions to retrieve. |

### Return type

[ResourceListOfSubscription](ResourceListOfSubscription.md)

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
<summary>Using the ListSubscriptionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfSubscription> response = apiInstance.ListSubscriptionsWithHttpInfo(filter, sortBy, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatesubscription"></a>
## UpdateSubscription

> Subscription UpdateSubscription(string scope, string code, UpdateSubscription updateSubscription)

UpdateSubscription: Update an existing subscription.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateSubscription = new UpdateSubscription(); // UpdateSubscription
Subscription result = apiInstance.UpdateSubscription(scope, code, updateSubscription);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that identifies a subscription |
| **code** | **string** | path | **required** | The code that identifies a subscription |
| **updateSubscription** | [UpdateSubscription](UpdateSubscription.md) | body | **required** | The data to update a subscription |

### Return type

[Subscription](Subscription.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | No subscription exists in current scope |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Subscription> response = apiInstance.UpdateSubscriptionWithHttpInfo(scope, code, updateSubscription);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

