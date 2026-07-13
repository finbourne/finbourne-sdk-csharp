# Finbourne.Sdk.Lusid.Api.SubscriptionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteSubscription**](#deletesubscription) | **DELETE** `/api/api/subscriptions/holdings/{scope}/{code}` | [EARLY ACCESS] DeleteSubscription: Delete a Subscription, assuming that it is present. |
| [**GetSubscription**](#getsubscription) | **GET** `/api/api/subscriptions/holdings/{scope}/{code}` | [EARLY ACCESS] GetSubscription: Get Subscription |
| [**ListSubscriptions**](#listsubscriptions) | **GET** `/api/api/subscriptions/holdings/{scope}` | [EARLY ACCESS] ListSubscriptions: List the set of Subscription definitions |
| [**UpsertSubscription**](#upsertsubscription) | **POST** `/api/api/subscriptions/holdings` | [EARLY ACCESS] UpsertSubscription: Upsert a Subscription. This creates or updates the subscription definition in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SubscriptionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
```

---

<a id="deletesubscription"></a>
## DeleteSubscription

> AnnulSingleStructuredDataResponse DeleteSubscription(string scope, string code)

[EARLY ACCESS] DeleteSubscription: Delete a Subscription, assuming that it is present.

Delete the specified Subscription definition from a single scope.                The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteSubscription(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Subscription to delete. |
| **code** | **string** | path | **required** | The Subscription to delete. |

### Return type

[AnnulSingleStructuredDataResponse](AnnulSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The AsAt of deletion or failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteSubscriptionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsubscription"></a>
## GetSubscription

> GetSubscriptionResponse GetSubscription(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetSubscription: Get Subscription

Get a Subscription definition from a single scope.                The response will return either the subscription that has been stored, or a failure explaining why the request was unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetSubscriptionResponse result = apiInstance.GetSubscription(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Subscription to retrieve. |
| **code** | **string** | path | **required** | The code of the Subscription to retrieve. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Subscription. Defaults to return the latest version if not specified. |

### Return type

[GetSubscriptionResponse](GetSubscriptionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Subscription or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetSubscriptionResponse> response = apiInstance.GetSubscriptionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listsubscriptions"></a>
## ListSubscriptions

> PagedResourceListOfGetSubscriptionResponse ListSubscriptions(string scope, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EARLY ACCESS] ListSubscriptions: List the set of Subscription definitions

List the set of subscription definitions at the specified date/time and scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfGetSubscriptionResponse result = apiInstance.ListSubscriptions(scope, asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to list subscriptions for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the subscriptions. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **limit** | **int?** | query | optional | Maximum number of results to return. Defaults to 100. |
| **page** | **string?** | query | optional | Pagination token from a previous result to fetch the next page. |

### Return type

[PagedResourceListOfGetSubscriptionResponse](PagedResourceListOfGetSubscriptionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested subscriptions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListSubscriptionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGetSubscriptionResponse> response = apiInstance.ListSubscriptionsWithHttpInfo(scope, asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertsubscription"></a>
## UpsertSubscription

> UpsertSingleStructuredDataResponse UpsertSubscription(UpsertSubscriptionRequest upsertSubscriptionRequest)

[EARLY ACCESS] UpsertSubscription: Upsert a Subscription. This creates or updates the subscription definition in LUSID.

Update or insert one Subscription definition. An item will be updated if it already exists  and inserted if it does not.                The referenced portfolio (and timeline, when supplied) must exist and be readable by the caller.                The response will return the successfully updated or inserted subscription or failure message if unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SubscriptionsApi>();
var upsertSubscriptionRequest = new UpsertSubscriptionRequest(); // UpsertSubscriptionRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertSubscription(upsertSubscriptionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertSubscriptionRequest** | [UpsertSubscriptionRequest](UpsertSubscriptionRequest.md) | body | **required** | The Subscription to update or insert |

### Return type

[UpsertSingleStructuredDataResponse](UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted item or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertSubscriptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertSubscriptionWithHttpInfo(upsertSubscriptionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

