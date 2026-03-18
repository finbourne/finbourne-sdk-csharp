# Finbourne.Sdk.Lusid.Api.ComplexMarketDataApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteComplexMarketData**](#deletecomplexmarketdata) | **POST** `/api/api/complexmarketdata/{scope}/$delete` | DeleteComplexMarketData: Delete one or more items of complex market data, assuming they are present. |
| [**GetComplexMarketData**](#getcomplexmarketdata) | **POST** `/api/api/complexmarketdata/{scope}/$get` | GetComplexMarketData: Get complex market data |
| [**ListComplexMarketData**](#listcomplexmarketdata) | **GET** `/api/api/complexmarketdata` | ListComplexMarketData: List the set of ComplexMarketData |
| [**UpsertAppendComplexMarketData**](#upsertappendcomplexmarketdata) | **POST** `/api/api/complexmarketdata/{scope}/$append` | [EARLY ACCESS] UpsertAppendComplexMarketData: Appends a new point to the end of a ComplexMarketData definition. |
| [**UpsertComplexMarketData**](#upsertcomplexmarketdata) | **POST** `/api/api/complexmarketdata/{scope}` | UpsertComplexMarketData: Upsert a set of complex market data items. This creates or updates the data in Lusid. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ComplexMarketDataApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplexMarketDataApi>();
```

---

<a id="deletecomplexmarketdata"></a>
## DeleteComplexMarketData

> AnnulStructuredDataResponse DeleteComplexMarketData(string scope, Dictionary<string, ComplexMarketDataId> requestBody)

DeleteComplexMarketData: Delete one or more items of complex market data, assuming they are present.

Delete one or more specified complex market data items from a single scope. Each item is identified by a unique id which includes  information about its type as well as the exact effective datetime (to the microsecond) at which it entered the system (became valid).                In the request each complex market data item must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each quote in the response.                The response will return both the collection of successfully deleted  complex market data items, as well as those that failed.  For the failures a reason will be provided explaining why the it could not be deleted.                It is important to always check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplexMarketDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, ComplexMarketDataId>(); // Dictionary<string, ComplexMarketDataId>
AnnulStructuredDataResponse result = apiInstance.DeleteComplexMarketData(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the complex market data to delete. |
| **requestBody** | [Dictionary&lt;string, ComplexMarketDataId&gt;](ComplexMarketDataId.md) | body | **required** | The complex market data Ids to delete, each keyed by a unique correlation id. |

### Return type

[AnnulStructuredDataResponse](AnnulStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully deleted ComplexMarketData along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteComplexMarketDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulStructuredDataResponse> response = apiInstance.DeleteComplexMarketDataWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcomplexmarketdata"></a>
## GetComplexMarketData

> GetComplexMarketDataResponse GetComplexMarketData(string scope, Dictionary<string, ComplexMarketDataId> requestBody, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? maxAge = null)

GetComplexMarketData: Get complex market data

Get one or more items of complex market data from a single scope.                Each item can be identified by its time invariant complex market data identifier.                For each id LUSID will return the most recent matched item with respect to the provided (or default) effective datetime.                An optional maximum age range window can be specified which defines how far back to look back for data from the specified effective datetime.  LUSID will return the most recent item within this window.                In the request each complex market data id must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each item in the response.                The response will return three collections. One, the successfully retrieved complex market data. Two, those that had a  valid identifier but could not be found. Three, those that failed because LUSID could not construct a valid identifier from the request.                For the ids that failed to resolve or could not be found a reason will be provided explaining why that is the case.                It is important to always check the failed and not found sets for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplexMarketDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, ComplexMarketDataId>(); // Dictionary<string, ComplexMarketDataId>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var maxAge = "maxAge_example";  // string? (optional)
GetComplexMarketDataResponse result = apiInstance.GetComplexMarketData(scope, requestBody, effectiveAt, asAt, maxAge);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the complex market data to retrieve. |
| **requestBody** | [Dictionary&lt;string, ComplexMarketDataId&gt;](ComplexMarketDataId.md) | body | **required** | The time invariant set of complex data identifiers to retrieve the data for. These need to be               keyed by a unique correlation id allowing the retrieved item to be identified in the response. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to retrieve the complex market data.               Defaults to the current LUSID system datetime if not specified.               Must match the Effective at of each ComplexMarketDataId given in the request body. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the complex market data. Defaults to return the latest version if not specified. |
| **maxAge** | **string?** | query | optional | The duration of the look back window in an ISO8601 time interval format e.g. P1Y2M3DT4H30M (1 year, 2 months, 3 days, 4 hours and 30 minutes).               This is subtracted from the provided effectiveAt datetime to generate a effective datetime window inside which a complex market data item must exist to be retrieved. |

### Return type

[GetComplexMarketDataResponse](GetComplexMarketDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved complex market data along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetComplexMarketDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetComplexMarketDataResponse> response = apiInstance.GetComplexMarketDataWithHttpInfo(scope, requestBody, effectiveAt, asAt, maxAge);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcomplexmarketdata"></a>
## ListComplexMarketData

> ResourceListOfListComplexMarketDataWithMetaDataResponse ListComplexMarketData(DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, string? page = null, int? limit = null)

ListComplexMarketData: List the set of ComplexMarketData

List the set of ComplexMarketData at the specified date/time,  along with the scope the data was stored in and its identifier in that scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplexMarketDataApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfListComplexMarketDataWithMetaDataResponse result = apiInstance.ListComplexMarketData(asAt, effectiveAt, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the ComplexMarketData. Defaults to latest if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to list the ComplexMarketData. Defaults to latest if not specified. Note  that this parameter is not implemented at this time and the latest version of the ComplexMarketData will  always be returned. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing ComplexMarketData; this              value is returned from the previous call. If a pagination token is provided, the effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. If not specified, no pagination will be applied. It is  highly recommended to supply a value for this parameter as the default behaviour will change in the future. |

### Return type

[ResourceListOfListComplexMarketDataWithMetaDataResponse](ResourceListOfListComplexMarketDataWithMetaDataResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested ComplexMarketData |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListComplexMarketDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfListComplexMarketDataWithMetaDataResponse> response = apiInstance.ListComplexMarketDataWithHttpInfo(asAt, effectiveAt, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertappendcomplexmarketdata"></a>
## UpsertAppendComplexMarketData

> UpsertSingleStructuredDataResponse UpsertAppendComplexMarketData(string scope, AppendComplexMarketDataRequest appendComplexMarketDataRequest, DateTimeOffset? asAt = null)

[EARLY ACCESS] UpsertAppendComplexMarketData: Appends a new point to the end of a ComplexMarketData definition.

Update a complex market data item in a single scope by appending a new point onto the end.                NOTE: This operation is only supported for FX curves with one of the following data types:  FxForwardCurveByQuoteReference, FxForwardCurveData, FxForwardPipsCurveData, FxForwardTenorCurveData, FxForwardTenorPipsCurveData

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplexMarketDataApi>();
var scope = "scope_example";  // string
var appendComplexMarketDataRequest = new AppendComplexMarketDataRequest(); // AppendComplexMarketDataRequest
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
UpsertSingleStructuredDataResponse result = apiInstance.UpsertAppendComplexMarketData(scope, appendComplexMarketDataRequest, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the complex market data to append. |
| **appendComplexMarketDataRequest** | [AppendComplexMarketDataRequest](AppendComplexMarketDataRequest.md) | body | **required** | Request definition of the point to append. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the complex market data. Defaults to return the latest version if not specified. |

### Return type

[UpsertSingleStructuredDataResponse](UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully appended ComplexMarketData along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertAppendComplexMarketDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertAppendComplexMarketDataWithHttpInfo(scope, appendComplexMarketDataRequest, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcomplexmarketdata"></a>
## UpsertComplexMarketData

> UpsertStructuredDataResponse UpsertComplexMarketData(string scope, Dictionary<string, UpsertComplexMarketDataRequest> requestBody)

UpsertComplexMarketData: Upsert a set of complex market data items. This creates or updates the data in Lusid.

Update or insert one or more complex market data items in a single scope. An item will be updated if it already exists  and inserted if it does not.                In the request each complex market data item must be keyed by a unique correlation id. This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each complex market data in the response.                The response will return both the collection of successfully updated or inserted complex market data, as well as those that failed.  For the failures a reason will be provided explaining why the item could not be updated or inserted.                It is important to always check the failed set for any unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ComplexMarketDataApi>();
var scope = "scope_example";  // string
var requestBody = new Dictionary<string, UpsertComplexMarketDataRequest>(); // Dictionary<string, UpsertComplexMarketDataRequest>
UpsertStructuredDataResponse result = apiInstance.UpsertComplexMarketData(scope, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to use when updating or inserting the complex market data. |
| **requestBody** | [Dictionary&lt;string, UpsertComplexMarketDataRequest&gt;](UpsertComplexMarketDataRequest.md) | body | **required** | The set of complex market data items to update or insert keyed by a unique correlation id. |

### Return type

[UpsertStructuredDataResponse](UpsertStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted ComplexMarketData along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertComplexMarketDataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertStructuredDataResponse> response = apiInstance.UpsertComplexMarketDataWithHttpInfo(scope, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

