# Finbourne.Sdk.Lusid.Api.AggregatedReturnsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteReturns**](#deletereturns) | **DELETE** `/api/api/returns/{scope}/{code}/{entityType}/{entityScope}/{entityCode}/$delete` | [EXPERIMENTAL] DeleteReturns: Delete Returns |
| [**DeleteReturnsEntity**](#deletereturnsentity) | **DELETE** `/api/api/returns/{scope}/{code}` | [EXPERIMENTAL] DeleteReturnsEntity: Delete returns entity. |
| [**GetAggregatedReturns**](#getaggregatedreturns) | **POST** `/api/api/returns/$aggregated` | [EXPERIMENTAL] GetAggregatedReturns: Calculate aggregated returns for an entity. |
| [**GetReturns**](#getreturns) | **GET** `/api/api/returns/{scope}/{code}/{entityType}/{entityScope}/{entityCode}` | [EXPERIMENTAL] GetReturns: Get Returns |
| [**GetReturnsEntity**](#getreturnsentity) | **GET** `/api/api/returns/{scope}/{code}` | [EXPERIMENTAL] GetReturnsEntity: Get returns entity. |
| [**ListReturnsEntities**](#listreturnsentities) | **GET** `/api/api/returns` | [EXPERIMENTAL] ListReturnsEntities: List returns entities. |
| [**UpsertReturns**](#upsertreturns) | **POST** `/api/api/returns/{scope}/{code}/{entityType}/{entityScope}/{entityCode}` | [EXPERIMENTAL] UpsertReturns: Upsert Returns |
| [**UpsertReturnsEntity**](#upsertreturnsentity) | **POST** `/api/api/returns` | [EXPERIMENTAL] UpsertReturnsEntity: Upsert returns entity. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AggregatedReturnsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
```

---

<a id="deletereturns"></a>
## DeleteReturns

> DeletedEntityResponse DeleteReturns(string scope, string code, string entityType, string entityScope, string entityCode, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, string? period = null)

[EXPERIMENTAL] DeleteReturns: Delete Returns

Cancel the Returns stored under the returns series against the specified entity inside the window.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var entityType = "entityType_example";  // string
var entityScope = "entityScope_example";  // string
var entityCode = "entityCode_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var period = "period_example";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeleteReturns(scope, code, entityType, entityScope, entityCode, fromEffectiveAt, toEffectiveAt, period);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Returns. |
| **code** | **string** | path | **required** | The code of the Returns. |
| **entityType** | **string** | path | **required** | The type of the entity the Returns are stored against: &#39;Portfolio&#39; or &#39;PortfolioGroup&#39;. Available values: Portfolio, PortfolioGroup. |
| **entityScope** | **string** | path | **required** | The scope of the entity. |
| **entityCode** | **string** | path | **required** | The code of the entity. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The start date from which to delete the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The end date from which to delete the Returns. |
| **period** | **string?** | query | optional | The period of the Returns to be deleted. Default value: Daily. Available values: Daily, Monthly. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully deleted Returns data along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteReturnsWithHttpInfo(scope, code, entityType, entityScope, entityCode, fromEffectiveAt, toEffectiveAt, period);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletereturnsentity"></a>
## DeleteReturnsEntity

> DeletedEntityResponse DeleteReturnsEntity(string scope, string code)

[EXPERIMENTAL] DeleteReturnsEntity: Delete returns entity.

Delete returns entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteReturnsEntity(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Returns entity scope. |
| **code** | **string** | path | **required** | Returns entity code. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time that the returns entity was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteReturnsEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteReturnsEntityWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaggregatedreturns"></a>
## GetAggregatedReturns

> AggregatedReturnsResponse GetAggregatedReturns(AggregatedReturnsEntityRequest aggregatedReturnsEntityRequest)

[EXPERIMENTAL] GetAggregatedReturns: Calculate aggregated returns for an entity.

Report daily returns for the entity specified in the request body over the effective window.              Supports a Portfolio, or a PortfolioGroup whose members' returns are rolled up in their common base              currency, on a daily return grid. Returns upserted to the Returns store under the supplied returns id              take precedence: if any exist in the window for a portfolio they are reported as-is and nothing is              calculated for it. A group member's upserted returns are weighted by their stored (net) opening market              value and contribute only on the days they cover; a day with no upserted return for that member is              reported from the other members alone. Otherwise time-weighted returns are calculated using the              recipe, fee handling and flow-discrepancy handling of the persisted Returns entity identified by the              returns id, and the request fails if no such entity exists. A calculated day's return is the day's              profit and loss over the portfolio's net opening value, cash included and signed, so a portfolio              financed by overdraft reports a return on its negative capital; a portfolio whose net opening value is              zero and that takes in no capital during the day reports a zero return, with the day's gain or loss              visible in its market values. When a reporting currency is requested the Returns entity is also              required, as its recipe supplies the FX rates.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var aggregatedReturnsEntityRequest = new AggregatedReturnsEntityRequest(); // AggregatedReturnsEntityRequest
AggregatedReturnsResponse result = apiInstance.GetAggregatedReturns(aggregatedReturnsEntityRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **aggregatedReturnsEntityRequest** | [AggregatedReturnsEntityRequest](../Model/AggregatedReturnsEntityRequest.md) | body | **required** | The entity to report returns for, the returns id under which upserted returns              are stored and the Returns entity that configures a calculation, the effective window and the metrics              to report. |

### Return type

[AggregatedReturnsResponse](../Model/AggregatedReturnsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The aggregated returns grouped by entity. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAggregatedReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AggregatedReturnsResponse> response = apiInstance.GetAggregatedReturnsWithHttpInfo(aggregatedReturnsEntityRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreturns"></a>
## GetReturns

> ResourceListOfPerformanceReturn GetReturns(string scope, string code, string entityType, string entityScope, string entityCode, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, string? period = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetReturns: Get Returns

Get the Returns stored under the returns series against the specified entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var entityType = "entityType_example";  // string
var entityScope = "entityScope_example";  // string
var entityCode = "entityCode_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var period = "period_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfPerformanceReturn result = apiInstance.GetReturns(scope, code, entityType, entityScope, entityCode, fromEffectiveAt, toEffectiveAt, period, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Returns. |
| **code** | **string** | path | **required** | The code of the Returns. |
| **entityType** | **string** | path | **required** | The type of the entity the Returns are stored against: &#39;Portfolio&#39; or &#39;PortfolioGroup&#39;. Available values: Portfolio, PortfolioGroup. |
| **entityScope** | **string** | path | **required** | The scope of the entity. |
| **entityCode** | **string** | path | **required** | The code of the entity. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The start date from which to get the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The end date from which to get the Returns. |
| **period** | **string?** | query | optional | The period for which to show the Returns. Default value: Daily. Available values: Daily, Monthly. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Returns. Defaults to the latest. |

### Return type

[ResourceListOfPerformanceReturn](../Model/ResourceListOfPerformanceReturn.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Returns on the given time period. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPerformanceReturn> response = apiInstance.GetReturnsWithHttpInfo(scope, code, entityType, entityScope, entityCode, fromEffectiveAt, toEffectiveAt, period, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreturnsentity"></a>
## GetReturnsEntity

> ReturnsEntity GetReturnsEntity(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetReturnsEntity: Get returns entity.

Get returns entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ReturnsEntity result = apiInstance.GetReturnsEntity(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Returns entity scope. |
| **code** | **string** | path | **required** | Returns entity code. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the returns entity. Defaults to return              the latest version of the definition if not specified. |

### Return type

[ReturnsEntity](../Model/ReturnsEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested returns entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReturnsEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReturnsEntity> response = apiInstance.GetReturnsEntityWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listreturnsentities"></a>
## ListReturnsEntities

> ResourceListOfReturnsEntity ListReturnsEntities(DateTimeOffset? asAt = null)

[EXPERIMENTAL] ListReturnsEntities: List returns entities.

List returns entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfReturnsEntity result = apiInstance.ListReturnsEntities(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the relation definitions. Defaults to return              the latest version of each definition if not specified. |

### Return type

[ResourceListOfReturnsEntity](../Model/ResourceListOfReturnsEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested returns entities |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListReturnsEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfReturnsEntity> response = apiInstance.ListReturnsEntitiesWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreturns"></a>
## UpsertReturns

> UpsertReturnsResponse UpsertReturns(string scope, string code, string entityType, string entityScope, string entityCode, List<PerformanceReturn> performanceReturn)

[EXPERIMENTAL] UpsertReturns: Upsert Returns

Update or insert returns stored under the returns series against the specified entity. Stored              returns take precedence over a calculation in the aggregated returns of that entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var entityType = "entityType_example";  // string
var entityScope = "entityScope_example";  // string
var entityCode = "entityCode_example";  // string
var performanceReturn = new List<PerformanceReturn>(); // List<PerformanceReturn>
UpsertReturnsResponse result = apiInstance.UpsertReturns(scope, code, entityType, entityScope, entityCode, performanceReturn);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Returns. |
| **code** | **string** | path | **required** | The code of the Returns. |
| **entityType** | **string** | path | **required** | The type of the entity the Returns are stored against: &#39;Portfolio&#39; or &#39;PortfolioGroup&#39;. Available values: Portfolio, PortfolioGroup. |
| **entityScope** | **string** | path | **required** | The scope of the entity. |
| **entityCode** | **string** | path | **required** | The code of the entity. |
| **performanceReturn** | [List&lt;PerformanceReturn&gt;](../Model/PerformanceReturn.md) | body | **required** | This contains the Returns which need to be upsert. |

### Return type

[UpsertReturnsResponse](../Model/UpsertReturnsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the entity that contains the newly updated or inserted Returns. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertReturnsResponse> response = apiInstance.UpsertReturnsWithHttpInfo(scope, code, entityType, entityScope, entityCode, performanceReturn);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreturnsentity"></a>
## UpsertReturnsEntity

> ReturnsEntity UpsertReturnsEntity(ReturnsEntity returnsEntity)

[EXPERIMENTAL] UpsertReturnsEntity: Upsert returns entity.

Upsert returns entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var returnsEntity = new ReturnsEntity(); // ReturnsEntity
ReturnsEntity result = apiInstance.UpsertReturnsEntity(returnsEntity);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **returnsEntity** | [ReturnsEntity](../Model/ReturnsEntity.md) | body | **required** | Definition of the returns entity. |

### Return type

[ReturnsEntity](../Model/ReturnsEntity.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The upserted returns entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReturnsEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReturnsEntity> response = apiInstance.UpsertReturnsEntityWithHttpInfo(returnsEntity);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

