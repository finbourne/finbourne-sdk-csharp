# Finbourne.Sdk.Lusid.Api.PortfoliosApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchUpsertPortfolioAccessMetadata**](#batchupsertportfolioaccessmetadata) | **PUT** `/api/api/portfolios/metadata` | [EARLY ACCESS] BatchUpsertPortfolioAccessMetadata: Upsert multiple Portfolio Access Metadata Rules to multiple Portfolios |
| [**DeleteInstrumentEventInstruction**](#deleteinstrumenteventinstruction) | **DELETE** `/api/api/portfolios/{scope}/{code}/instrumenteventinstructions/{instrumentEventInstructionId}` | [EARLY ACCESS] DeleteInstrumentEventInstruction: Delete Instrument Event Instruction |
| [**DeleteKeyFromPortfolioAccessMetadata**](#deletekeyfromportfolioaccessmetadata) | **DELETE** `/api/api/portfolios/{scope}/{code}/metadata/{metadataKey}` | DeleteKeyFromPortfolioAccessMetadata: Delete a Portfolio Access Metadata Rule |
| [**DeletePortfolio**](#deleteportfolio) | **DELETE** `/api/api/portfolios/{scope}/{code}` | DeletePortfolio: Delete portfolio |
| [**DeletePortfolioProperties**](#deleteportfolioproperties) | **DELETE** `/api/api/portfolios/{scope}/{code}/properties` | DeletePortfolioProperties: Delete portfolio properties |
| [**DeletePortfolioReturns**](#deleteportfolioreturns) | **DELETE** `/api/api/portfolios/{scope}/{code}/returns/{returnScope}/{returnCode}/$delete` | [EARLY ACCESS] DeletePortfolioReturns: Delete Returns |
| [**GetAggregatedReturnsDispersionMetrics**](#getaggregatedreturnsdispersionmetrics) | **POST** `/api/api/portfolios/{scope}/{code}/returns/dispersion/$aggregated` | [EARLY ACCESS] GetAggregatedReturnsDispersionMetrics: Get the Aggregated Returns Dispersion metric |
| [**GetCompositeBreakdown**](#getcompositebreakdown) | **POST** `/api/api/portfolios/{scope}/{code}/returns/breakdown` | [EARLY ACCESS] GetCompositeBreakdown: Get the Composite Breakdown on how the composite Returns are calculated |
| [**GetInstrumentEventInstruction**](#getinstrumenteventinstruction) | **GET** `/api/api/portfolios/{scope}/{code}/instrumenteventinstructions/{instrumentEventInstructionId}` | [EARLY ACCESS] GetInstrumentEventInstruction: Get Instrument Event Instruction |
| [**GetPortfolio**](#getportfolio) | **GET** `/api/api/portfolios/{scope}/{code}` | GetPortfolio: Get portfolio |
| [**GetPortfolioAggregateReturns**](#getportfolioaggregatereturns) | **GET** `/api/api/portfolios/{scope}/{code}/returns/{returnScope}/{returnCode}/aggregated` | [DEPRECATED] GetPortfolioAggregateReturns: Aggregate Returns (This is a deprecated endpoint). |
| [**GetPortfolioAggregatedReturns**](#getportfolioaggregatedreturns) | **POST** `/api/api/portfolios/{scope}/{code}/returns/$aggregated` | GetPortfolioAggregatedReturns: Aggregated Returns |
| [**GetPortfolioCommands**](#getportfoliocommands) | **GET** `/api/api/portfolios/{scope}/{code}/commands` | GetPortfolioCommands: Get portfolio commands |
| [**GetPortfolioMetadata**](#getportfoliometadata) | **GET** `/api/api/portfolios/{scope}/{code}/metadata` | GetPortfolioMetadata: Get access metadata rules for a portfolio |
| [**GetPortfolioProperties**](#getportfolioproperties) | **GET** `/api/api/portfolios/{scope}/{code}/properties` | GetPortfolioProperties: Get portfolio properties |
| [**GetPortfolioPropertyTimeSeries**](#getportfoliopropertytimeseries) | **GET** `/api/api/portfolios/{scope}/{code}/properties/time-series` | GetPortfolioPropertyTimeSeries: Get portfolio property time series |
| [**GetPortfolioRelations**](#getportfoliorelations) | **GET** `/api/api/portfolios/{scope}/{code}/relations` | [EXPERIMENTAL] GetPortfolioRelations: Get portfolio relations |
| [**GetPortfolioRelationships**](#getportfoliorelationships) | **GET** `/api/api/portfolios/{scope}/{code}/relationships` | GetPortfolioRelationships: Get portfolio relationships |
| [**GetPortfolioReturns**](#getportfolioreturns) | **GET** `/api/api/portfolios/{scope}/{code}/returns/{returnScope}/{returnCode}` | GetPortfolioReturns: Get Returns |
| [**GetPortfoliosAccessMetadataByKey**](#getportfoliosaccessmetadatabykey) | **GET** `/api/api/portfolios/{scope}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] GetPortfoliosAccessMetadataByKey: Get an entry identified by a metadataKey in the access metadata object |
| [**ListInstrumentEventInstructions**](#listinstrumenteventinstructions) | **GET** `/api/api/portfolios/{scope}/{code}/instrumenteventinstructions` | [EARLY ACCESS] ListInstrumentEventInstructions: List Instrument Event Instructions |
| [**ListPortfolioProperties**](#listportfolioproperties) | **GET** `/api/api/portfolios/{scope}/{code}/properties/list` | [EARLY ACCESS] ListPortfolioProperties: Get portfolio properties |
| [**ListPortfolios**](#listportfolios) | **GET** `/api/api/portfolios` | ListPortfolios: List portfolios |
| [**ListPortfoliosForScope**](#listportfoliosforscope) | **GET** `/api/api/portfolios/{scope}` | ListPortfoliosForScope: List portfolios for scope |
| [**PatchPortfolio**](#patchportfolio) | **PATCH** `/api/api/portfolios/{scope}/{code}` | PatchPortfolio: Patch portfolio. |
| [**PatchPortfolioAccessMetadata**](#patchportfolioaccessmetadata) | **PATCH** `/api/api/portfolios/{scope}/{code}/metadata` | [EARLY ACCESS] PatchPortfolioAccessMetadata: Patch Access Metadata rules for a Portfolio. |
| [**UpdatePortfolio**](#updateportfolio) | **PUT** `/api/api/portfolios/{scope}/{code}` | UpdatePortfolio: Update portfolio |
| [**UpsertInstrumentEventInstructions**](#upsertinstrumenteventinstructions) | **POST** `/api/api/portfolios/{scope}/{code}/instrumenteventinstructions` | [EARLY ACCESS] UpsertInstrumentEventInstructions: Upsert Instrument Event Instructions |
| [**UpsertPortfolioAccessMetadata**](#upsertportfolioaccessmetadata) | **PUT** `/api/api/portfolios/{scope}/{code}/metadata/{metadataKey}` | UpsertPortfolioAccessMetadata: Upsert a Portfolio Access Metadata Rule associated with specific metadataKey. This creates or updates the data in LUSID. |
| [**UpsertPortfolioProperties**](#upsertportfolioproperties) | **POST** `/api/api/portfolios/{scope}/{code}/properties` | UpsertPortfolioProperties: Upsert portfolio properties |
| [**UpsertPortfolioReturns**](#upsertportfolioreturns) | **POST** `/api/api/portfolios/{scope}/{code}/returns/{returnScope}/{returnCode}` | UpsertPortfolioReturns: Upsert Returns |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PortfoliosApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
```

---

<a id="batchupsertportfolioaccessmetadata"></a>
## BatchUpsertPortfolioAccessMetadata

> BatchUpsertPortfolioAccessMetadataResponse BatchUpsertPortfolioAccessMetadata(Dictionary<string, BatchUpsertPortfolioAccessMetadataRequest> requestBody, DateTimeOrCutLabel? effectiveAt = null, DateTimeOrCutLabel? effectiveUntil = null)

[EARLY ACCESS] BatchUpsertPortfolioAccessMetadata: Upsert multiple Portfolio Access Metadata Rules to multiple Portfolios

Update or insert multiple Access Metadata rules for multiple Portfolios. Items will be updated if they already exist  and inserted if they do not. No other items will be affected    The response will return the successfully updated or inserted Portfolio Access Metadata Rules or a failure message if unsuccessful                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var requestBody = new Dictionary<string, BatchUpsertPortfolioAccessMetadataRequest>(); // Dictionary<string, BatchUpsertPortfolioAccessMetadataRequest>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = "effectiveUntil_example";  // DateTimeOrCutLabel? (optional)
BatchUpsertPortfolioAccessMetadataResponse result = apiInstance.BatchUpsertPortfolioAccessMetadata(requestBody, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, BatchUpsertPortfolioAccessMetadataRequest&gt;](BatchUpsertPortfolioAccessMetadataRequest.md) | body | **required** | The Access Metadata Rules to upsert and the Portfolio identifiers to upsert for |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The date these rules will be effective from |
| **effectiveUntil** | **DateTimeOrCutLabel?** | query | optional | The effective date until which the Access Metadata is valid. If not supplied, this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[BatchUpsertPortfolioAccessMetadataResponse](BatchUpsertPortfolioAccessMetadataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted items or any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertPortfolioAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertPortfolioAccessMetadataResponse> response = apiInstance.BatchUpsertPortfolioAccessMetadataWithHttpInfo(requestBody, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinstrumenteventinstruction"></a>
## DeleteInstrumentEventInstruction

> DeletedEntityResponse DeleteInstrumentEventInstruction(string scope, string code, string instrumentEventInstructionId, DateTimeOrCutLabel? portfolioEffectiveAt = null)

[EARLY ACCESS] DeleteInstrumentEventInstruction: Delete Instrument Event Instruction

Delete a particular instruction for a particular portfolio

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var instrumentEventInstructionId = "instrumentEventInstructionId_example";  // string
var portfolioEffectiveAt = "portfolioEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteInstrumentEventInstruction(scope, code, instrumentEventInstructionId, portfolioEffectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **instrumentEventInstructionId** | **string** | path | **required** | The id of the instruction to be deleted. |
| **portfolioEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date at which the portfolio will be resolved. Defaults to current time if not specified. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the instruction was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInstrumentEventInstructionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteInstrumentEventInstructionWithHttpInfo(scope, code, instrumentEventInstructionId, portfolioEffectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletekeyfromportfolioaccessmetadata"></a>
## DeleteKeyFromPortfolioAccessMetadata

> DeletedEntityResponse DeleteKeyFromPortfolioAccessMetadata(string scope, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

DeleteKeyFromPortfolioAccessMetadata: Delete a Portfolio Access Metadata Rule

Delete the Portfolio Access Metadata Rule that exactly matches the provided identifier parts

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.DeleteKeyFromPortfolioAccessMetadata(scope, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Quote Access Metadata Rule to retrieve. |
| **code** | **string** | path | **required** | Portfolio code |
| **metadataKey** | **string** | path | **required** | The metadataKey identifying the access metadata entry to delete |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date to delete at, if this is not supplied, it will delete all data found |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the delete is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rule that has been deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteKeyFromPortfolioAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteKeyFromPortfolioAccessMetadataWithHttpInfo(scope, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteportfolio"></a>
## DeletePortfolio

> DeletedEntityResponse DeletePortfolio(string scope, string code)

DeletePortfolio: Delete portfolio

Delete a particular portfolio.                The deletion will take effect from the portfolio's creation datetime. This means that the portfolio will no longer exist at any effective datetime, as per the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeletePortfolio(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the portfolio was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePortfolioWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteportfolioproperties"></a>
## DeletePortfolioProperties

> DeletedEntityResponse DeletePortfolioProperties(string scope, string code, List<string> propertyKeys, DateTimeOrCutLabel? effectiveAt = null)

DeletePortfolioProperties: Delete portfolio properties

Delete one or more properties from a particular portfolio. If the properties are time-variant then an effective datetime from which  to delete properties must be specified. If the properties are perpetual then it is invalid to specify an effective datetime for deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeletePortfolioProperties(scope, code, propertyKeys, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | The property keys of the properties to delete. These must take the format              {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. Each property must be from the &#39;Portfolio&#39; domain. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete time-variant properties from.              The property must exist at the specified &#39;effectiveAt&#39; datetime. If the &#39;effectiveAt&#39; is not provided or is              before the time-variant property exists then a failure is returned. Do not specify this parameter if any of              the properties to delete are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the properties were deleted from the specified portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePortfolioPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePortfolioPropertiesWithHttpInfo(scope, code, propertyKeys, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteportfolioreturns"></a>
## DeletePortfolioReturns

> DeletedEntityResponse DeletePortfolioReturns(string scope, string code, string returnScope, string returnCode, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, string? period = null)

[EARLY ACCESS] DeletePortfolioReturns: Delete Returns

Cancel one or more Returns which exist into the specified portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var returnScope = "returnScope_example";  // string
var returnCode = "returnCode_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var period = "period_example";  // string? (optional)
DeletedEntityResponse result = apiInstance.DeletePortfolioReturns(scope, code, returnScope, returnCode, fromEffectiveAt, toEffectiveAt, period);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **returnScope** | **string** | path | **required** | The scope of the Returns. |
| **returnCode** | **string** | path | **required** | The code of the Returns. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The start date from which to delete the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The end date from which to delete the Returns. |
| **period** | **string?** | query | optional | The Period (Daily or Monthly) of the Returns to be deleted. Defaults to Daily. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

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
<summary>Using the DeletePortfolioReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePortfolioReturnsWithHttpInfo(scope, code, returnScope, returnCode, fromEffectiveAt, toEffectiveAt, period);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaggregatedreturnsdispersionmetrics"></a>
## GetAggregatedReturnsDispersionMetrics

> CompositeDispersionResponse GetAggregatedReturnsDispersionMetrics(string scope, string code, AggregatedReturnsDispersionRequest aggregatedReturnsDispersionRequest, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetAggregatedReturnsDispersionMetrics: Get the Aggregated Returns Dispersion metric

Calculate the dispersion metric with the Aggregate Returns which are on the specified portfolio.             This works only for composites which have at least 6 constituents for a full year in.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var aggregatedReturnsDispersionRequest = new AggregatedReturnsDispersionRequest(); // AggregatedReturnsDispersionRequest
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CompositeDispersionResponse result = apiInstance.GetAggregatedReturnsDispersionMetrics(scope, code, aggregatedReturnsDispersionRequest, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **aggregatedReturnsDispersionRequest** | [AggregatedReturnsDispersionRequest](AggregatedReturnsDispersionRequest.md) | body | **required** | The request used in the AggregatedReturnsDispersionMetric. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Returns. Defaults to the latest. |

### Return type

[CompositeDispersionResponse](CompositeDispersionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The aggregated returns grouped by return stream. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAggregatedReturnsDispersionMetricsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CompositeDispersionResponse> response = apiInstance.GetAggregatedReturnsDispersionMetricsWithHttpInfo(scope, code, aggregatedReturnsDispersionRequest, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcompositebreakdown"></a>
## GetCompositeBreakdown

> CompositeBreakdownResponse GetCompositeBreakdown(string scope, string code, CompositeBreakdownRequest compositeBreakdownRequest, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetCompositeBreakdown: Get the Composite Breakdown on how the composite Returns are calculated

Calculate the Composite Returns and return this with the constituents which are included in this calculation

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var compositeBreakdownRequest = new CompositeBreakdownRequest(); // CompositeBreakdownRequest
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CompositeBreakdownResponse result = apiInstance.GetCompositeBreakdown(scope, code, compositeBreakdownRequest, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **compositeBreakdownRequest** | [CompositeBreakdownRequest](CompositeBreakdownRequest.md) | body | **required** | The request used in the GetCompositeBreakdown. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The start date from which to calculate the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The end date for which to calculate the Returns. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Returns. Defaults to the latest. |

### Return type

[CompositeBreakdownResponse](CompositeBreakdownResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The aggregated returns grouped by return stream. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCompositeBreakdownWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CompositeBreakdownResponse> response = apiInstance.GetCompositeBreakdownWithHttpInfo(scope, code, compositeBreakdownRequest, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumenteventinstruction"></a>
## GetInstrumentEventInstruction

> InstrumentEventInstruction GetInstrumentEventInstruction(string scope, string code, string instrumentEventInstructionId, DateTimeOrCutLabel? portfolioEffectiveAt = null, DateTimeOffset? asAt = null, string? timelineScope = null, string? timelineCode = null, string? closedPeriodId = null)

[EARLY ACCESS] GetInstrumentEventInstruction: Get Instrument Event Instruction

Get a particular instruction for a particular portfolio

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var instrumentEventInstructionId = "instrumentEventInstructionId_example";  // string
var portfolioEffectiveAt = "portfolioEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var timelineScope = "timelineScope_example";  // string? (optional)
var timelineCode = "timelineCode_example";  // string? (optional)
var closedPeriodId = "closedPeriodId_example";  // string? (optional)
InstrumentEventInstruction result = apiInstance.GetInstrumentEventInstruction(scope, code, instrumentEventInstructionId, portfolioEffectiveAt, asAt, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **instrumentEventInstructionId** | **string** | path | **required** | The id of the instruction to be retrieved. |
| **portfolioEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date at which the portfolio will be resolved. Defaults to current time if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instruction. Defaults to return the latest version of the instruction if not specified. |
| **timelineScope** | **string?** | query | optional | The scope of the Timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineCode must also be provided. |
| **timelineCode** | **string?** | query | optional | The code of the Timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineScope must also be provided. |
| **closedPeriodId** | **string?** | query | optional | The code of the ClosedPeriod attached to the timeline, used to override the AsAt, and fetch post close activity data.              If this field is left empty and the timelineScope and timelineCode fields are filled out, the portfolioEffectiveAt will be used to resolve the relevant closed period. |

### Return type

[InstrumentEventInstruction](InstrumentEventInstruction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested instrument event instruction |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentEventInstructionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentEventInstruction> response = apiInstance.GetInstrumentEventInstructionWithHttpInfo(scope, code, instrumentEventInstructionId, portfolioEffectiveAt, asAt, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfolio"></a>
## GetPortfolio

> Portfolio GetPortfolio(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

GetPortfolio: Get portfolio

Retrieve the definition of a particular portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
Portfolio result = apiInstance.GetPortfolio(scope, code, effectiveAt, asAt, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the portfolio definition. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio definition. Defaults to returning the latest version of the portfolio definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Portfolio&#39; domain to decorate onto the portfolio,              or from any domain that supports relationships to decorate onto related entities. These must take the format              {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the portfolio in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.GetPortfolioWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfolioaggregatereturns"></a>
## GetPortfolioAggregateReturns

> ResourceListOfAggregatedReturn GetPortfolioAggregateReturns(string scope, string code, string returnScope, string returnCode, string? recipeIdScope = null, string? recipeIdCode = null, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, string? compositeMethod = null, string? period = null, string? outputFrequency = null, List<string>? metrics = null, DateTimeOffset? asAt = null, DateTimeOrCutLabel? alternativeIncDate = null)

[DEPRECATED] GetPortfolioAggregateReturns: Aggregate Returns (This is a deprecated endpoint).

Aggregate Returns which are on the specified portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var returnScope = "returnScope_example";  // string
var returnCode = "returnCode_example";  // string
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var compositeMethod = "compositeMethod_example";  // string? (optional)
var period = "period_example";  // string? (optional)
var outputFrequency = "outputFrequency_example";  // string? (optional)
var metrics = new List<string>?(); // List<string>? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var alternativeIncDate = "alternativeIncDate_example";  // DateTimeOrCutLabel? (optional)
ResourceListOfAggregatedReturn result = apiInstance.GetPortfolioAggregateReturns(scope, code, returnScope, returnCode, recipeIdScope, recipeIdCode, fromEffectiveAt, toEffectiveAt, compositeMethod, period, outputFrequency, metrics, asAt, alternativeIncDate);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **returnScope** | **string** | path | **required** | The scope of the Returns. |
| **returnCode** | **string** | path | **required** | The code of the Returns. |
| **recipeIdScope** | **string?** | query | optional | The Recipe Scope for getting the fx rates |
| **recipeIdCode** | **string?** | query | optional | The Recipe Code for getting the fx rates |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The start date from which to calculate the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The end date for which to calculate the Returns. |
| **compositeMethod** | **string?** | query | optional | The method used to calculate the Portfolio performance:              Equal/Asset. |
| **period** | **string?** | query | optional | The type of the returns used to calculate the aggregation result: Daily/Monthly. |
| **outputFrequency** | **string?** | query | optional | The type of calculated output: Daily/Weekly/Monthly/Quarterly/Half-Yearly/Yearly. |
| **metrics** | [List&lt;string&gt;?](string.md) | query | optional | Determines what type of returns should be calculated, see https://support.lusid.com/knowledgebase/article/KA-01675/en-us for a list of available metrics. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Returns. Defaults to the latest. |
| **alternativeIncDate** | **DateTimeOrCutLabel?** | query | optional | The date from which to consider the Returns on the Portfolio, if this is different from the date when Returns begin. Can be a date string or Portfolio property. |

### Return type

[ResourceListOfAggregatedReturn](ResourceListOfAggregatedReturn.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The aggregated returns. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioAggregateReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAggregatedReturn> response = apiInstance.GetPortfolioAggregateReturnsWithHttpInfo(scope, code, returnScope, returnCode, recipeIdScope, recipeIdCode, fromEffectiveAt, toEffectiveAt, compositeMethod, period, outputFrequency, metrics, asAt, alternativeIncDate);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfolioaggregatedreturns"></a>
## GetPortfolioAggregatedReturns

> AggregatedReturnsResponse GetPortfolioAggregatedReturns(string scope, string code, AggregatedReturnsRequest aggregatedReturnsRequest, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, DateTimeOffset? asAt = null)

GetPortfolioAggregatedReturns: Aggregated Returns

Aggregate Returns which are on the specified portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var aggregatedReturnsRequest = new AggregatedReturnsRequest(); // AggregatedReturnsRequest
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AggregatedReturnsResponse result = apiInstance.GetPortfolioAggregatedReturns(scope, code, aggregatedReturnsRequest, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **aggregatedReturnsRequest** | [AggregatedReturnsRequest](AggregatedReturnsRequest.md) | body | **required** | The request used in the AggregatedReturns. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The start date from which to calculate the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The end date for which to calculate the Returns. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Returns. Defaults to the latest. |

### Return type

[AggregatedReturnsResponse](AggregatedReturnsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The aggregated returns grouped by return stream. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioAggregatedReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AggregatedReturnsResponse> response = apiInstance.GetPortfolioAggregatedReturnsWithHttpInfo(scope, code, aggregatedReturnsRequest, fromEffectiveAt, toEffectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliocommands"></a>
## GetPortfolioCommands

> ResourceListOfProcessedCommand GetPortfolioCommands(string scope, string code, DateTimeOffset? fromAsAt = null, DateTimeOffset? toAsAt = null, string? filter = null, string? page = null, int? limit = null)

GetPortfolioCommands: Get portfolio commands

Get all the commands that modified a particular portfolio, including any input transactions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromAsAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var toAsAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfProcessedCommand result = apiInstance.GetPortfolioCommands(scope, code, fromAsAt, toAsAt, filter, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **fromAsAt** | **DateTimeOffset?** | query | optional | The lower bound asAt datetime (inclusive) from which to retrieve commands. There is no lower bound if this is not specified. |
| **toAsAt** | **DateTimeOffset?** | query | optional | The upper bound asAt datetime (inclusive) from which to retrieve commands. There is no upper bound if this is not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the User ID, specify \&quot;userId.id eq &#39;string&#39;\&quot;.              For more information about filtering, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing commands; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 500 if not specified. |

### Return type

[ResourceListOfProcessedCommand](ResourceListOfProcessedCommand.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The commands that modified the specified portfolio. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioCommandsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfProcessedCommand> response = apiInstance.GetPortfolioCommandsWithHttpInfo(scope, code, fromAsAt, toAsAt, filter, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliometadata"></a>
## GetPortfolioMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; GetPortfolioMetadata(string scope, string code, string? effectiveAt = null, DateTimeOffset? asAt = null)

GetPortfolioMetadata: Get access metadata rules for a portfolio

Pass the scope and portfolio code parameters to retrieve the AccessMetadata associated with a portfolio

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.GetPortfolioMetadata(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Access Metadata Rule to retrieve. |
| **code** | **string** | path | **required** | Portfolio code |
| **effectiveAt** | **string?** | query | optional | The effectiveAt datetime at which to retrieve the access metadata rule. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio access metadata. |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The filtered list of results |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.GetPortfolioMetadataWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfolioproperties"></a>
## GetPortfolioProperties

> PortfolioProperties GetPortfolioProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

GetPortfolioProperties: Get portfolio properties

List all the properties of a particular portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PortfolioProperties result = apiInstance.GetPortfolioProperties(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the portfolio&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the portfolio&#39;s properties. Defaults to returning the latest version of each property if not specified. |

### Return type

[PortfolioProperties](PortfolioProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioProperties> response = apiInstance.GetPortfolioPropertiesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliopropertytimeseries"></a>
## GetPortfolioPropertyTimeSeries

> ResourceListOfPropertyInterval GetPortfolioPropertyTimeSeries(string scope, string code, string propertyKey, string? portfolioEffectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, string? page = null, int? limit = null)

GetPortfolioPropertyTimeSeries: Get portfolio property time series

Show the complete time series (history) for a particular portfolio property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var propertyKey = "propertyKey_example";  // string
var portfolioEffectiveAt = "portfolioEffectiveAt_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfPropertyInterval result = apiInstance.GetPortfolioPropertyTimeSeries(scope, code, propertyKey, portfolioEffectiveAt, asAt, filter, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **propertyKey** | **string** | query | **required** | The property key of the property whose history to show.              This must be from the &#39;Portfolio&#39; domain and in the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **portfolioEffectiveAt** | **string?** | query | optional | The effective datetime used to resolve the portfolio. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to show the history. Defaults to returning the current datetime if not supplied. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering,              see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing properties; this value is returned from              the previous call. If a pagination token is provided, the filter, portfolioEffectiveAt, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. |

### Return type

[ResourceListOfPropertyInterval](ResourceListOfPropertyInterval.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time series of the property |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioPropertyTimeSeriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyInterval> response = apiInstance.GetPortfolioPropertyTimeSeriesWithHttpInfo(scope, code, propertyKey, portfolioEffectiveAt, asAt, filter, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliorelations"></a>
## GetPortfolioRelations

> ResourceListOfRelation GetPortfolioRelations(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EXPERIMENTAL] GetPortfolioRelations: Get portfolio relations

Get relations for a particular portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelation result = apiInstance.GetPortfolioRelations(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve relations. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relations. Defaults to returning the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the relations. Provide a null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifier types (as property keys) used for referencing Persons or Legal Entities.              These must be from the &#39;Person&#39; or &#39;LegalEntity&#39; domains and have the format {domain}/{scope}/{code}, for example              &#39;Person/CompanyDetails/Role&#39;. Only identifier types provided will be used to look up relevant entities in relations. If not applicable, provide an empty array. |

### Return type

[ResourceListOfRelation](ResourceListOfRelation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relations for the specified portfolio. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioRelationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelation> response = apiInstance.GetPortfolioRelationsWithHttpInfo(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliorelationships"></a>
## GetPortfolioRelationships

> ResourceListOfRelationship GetPortfolioRelationships(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

GetPortfolioRelationships: Get portfolio relationships

Get relationships for a particular portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelationship result = apiInstance.GetPortfolioRelationships(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve relationships. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relationships. Defaults to returning the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the relationships. Provide a null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifier types (as property keys) used for referencing Persons or Legal Entities.              These can be specified from the &#39;Person&#39; or &#39;LegalEntity&#39; domains and have the format {domain}/{scope}/{code}, for example              &#39;Person/CompanyDetails/Role&#39;. An Empty array may be used to return all related Entities. |

### Return type

[ResourceListOfRelationship](ResourceListOfRelationship.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relationships for the specified portfolio. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetPortfolioRelationshipsWithHttpInfo(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfolioreturns"></a>
## GetPortfolioReturns

> ResourceListOfPerformanceReturn GetPortfolioReturns(string scope, string code, string returnScope, string returnCode, DateTimeOrCutLabel? fromEffectiveAt = null, DateTimeOrCutLabel? toEffectiveAt = null, string? period = null, DateTimeOffset? asAt = null)

GetPortfolioReturns: Get Returns

Get Returns which are on the specified portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var returnScope = "returnScope_example";  // string
var returnCode = "returnCode_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var period = "period_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfPerformanceReturn result = apiInstance.GetPortfolioReturns(scope, code, returnScope, returnCode, fromEffectiveAt, toEffectiveAt, period, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **returnScope** | **string** | path | **required** | The scope of the Returns. |
| **returnCode** | **string** | path | **required** | The code of the Returns. |
| **fromEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The start date from which to get the Returns. |
| **toEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The end date from which to get the Returns. |
| **period** | **string?** | query | optional | Show the Returns on a Daily or Monthly period. Defaults to Daily. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Returns. Defaults to the latest. |

### Return type

[ResourceListOfPerformanceReturn](ResourceListOfPerformanceReturn.md)

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
<summary>Using the GetPortfolioReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPerformanceReturn> response = apiInstance.GetPortfolioReturnsWithHttpInfo(scope, code, returnScope, returnCode, fromEffectiveAt, toEffectiveAt, period, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliosaccessmetadatabykey"></a>
## GetPortfoliosAccessMetadataByKey

> List&lt;AccessMetadataValue&gt; GetPortfoliosAccessMetadataByKey(string scope, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetPortfoliosAccessMetadataByKey: Get an entry identified by a metadataKey in the access metadata object

Get a specific portfolio access metadata rule by specifying the corresponding identifier parts                No matching will be performed through this endpoint. To retrieve a rule, it is necessary to specify, exactly, the identifier of the rule

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<AccessMetadataValue> result = apiInstance.GetPortfoliosAccessMetadataByKey(scope, code, metadataKey, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Access Metadata Rule to retrieve. |
| **code** | **string** | path | **required** | The code of the portfolio |
| **metadataKey** | **string** | path | **required** | Key of the metadata to retrieve |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date of the rule |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio access metadata. |

### Return type

[List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Portfolio Access Metadata Rule or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfoliosAccessMetadataByKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AccessMetadataValue>> response = apiInstance.GetPortfoliosAccessMetadataByKeyWithHttpInfo(scope, code, metadataKey, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listinstrumenteventinstructions"></a>
## ListInstrumentEventInstructions

> PagedResourceListOfInstrumentEventInstruction ListInstrumentEventInstructions(string scope, string code, DateTimeOrCutLabel? portfolioEffectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, string? timelineScope = null, string? timelineCode = null, string? closedPeriodId = null)

[EARLY ACCESS] ListInstrumentEventInstructions: List Instrument Event Instructions

Lists all instructions for a particular portfolio

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var portfolioEffectiveAt = "portfolioEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var timelineScope = "timelineScope_example";  // string? (optional)
var timelineCode = "timelineCode_example";  // string? (optional)
var closedPeriodId = "closedPeriodId_example";  // string? (optional)
PagedResourceListOfInstrumentEventInstruction result = apiInstance.ListInstrumentEventInstructions(scope, code, portfolioEffectiveAt, asAt, page, limit, filter, sortBy, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **portfolioEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date at which the portfolio will be resolved. Defaults to current time if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instructions. Defaults to latest if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing instructions; this value is returned from the previous call.              If a pagination token is provided, the filter, effectiveAt and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **timelineScope** | **string?** | query | optional | The scope of the Timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineCode must also be provided. |
| **timelineCode** | **string?** | query | optional | The code of the Timeline, used to override the AsAt, and fetch post close activity data.              If this is provided, timelineScope must also be provided. |
| **closedPeriodId** | **string?** | query | optional | The code of the ClosedPeriod attached to the timeline, used to override the AsAt, and fetch post close activity data.              If this field is left empty and the timelineScope and timelineCode fields are filled out, the portfolioEffectiveAt will be used to resolve the relevant closed period. |

### Return type

[PagedResourceListOfInstrumentEventInstruction](PagedResourceListOfInstrumentEventInstruction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested instrument event instructions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListInstrumentEventInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfInstrumentEventInstruction> response = apiInstance.ListInstrumentEventInstructionsWithHttpInfo(scope, code, portfolioEffectiveAt, asAt, page, limit, filter, sortBy, timelineScope, timelineCode, closedPeriodId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listportfolioproperties"></a>
## ListPortfolioProperties

> ResourceListOfProperty ListPortfolioProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null)

[EARLY ACCESS] ListPortfolioProperties: Get portfolio properties

List all the properties of a particular portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfProperty result = apiInstance.ListPortfolioProperties(scope, code, effectiveAt, asAt, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the portfolio&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the portfolio&#39;s properties. Defaults to returning the latest version of each property if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing commands; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results per page to this number. |

### Return type

[ResourceListOfProperty](ResourceListOfProperty.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPortfolioPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfProperty> response = apiInstance.ListPortfolioPropertiesWithHttpInfo(scope, code, effectiveAt, asAt, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listportfolios"></a>
## ListPortfolios

> ResourceListOfPortfolio ListPortfolios(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, string? query = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

ListPortfolios: List portfolios

List all the portfolios matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var query = "query_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
ResourceListOfPortfolio result = apiInstance.ListPortfolios(effectiveAt, asAt, page, limit, filter, sortBy, query, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the portfolios. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the portfolios. Defaults to returning the latest version              of each portfolio if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing portfolios; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the transaction type, specify \&quot;type eq &#39;Transaction&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **query** | **string?** | query | optional | Expression specifying the criteria that the returned portfolios must meet. For example, to see which              portfolios have holdings in instruments with a LusidInstrumentId (LUID) of &#39;LUID_PPA8HI6M&#39; or a Figi of &#39;BBG000BLNNH6&#39;,              specify \&quot;instrument.identifiers in ((&#39;LusidInstrumentId&#39;, &#39;LUID_PPA8HI6M&#39;), (&#39;Figi&#39;, &#39;BBG000BLNNH6&#39;))\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Portfolio&#39; domain to decorate onto each portfolio,              or from any domain that supports relationships to decorate onto related entities. These must take the              format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the portfolios in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[ResourceListOfPortfolio](ResourceListOfPortfolio.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolios |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPortfoliosWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPortfolio> response = apiInstance.ListPortfoliosWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, query, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listportfoliosforscope"></a>
## ListPortfoliosForScope

> ResourceListOfPortfolio ListPortfoliosForScope(string scope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

ListPortfoliosForScope: List portfolios for scope

List all the portfolios in a particular scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
ResourceListOfPortfolio result = apiInstance.ListPortfoliosForScope(scope, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope whose portfolios to list. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the portfolios. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the portfolios. Defaults to returning the latest version              of each portfolio if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing portfolios. This  value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to return only transactions with a transaction type of &#39;Buy&#39;, specify \&quot;type eq &#39;Buy&#39;\&quot;.              For more information about filtering results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Portfolio&#39; domain to decorate onto each portfolio,              or from any domain that supports relationships to decorate onto related entities. These must take the              format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the portfolios in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[ResourceListOfPortfolio](ResourceListOfPortfolio.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The portfolios in the specified scope |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPortfoliosForScopeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPortfolio> response = apiInstance.ListPortfoliosForScopeWithHttpInfo(scope, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchportfolio"></a>
## PatchPortfolio

> Portfolio PatchPortfolio(string scope, string code, List<Operation> operation)

PatchPortfolio: Patch portfolio.

Create or update certain fields for a particular  portfolio.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: Created, InstrumentScopes, Type.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
Portfolio result = apiInstance.PatchPortfolio(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the              scope this uniquely identifies the portfolio. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more check: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly patched portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchPortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.PatchPortfolioWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchportfolioaccessmetadata"></a>
## PatchPortfolioAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; PatchPortfolioAccessMetadata(string scope, string code, List<AccessMetadataOperation> accessMetadataOperation, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] PatchPortfolioAccessMetadata: Patch Access Metadata rules for a Portfolio.

Patch Portfolio Access Metadata Rules in a single scope.  The behaviour is defined by the JSON Patch specification.                Currently only 'add' is a supported operation on the patch document.    Currently only valid metadata keys are supported paths on the patch document.    The response will return any affected Portfolio Access Metadata rules or a failure message if unsuccessful.    It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var accessMetadataOperation = new List<AccessMetadataOperation>(); // List<AccessMetadataOperation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.PatchPortfolioAccessMetadata(scope, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Access Metadata Rule. |
| **code** | **string** | path | **required** | Portfolio code |
| **accessMetadataOperation** | [List&lt;AccessMetadataOperation&gt;](AccessMetadataOperation.md) | body | **required** | The Json Patch document |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The date this rule will effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully patched items. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchPortfolioAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.PatchPortfolioAccessMetadataWithHttpInfo(scope, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateportfolio"></a>
## UpdatePortfolio

> Portfolio UpdatePortfolio(string scope, string code, UpdatePortfolioRequest updatePortfolioRequest, DateTimeOrCutLabel? effectiveAt = null)

UpdatePortfolio: Update portfolio

Update the definition of a particular portfolio.                Note that not all elements of a portfolio definition are  modifiable due to the potential implications for data already stored.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var updatePortfolioRequest = new UpdatePortfolioRequest(); // UpdatePortfolioRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
Portfolio result = apiInstance.UpdatePortfolio(scope, code, updatePortfolioRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **updatePortfolioRequest** | [UpdatePortfolioRequest](UpdatePortfolioRequest.md) | body | **required** | The updated portfolio definition. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to update the definition. Defaults to the current               LUSID system datetime if not specified. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated definition of the portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.UpdatePortfolioWithHttpInfo(scope, code, updatePortfolioRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertinstrumenteventinstructions"></a>
## UpsertInstrumentEventInstructions

> InstrumentEventInstructionsResponse UpsertInstrumentEventInstructions(string scope, string code, string successMode, Dictionary<string, InstrumentEventInstructionRequest> requestBody, DateTimeOrCutLabel? portfolioEffectiveAt = null)

[EARLY ACCESS] UpsertInstrumentEventInstructions: Upsert Instrument Event Instructions

Batch upsert for instrument event instructions, for the portfolio or individual holdings

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var successMode = "\"Partial\"";  // string
var requestBody = new Dictionary<string, InstrumentEventInstructionRequest>(); // Dictionary<string, InstrumentEventInstructionRequest>
var portfolioEffectiveAt = "portfolioEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
InstrumentEventInstructionsResponse result = apiInstance.UpsertInstrumentEventInstructions(scope, code, successMode, requestBody, portfolioEffectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **successMode** | **string** | query | **required** | Whether the batch request should fail atomically or in a partial fashion - allowed values: Atomic, Partial (default) Default: `&quot;Partial&quot;` |
| **requestBody** | [Dictionary&lt;string, InstrumentEventInstructionRequest&gt;](InstrumentEventInstructionRequest.md) | body | **required** | The instructions to be upserted to the portfolio. |
| **portfolioEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date at which the portfolio will be resolved. Defaults to current time if not specified. |

### Return type

[InstrumentEventInstructionsResponse](InstrumentEventInstructionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly inserted or updated instrument event instructions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertInstrumentEventInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentEventInstructionsResponse> response = apiInstance.UpsertInstrumentEventInstructionsWithHttpInfo(scope, code, successMode, requestBody, portfolioEffectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertportfolioaccessmetadata"></a>
## UpsertPortfolioAccessMetadata

> ResourceListOfAccessMetadataValueOf UpsertPortfolioAccessMetadata(string scope, string code, string metadataKey, UpsertPortfolioAccessMetadataRequest upsertPortfolioAccessMetadataRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

UpsertPortfolioAccessMetadata: Upsert a Portfolio Access Metadata Rule associated with specific metadataKey. This creates or updates the data in LUSID.

Update or insert one Portfolio Access Metadata Rule in a single scope. An item will be updated if it already exists  and inserted if it does not.    The response will return the successfully updated or inserted Portfolio Access Metadata Rule or failure message if unsuccessful    It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exists with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var upsertPortfolioAccessMetadataRequest = new UpsertPortfolioAccessMetadataRequest(); // UpsertPortfolioAccessMetadataRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfAccessMetadataValueOf result = apiInstance.UpsertPortfolioAccessMetadata(scope, code, metadataKey, upsertPortfolioAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to use when updating or inserting the Portfolio Access Metadata Rule. |
| **code** | **string** | path | **required** | Portfolio code |
| **metadataKey** | **string** | path | **required** | Key of the access metadata to upsert |
| **upsertPortfolioAccessMetadataRequest** | [UpsertPortfolioAccessMetadataRequest](UpsertPortfolioAccessMetadataRequest.md) | body | **required** | The Portfolio Access Metadata Rule to update or insert |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The date this rule will effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[ResourceListOfAccessMetadataValueOf](ResourceListOfAccessMetadataValueOf.md)

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
<summary>Using the UpsertPortfolioAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAccessMetadataValueOf> response = apiInstance.UpsertPortfolioAccessMetadataWithHttpInfo(scope, code, metadataKey, upsertPortfolioAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertportfolioproperties"></a>
## UpsertPortfolioProperties

> PortfolioProperties UpsertPortfolioProperties(string scope, string code, Dictionary<string, Property> requestBody)

UpsertPortfolioProperties: Upsert portfolio properties

Create or update one or more properties for a particular portfolio. A property is updated if it  already exists and created if it does not. All properties must be from the 'Portfolio' domain.                Properties have an <i>effectiveFrom</i> datetime from which the property is valid, and an <i>effectiveUntil</i>  datetime until which it is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>(); // Dictionary<string, Property>
PortfolioProperties result = apiInstance.UpsertPortfolioProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio. |
| **code** | **string** | path | **required** | The code of the portfolio. Together with the scope this uniquely identifies the portfolio. |
| **requestBody** | [Dictionary&lt;string, Property&gt;](Property.md) | body | **required** | The properties to be created or updated. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code}, for example               &#39;Portfolio/Manager/Id&#39;. |

### Return type

[PortfolioProperties](PortfolioProperties.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted properties |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPortfolioPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioProperties> response = apiInstance.UpsertPortfolioPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertportfolioreturns"></a>
## UpsertPortfolioReturns

> UpsertReturnsResponse UpsertPortfolioReturns(string scope, string code, string returnScope, string returnCode, List<PerformanceReturn> performanceReturn)

UpsertPortfolioReturns: Upsert Returns

Update or insert returns into the specified portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var returnScope = "returnScope_example";  // string
var returnCode = "returnCode_example";  // string
var performanceReturn = new List<PerformanceReturn>(); // List<PerformanceReturn>
UpsertReturnsResponse result = apiInstance.UpsertPortfolioReturns(scope, code, returnScope, returnCode, performanceReturn);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio. |
| **code** | **string** | path | **required** | The code of the  Portfolio. |
| **returnScope** | **string** | path | **required** | The scope of the Returns. |
| **returnCode** | **string** | path | **required** | The code of the Returns. |
| **performanceReturn** | [List&lt;PerformanceReturn&gt;](PerformanceReturn.md) | body | **required** | This contains the Returns which need to be upsert. |

### Return type

[UpsertReturnsResponse](UpsertReturnsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The version of the portfolio that contains the newly updated or inserted Returns. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPortfolioReturnsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertReturnsResponse> response = apiInstance.UpsertPortfolioReturnsWithHttpInfo(scope, code, returnScope, returnCode, performanceReturn);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

