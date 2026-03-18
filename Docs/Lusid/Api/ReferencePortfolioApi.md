# Finbourne.Sdk.Lusid.Api.ReferencePortfolioApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateReferencePortfolio**](#createreferenceportfolio) | **POST** `/api/api/referenceportfolios/{scope}` | CreateReferencePortfolio: Create reference portfolio |
| [**GetReferencePortfolioConstituents**](#getreferenceportfolioconstituents) | **GET** `/api/api/referenceportfolios/{scope}/{code}/constituents` | GetReferencePortfolioConstituents: Get reference portfolio constituents |
| [**ListConstituentsAdjustments**](#listconstituentsadjustments) | **GET** `/api/api/referenceportfolios/{scope}/{code}/constituentsadjustments` | ListConstituentsAdjustments: List constituents adjustments |
| [**UpsertReferencePortfolioConstituentProperties**](#upsertreferenceportfolioconstituentproperties) | **POST** `/api/api/referenceportfolios/{scope}/{code}/constituents/properties` | [EARLY ACCESS] UpsertReferencePortfolioConstituentProperties: Upsert constituent properties |
| [**UpsertReferencePortfolioConstituents**](#upsertreferenceportfolioconstituents) | **POST** `/api/api/referenceportfolios/{scope}/{code}/constituents` | UpsertReferencePortfolioConstituents: Upsert reference portfolio constituents |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ReferencePortfolioApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferencePortfolioApi>();
```

---

<a id="createreferenceportfolio"></a>
## CreateReferencePortfolio

> Portfolio CreateReferencePortfolio(string scope, CreateReferencePortfolioRequest createReferencePortfolioRequest)

CreateReferencePortfolio: Create reference portfolio

Create a reference portfolio in a particular scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferencePortfolioApi>();
var scope = "scope_example";  // string
var createReferencePortfolioRequest = new CreateReferencePortfolioRequest(); // CreateReferencePortfolioRequest
Portfolio result = apiInstance.CreateReferencePortfolio(scope, createReferencePortfolioRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create the reference portfolio. |
| **createReferencePortfolioRequest** | [CreateReferencePortfolioRequest](CreateReferencePortfolioRequest.md) | body | **required** | The definition of the reference portfolio. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created reference portfolio, with populated id |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateReferencePortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.CreateReferencePortfolioWithHttpInfo(scope, createReferencePortfolioRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreferenceportfolioconstituents"></a>
## GetReferencePortfolioConstituents

> GetReferencePortfolioConstituentsResponse GetReferencePortfolioConstituents(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

GetReferencePortfolioConstituents: Get reference portfolio constituents

Get constituents from a reference portfolio at a particular effective time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferencePortfolioApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
GetReferencePortfolioConstituentsResponse result = apiInstance.GetReferencePortfolioConstituents(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the reference portfolio. |
| **code** | **string** | path | **required** | The code of the reference portfolio. Together with the scope this uniquely identifies              the reference portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date of the constituents to retrieve. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve constituents. Defaults to return the latest version              of each constituent if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39; or &#39;ReferenceHolding&#39; domain to decorate onto              constituents. These take the format {domain}/{scope}/{code} e.g. &#39;Instrument/system/Name&#39; or              &#39;ReferenceHolding/strategy/quantsignal&#39;. Defaults to return all available instrument and reference holding properties if not specified. |

### Return type

[GetReferencePortfolioConstituentsResponse](GetReferencePortfolioConstituentsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested reference portfolio constituents |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReferencePortfolioConstituentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetReferencePortfolioConstituentsResponse> response = apiInstance.GetReferencePortfolioConstituentsWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listconstituentsadjustments"></a>
## ListConstituentsAdjustments

> ResourceListOfConstituentsAdjustmentHeader ListConstituentsAdjustments(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOffset? asAtTime = null)

ListConstituentsAdjustments: List constituents adjustments

List adjustments made to constituents in a reference portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferencePortfolioApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var asAtTime = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfConstituentsAdjustmentHeader result = apiInstance.ListConstituentsAdjustments(scope, code, fromEffectiveAt, toEffectiveAt, asAtTime);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the reference portfolio. |
| **code** | **string** | path | **required** | The code of the reference portfolio. Together with the scope this uniquely identifies              the reference portfolio. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | Events between this time (inclusive) and the toEffectiveAt are returned. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | Events between this time (inclusive) and the fromEffectiveAt are returned. |
| **asAtTime** | **DateTimeOffset?** | query | optional | The asAt time for which the result is valid. |

### Return type

[ResourceListOfConstituentsAdjustmentHeader](ResourceListOfConstituentsAdjustmentHeader.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListConstituentsAdjustmentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfConstituentsAdjustmentHeader> response = apiInstance.ListConstituentsAdjustmentsWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAtTime);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreferenceportfolioconstituentproperties"></a>
## UpsertReferencePortfolioConstituentProperties

> UpsertReferencePortfolioConstituentPropertiesResponse UpsertReferencePortfolioConstituentProperties(string scope, string code, UpsertReferencePortfolioConstituentPropertiesRequest upsertReferencePortfolioConstituentPropertiesRequest)

[EARLY ACCESS] UpsertReferencePortfolioConstituentProperties: Upsert constituent properties

Create or update one or more constituent properties for a single constituent in the reference portfolio.  Each property will be updated if it already exists, created if it does not and deleted if value is null.  Both constituent and portfolio must exist at the time when properties are created or updated.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferencePortfolioApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertReferencePortfolioConstituentPropertiesRequest = new UpsertReferencePortfolioConstituentPropertiesRequest(); // UpsertReferencePortfolioConstituentPropertiesRequest
UpsertReferencePortfolioConstituentPropertiesResponse result = apiInstance.UpsertReferencePortfolioConstituentProperties(scope, code, upsertReferencePortfolioConstituentPropertiesRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the reference portfolio. |
| **code** | **string** | path | **required** | The code of the reference portfolio. Together with the scope this uniquely identifies              the reference portfolio. |
| **upsertReferencePortfolioConstituentPropertiesRequest** | [UpsertReferencePortfolioConstituentPropertiesRequest](UpsertReferencePortfolioConstituentPropertiesRequest.md) | body | **required** | The request to modify properties for the constituent. |

### Return type

[UpsertReferencePortfolioConstituentPropertiesResponse](UpsertReferencePortfolioConstituentPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReferencePortfolioConstituentPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertReferencePortfolioConstituentPropertiesResponse> response = apiInstance.UpsertReferencePortfolioConstituentPropertiesWithHttpInfo(scope, code, upsertReferencePortfolioConstituentPropertiesRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreferenceportfolioconstituents"></a>
## UpsertReferencePortfolioConstituents

> UpsertReferencePortfolioConstituentsResponse UpsertReferencePortfolioConstituents(string scope, string code, UpsertReferencePortfolioConstituentsRequest upsertReferencePortfolioConstituentsRequest)

UpsertReferencePortfolioConstituents: Upsert reference portfolio constituents

Add constituents to a reference portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ReferencePortfolioApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertReferencePortfolioConstituentsRequest = new UpsertReferencePortfolioConstituentsRequest(); // UpsertReferencePortfolioConstituentsRequest
UpsertReferencePortfolioConstituentsResponse result = apiInstance.UpsertReferencePortfolioConstituents(scope, code, upsertReferencePortfolioConstituentsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the reference portfolio. |
| **code** | **string** | path | **required** | The code of the reference portfolio. Together with the scope this uniquely identifies              the reference portfolio. |
| **upsertReferencePortfolioConstituentsRequest** | [UpsertReferencePortfolioConstituentsRequest](UpsertReferencePortfolioConstituentsRequest.md) | body | **required** | The constituents to upload to the reference portfolio. |

### Return type

[UpsertReferencePortfolioConstituentsResponse](UpsertReferencePortfolioConstituentsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReferencePortfolioConstituentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertReferencePortfolioConstituentsResponse> response = apiInstance.UpsertReferencePortfolioConstituentsWithHttpInfo(scope, code, upsertReferencePortfolioConstituentsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

