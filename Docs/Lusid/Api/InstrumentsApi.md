# Finbourne.Sdk.Lusid.Api.InstrumentsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchUpsertInstrumentProperties**](#batchupsertinstrumentproperties) | **POST** `/api/api/instruments/$batchupsertproperties` | BatchUpsertInstrumentProperties: Batch upsert instruments properties |
| [**CalculateSettlementDate**](#calculatesettlementdate) | **GET** `/api/api/instruments/{identifierType}/{identifier}/settlementdate` | CalculateSettlementDate: Get the settlement date for an instrument. |
| [**DeleteInstrument**](#deleteinstrument) | **DELETE** `/api/api/instruments/{identifierType}/{identifier}` | DeleteInstrument: Soft delete a single instrument |
| [**DeleteInstrumentProperties**](#deleteinstrumentproperties) | **POST** `/api/api/instruments/{identifierType}/{identifier}/properties/$delete` | DeleteInstrumentProperties: Delete instrument properties |
| [**DeleteInstruments**](#deleteinstruments) | **POST** `/api/api/instruments/$delete` | DeleteInstruments: Soft or hard delete multiple instruments |
| [**GetAllPossibleFeatures**](#getallpossiblefeatures) | **GET** `/api/api/instruments/{instrumentType}/allfeatures` | GetAllPossibleFeatures: Provides list of all possible features for instrument type. |
| [**GetExistingInstrumentCapabilities**](#getexistinginstrumentcapabilities) | **GET** `/api/api/instruments/{identifier}/capabilities` | GetExistingInstrumentCapabilities: Retrieve capabilities of an existing instrument identified by LUID. These include instrument features, and if model is provided it also includes supported address keys and economic dependencies.  Given an lusid instrument id provides instrument capabilities, outlining features, and, given the model, the capabilities also include supported addresses as well as economic dependencies. |
| [**GetExistingInstrumentModels**](#getexistinginstrumentmodels) | **GET** `/api/api/instruments/{identifier}/models` | GetExistingInstrumentModels: Retrieve supported pricing models for an existing instrument identified by LUID. |
| [**GetInstrument**](#getinstrument) | **GET** `/api/api/instruments/{identifierType}/{identifier}` | GetInstrument: Get instrument |
| [**GetInstrumentIdentifierTypes**](#getinstrumentidentifiertypes) | **GET** `/api/api/instruments/identifierTypes` | GetInstrumentIdentifierTypes: Get instrument identifier types |
| [**GetInstrumentPaymentDiary**](#getinstrumentpaymentdiary) | **GET** `/api/api/instruments/{identifierType}/{identifier}/paymentdiary` | GetInstrumentPaymentDiary: Get instrument payment diary |
| [**GetInstrumentProperties**](#getinstrumentproperties) | **GET** `/api/api/instruments/{identifierType}/{identifier}/properties` | GetInstrumentProperties: Get instrument properties |
| [**GetInstrumentPropertyTimeSeries**](#getinstrumentpropertytimeseries) | **GET** `/api/api/instruments/{identifierType}/{identifier}/properties/time-series` | GetInstrumentPropertyTimeSeries: Get instrument property time series |
| [**GetInstrumentRelationships**](#getinstrumentrelationships) | **GET** `/api/api/instruments/{identifierType}/{identifier}/relationships` | GetInstrumentRelationships: Get Instrument relationships |
| [**GetInstruments**](#getinstruments) | **POST** `/api/api/instruments/$get` | GetInstruments: Get instruments |
| [**ListInstrumentProperties**](#listinstrumentproperties) | **GET** `/api/api/instruments/{identifierType}/{identifier}/properties/list` | ListInstrumentProperties: Get instrument properties (with Pagination) |
| [**ListInstruments**](#listinstruments) | **GET** `/api/api/instruments` | ListInstruments: List instruments |
| [**QueryInstrumentCapabilities**](#queryinstrumentcapabilities) | **POST** `/api/api/instruments/capabilities` | QueryInstrumentCapabilities: Query capabilities of a particular instrument in advance of creating it. These include instrument features, and if model is provided it also includes supported address keys and economic dependencies. |
| [**UpdateInstrumentIdentifier**](#updateinstrumentidentifier) | **POST** `/api/api/instruments/{identifierType}/{identifier}` | UpdateInstrumentIdentifier: Update instrument identifier |
| [**UpsertInstruments**](#upsertinstruments) | **POST** `/api/api/instruments` | UpsertInstruments: Upsert instruments |
| [**UpsertInstrumentsProperties**](#upsertinstrumentsproperties) | **POST** `/api/api/instruments/$upsertproperties` | UpsertInstrumentsProperties: Upsert instruments properties |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<InstrumentsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
```

---

<a id="batchupsertinstrumentproperties"></a>
## BatchUpsertInstrumentProperties

> BatchUpsertInstrumentPropertiesResponse BatchUpsertInstrumentProperties(Dictionary<string, UpsertInstrumentPropertyRequest> requestBody, string? scope = null, DateTimeOrCutLabel? identifierEffectiveAt = null, string? successMode = null, string? dataModelScope = null, string? dataModelCode = null)

BatchUpsertInstrumentProperties: Batch upsert instruments properties

Create or update one or more properties for particular instruments.    Each instrument property is updated if it exists and created if it does not. For any failures, a reason  is provided.    Properties have an <i>effectiveFrom</i> datetime from which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var requestBody = new Dictionary<string, UpsertInstrumentPropertyRequest>(); // Dictionary<string, UpsertInstrumentPropertyRequest>
var scope = "\"default\"";  // string? (optional)
var identifierEffectiveAt = "identifierEffectiveAt_example";  // DateTimeOrCutLabel? (optional)
var successMode = "\"Partial\"";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
BatchUpsertInstrumentPropertiesResponse result = apiInstance.BatchUpsertInstrumentProperties(requestBody, scope, identifierEffectiveAt, successMode, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, UpsertInstrumentPropertyRequest&gt;](UpsertInstrumentPropertyRequest.md) | body | **required** | A list of instruments and associated instrument properties to create or update. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **identifierEffectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime used to resolve each instrument from the provided identifiers. Defaults to the current LUSID system datetime if not specified. |
| **successMode** | **string?** | query | optional | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial. Default: `&quot;Partial&quot;` |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[BatchUpsertInstrumentPropertiesResponse](BatchUpsertInstrumentPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successfully upserted properties along with any failures. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertInstrumentPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertInstrumentPropertiesResponse> response = apiInstance.BatchUpsertInstrumentPropertiesWithHttpInfo(requestBody, scope, identifierEffectiveAt, successMode, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="calculatesettlementdate"></a>
## CalculateSettlementDate

> AddBusinessDaysToDateResponse CalculateSettlementDate(string identifierType, string identifier, DateTimeOrCutLabel? transactionDate = null, string? scope = null, DateTimeOffset? asAt = null)

CalculateSettlementDate: Get the settlement date for an instrument.

Get the settlement date for a given trade date and instrument. The calculated settlement date will be in UTC.  If a cut label transaction date is provided, the settlement date will be calculated relative to the absolute UTC datetime.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var transactionDate = "transactionDate_example";  // DateTimeOrCutLabel? (optional)
var scope = "\"default\"";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AddBusinessDaysToDateResponse result = apiInstance.CalculateSettlementDate(identifierType, identifier, transactionDate, scope, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | An identifier type attached to the Instrument. |
| **identifier** | **string** | path | **required** | The identifier value. |
| **transactionDate** | **DateTimeOrCutLabel?** | query | optional | The transaction date to calculate the settlement date from. This can be a UTC datetime offset or a cut label. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the related instrument and calendars for calculation. Defaults to              returning the latest version if not specified. |

### Return type

[AddBusinessDaysToDateResponse](AddBusinessDaysToDateResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The calculated settlement date. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CalculateSettlementDateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AddBusinessDaysToDateResponse> response = apiInstance.CalculateSettlementDateWithHttpInfo(identifierType, identifier, transactionDate, scope, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinstrument"></a>
## DeleteInstrument

> DeleteInstrumentResponse DeleteInstrument(string identifierType, string identifier, string? scope = null)

DeleteInstrument: Soft delete a single instrument

Soft delete a particular instrument, as identified by a particular instrument identifier.                Once deleted, an instrument is marked as inactive and can no longer be referenced when creating or updating  transactions or holdings. You can still query existing transactions and holdings related to the  deleted instrument.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var scope = "\"default\"";  // string? (optional)
DeleteInstrumentResponse result = apiInstance.DeleteInstrument(identifierType, identifier, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to search, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[DeleteInstrumentResponse](DeleteInstrumentResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the instrument was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInstrumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeleteInstrumentResponse> response = apiInstance.DeleteInstrumentWithHttpInfo(identifierType, identifier, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinstrumentproperties"></a>
## DeleteInstrumentProperties

> DeleteInstrumentPropertiesResponse DeleteInstrumentProperties(string identifierType, string identifier, List<string> requestBody, DateTimeOrCutLabel? effectiveAt = null, string? scope = null, string? dataModelScope = null, string? dataModelCode = null)

DeleteInstrumentProperties: Delete instrument properties

Delete one or more properties from a particular instrument. If the properties are time-variant then an effective datetime from which  to delete properties must be specified. If the properties are perpetual then it is invalid to specify an effective datetime for deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var requestBody = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var scope = "\"default\"";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
DeleteInstrumentPropertiesResponse result = apiInstance.DeleteInstrumentProperties(identifierType, identifier, requestBody, effectiveAt, scope, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to search, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | A list of property keys from the &#39;Instruments&#39; domain whose properties to delete. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete time-variant properties from.              The property must exist at the specified &#39;effectiveAt&#39; datetime. If the &#39;effectiveAt&#39; is not provided or is              before the time-variant property exists then a failure is returned. Do not specify this parameter if any of              the properties to delete are perpetual. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[DeleteInstrumentPropertiesResponse](DeleteInstrumentPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The asAt datetime at which properties were deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInstrumentPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeleteInstrumentPropertiesResponse> response = apiInstance.DeleteInstrumentPropertiesWithHttpInfo(identifierType, identifier, requestBody, effectiveAt, scope, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinstruments"></a>
## DeleteInstruments

> DeleteInstrumentsResponse DeleteInstruments(List<string> requestBody, string? deleteMode = null, string? scope = null)

DeleteInstruments: Soft or hard delete multiple instruments

Deletes a number of instruments identified by LusidInstrumentId.                Soft deletion marks the instrument as inactive so it can no longer be referenced when creating or updating transactions or holdings. You can still query existing transactions and holdings related to the inactive instrument.                In addition to the above behaviour, hard deletion: (i) completely removes all external identifiers from the instrument; (ii) marks the instrument as 'Deleted'; (iii) prepends the instrument's name with 'DELETED '; (iv) prevents the instrument from being returned in list instruments queries.                Following hard deletion, an instrument may only be retrieved by making a direct get instrument request for the LusidInstrumentId. Instrument deletion cannot be undone. Please note that currency instruments cannot currently be deleted.  The maximum number of instruments that this method can delete per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var requestBody = new List<string>(); // List<string>
var deleteMode = "Soft";  // string? (optional)
var scope = "\"default\"";  // string? (optional)
DeleteInstrumentsResponse result = apiInstance.DeleteInstruments(requestBody, deleteMode, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | The list of lusidInstrumentId&#39;s to delete. |
| **deleteMode** | **string?** | query | optional | The delete mode to use (defaults to &#39;Soft&#39;). |
| **scope** | **string?** | query | optional | The scope in which the instruments lie. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[DeleteInstrumentsResponse](DeleteInstrumentsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the instruments were deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInstrumentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeleteInstrumentsResponse> response = apiInstance.DeleteInstrumentsWithHttpInfo(requestBody, deleteMode, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallpossiblefeatures"></a>
## GetAllPossibleFeatures

> Dictionary&lt;string, List&lt;string&gt;&gt; GetAllPossibleFeatures(string instrumentType)

GetAllPossibleFeatures: Provides list of all possible features for instrument type.

Provides all possible instrument features an instrument of a given type can provide.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var instrumentType = "instrumentType_example";  // string
Dictionary<string, List<string>> result = apiInstance.GetAllPossibleFeatures(instrumentType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instrumentType** | **string** | path | **required** | A lusid instrument type e.g. Bond, FxOption. |

### Return type

**Dictionary<string, List<string>>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Provides all possible instrument features an instrument of a given type can provide. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllPossibleFeaturesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<string>>> response = apiInstance.GetAllPossibleFeaturesWithHttpInfo(instrumentType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getexistinginstrumentcapabilities"></a>
## GetExistingInstrumentCapabilities

> InstrumentCapabilities GetExistingInstrumentCapabilities(string identifier, string? model = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? instrumentScope = null, string? recipeScope = null, string? recipeCode = null)

GetExistingInstrumentCapabilities: Retrieve capabilities of an existing instrument identified by LUID. These include instrument features, and if model is provided it also includes supported address keys and economic dependencies.  Given an lusid instrument id provides instrument capabilities, outlining features, and, given the model, the capabilities also include supported addresses as well as economic dependencies.

Returns instrument capabilities containing useful information about the instrument and the model. This includes  - features corresponding to the instrument e.g. Optionality:American, Other:InflationLinked  - supported addresses (if model provided) e.g. Valuation/Pv, Valuation/DirtyPriceKey, Valuation/Accrued  - economic dependencies (if model provided) e.g. Cash:USD, Fx:GBP.USD, Rates:GBP.GBPOIS

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifier = "identifier_example";  // string
var model = "model_example";  // string? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var instrumentScope = "\"default\"";  // string? (optional)
var recipeScope = "\"default\"";  // string? (optional)
var recipeCode = "recipeCode_example";  // string? (optional)
InstrumentCapabilities result = apiInstance.GetExistingInstrumentCapabilities(identifier, model, effectiveAt, asAt, instrumentScope, recipeScope, recipeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifier** | **string** | path | **required** | A lusid instrument id identifying the instrument. |
| **model** | **string?** | query | optional | A pricing model for the instrument. Defaults to Unknown if not specified. If not specified the SupportedAddresses and EconomicDependencies are not provided. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the instrument.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument. Defaults to              returning the latest version if not specified. |
| **instrumentScope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **recipeScope** | **string?** | query | optional | The scope in which the recipe lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **recipeCode** | **string?** | query | optional | A unique identifier for an entity, used to obtain configuration recipe details. Default configuration recipe is used if not provided. |

### Return type

[InstrumentCapabilities](InstrumentCapabilities.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Capabilities for a given instrument, with more details should the model be provided. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetExistingInstrumentCapabilitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentCapabilities> response = apiInstance.GetExistingInstrumentCapabilitiesWithHttpInfo(identifier, model, effectiveAt, asAt, instrumentScope, recipeScope, recipeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getexistinginstrumentmodels"></a>
## GetExistingInstrumentModels

> InstrumentModels GetExistingInstrumentModels(string identifier, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? instrumentScope = null, string? recipeScope = null, string? recipeCode = null)

GetExistingInstrumentModels: Retrieve supported pricing models for an existing instrument identified by LUID.

Get the supported pricing models of a single instrument.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifier = "identifier_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var instrumentScope = "\"default\"";  // string? (optional)
var recipeScope = "\"default\"";  // string? (optional)
var recipeCode = "recipeCode_example";  // string? (optional)
InstrumentModels result = apiInstance.GetExistingInstrumentModels(identifier, effectiveAt, asAt, instrumentScope, recipeScope, recipeCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifier** | **string** | path | **required** | A lusid instrument id identifying the instrument. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the instrument.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument. Defaults to              returning the latest version if not specified. |
| **instrumentScope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **recipeScope** | **string?** | query | optional | The scope in which the recipe lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **recipeCode** | **string?** | query | optional | A unique identifier for an entity, used to obtain configuration recipe details. Default configuration recipe is used if not provided. |

### Return type

[InstrumentModels](InstrumentModels.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Models which can be used to value a given instrument. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetExistingInstrumentModelsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentModels> response = apiInstance.GetExistingInstrumentModelsWithHttpInfo(identifier, effectiveAt, asAt, instrumentScope, recipeScope, recipeCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrument"></a>
## GetInstrument

> Instrument GetInstrument(string identifierType, string identifier, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null, string? scope = null, List<string>? relationshipDefinitionIds = null, string? dataModelScope = null, string? dataModelCode = null)

GetInstrument: Get instrument

Retrieve the definition of a particular instrument, as identified by a particular unique identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var scope = "\"default\"";  // string? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
Instrument result = apiInstance.GetInstrument(identifierType, identifier, effectiveAt, asAt, propertyKeys, scope, relationshipDefinitionIds, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to use, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the instrument.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument. Defaults to              returning the latest version if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39; domain to decorate onto              the instrument, or from any domain that supports relationships to decorate onto related entities.              These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39;. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the instrument in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use. |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use. |

### Return type

[Instrument](Instrument.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested instrument. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Instrument> response = apiInstance.GetInstrumentWithHttpInfo(identifierType, identifier, effectiveAt, asAt, propertyKeys, scope, relationshipDefinitionIds, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentidentifiertypes"></a>
## GetInstrumentIdentifierTypes

> ResourceListOfInstrumentIdTypeDescriptor GetInstrumentIdentifierTypes()

GetInstrumentIdentifierTypes: Get instrument identifier types

Retrieve a list of all valid instrument identifier types and whether they are unique or not.                An instrument must have a value for at least one unique identifier type (it can have more than one unique type and value).  In addition, a value is automatically generated for a LUSID Instrument ID (LUID) unique type by the system.                An instrument can have values for multiple non-unique identifier types (or it can have zero non-unique types and values).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
ResourceListOfInstrumentIdTypeDescriptor result = apiInstance.GetInstrumentIdentifierTypes();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfInstrumentIdTypeDescriptor](ResourceListOfInstrumentIdTypeDescriptor.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of valid instrument identifier types. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentIdentifierTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfInstrumentIdTypeDescriptor> response = apiInstance.GetInstrumentIdentifierTypesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentpaymentdiary"></a>
## GetInstrumentPaymentDiary

> InstrumentPaymentDiary GetInstrumentPaymentDiary(string identifierType, string identifier, string recipeScope, string recipeCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? scope = null)

GetInstrumentPaymentDiary: Get instrument payment diary

Get the payment diary of a single instrument.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var recipeScope = "recipeScope_example";  // string
var recipeCode = "recipeCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var scope = "\"default\"";  // string? (optional)
InstrumentPaymentDiary result = apiInstance.GetInstrumentPaymentDiary(identifierType, identifier, recipeScope, recipeCode, effectiveAt, asAt, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The identifier being supplied e.g. \&quot;Figi\&quot;. |
| **identifier** | **string** | path | **required** | The value of the identifier for the requested instrument. |
| **recipeScope** | **string** | query | **required** | The scope of the valuation recipe being used to generate the payment diary |
| **recipeCode** | **string** | query | **required** | The code of the valuation recipe being used to generate the payment diary |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the instrument&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the instrument&#39;s properties. Defaults to return the latest version of each property if not specified. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[InstrumentPaymentDiary](InstrumentPaymentDiary.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The payment diary of the specified instrument |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentPaymentDiaryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentPaymentDiary> response = apiInstance.GetInstrumentPaymentDiaryWithHttpInfo(identifierType, identifier, recipeScope, recipeCode, effectiveAt, asAt, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentproperties"></a>
## GetInstrumentProperties

> InstrumentProperties GetInstrumentProperties(string identifierType, string identifier, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? scope = null)

GetInstrumentProperties: Get instrument properties

List all the properties of a particular instrument, as identified by a particular unique identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var scope = "\"default\"";  // string? (optional)
InstrumentProperties result = apiInstance.GetInstrumentProperties(identifierType, identifier, effectiveAt, asAt, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to search, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the instrument&#39;s properties.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the instrument&#39;s properties. Defaults to returning              the latest version of each property if not specified. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[InstrumentProperties](InstrumentProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified instrument |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentProperties> response = apiInstance.GetInstrumentPropertiesWithHttpInfo(identifierType, identifier, effectiveAt, asAt, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentpropertytimeseries"></a>
## GetInstrumentPropertyTimeSeries

> ResourceListOfPropertyInterval GetInstrumentPropertyTimeSeries(string identifierType, string identifier, string propertyKey, string? identifierEffectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, string? page = null, int? limit = null, string? scope = null)

GetInstrumentPropertyTimeSeries: Get instrument property time series

Retrieve the complete time series (history) for a particular property of an instrument.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var propertyKey = "propertyKey_example";  // string
var identifierEffectiveAt = "identifierEffectiveAt_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var scope = "\"default\"";  // string? (optional)
ResourceListOfPropertyInterval result = apiInstance.GetInstrumentPropertyTimeSeries(identifierType, identifier, propertyKey, identifierEffectiveAt, asAt, filter, page, limit, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to search, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **propertyKey** | **string** | query | **required** | The property key of a property from the &#39;Instrument&#39; domain whose history to retrieve.              This must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39;. |
| **identifierEffectiveAt** | **string?** | query | optional | The effective datetime used to resolve the instrument from the identifier.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument&#39;s property history. Defaults to              returning the current datetime if not supplied. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering,              see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing properties; this value is returned from              the previous call. If a pagination token is provided, the &lt;i&gt;filter&lt;/i&gt;, &lt;i&gt;effectiveAt&lt;/i&gt; and              &lt;i&gt;asAt&lt;/i&gt; fields must not have changed since the original request. For more information, see              https://support.lusid.com/knowledgebase/article/KA-01915. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

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
<summary>Using the GetInstrumentPropertyTimeSeriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyInterval> response = apiInstance.GetInstrumentPropertyTimeSeriesWithHttpInfo(identifierType, identifier, propertyKey, identifierEffectiveAt, asAt, filter, page, limit, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentrelationships"></a>
## GetInstrumentRelationships

> ResourceListOfRelationship GetInstrumentRelationships(string identifierType, string identifier, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null, string? scope = null)

GetInstrumentRelationships: Get Instrument relationships

Get relationships for a particular Instrument.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
var scope = "\"default\"";  // string? (optional)
ResourceListOfRelationship result = apiInstance.GetInstrumentRelationships(identifierType, identifier, effectiveAt, asAt, filter, identifierTypes, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | An identifier type attached to the Instrument. |
| **identifier** | **string** | path | **required** | The identifier value. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get relationships. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relationships. Defaults to return the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter relationships. Users should provide null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifier types (as property keys) used for referencing Persons or Legal Entities.              These can be specified from the &#39;Person&#39; or &#39;LegalEntity&#39; domains and have the format {domain}/{scope}/{code}, for example              &#39;Person/CompanyDetails/Role&#39;. An Empty array may be used to return all related Entities. |
| **scope** | **string?** | query | optional | The entity scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[ResourceListOfRelationship](ResourceListOfRelationship.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relationships for the specified instrument. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetInstrumentRelationshipsWithHttpInfo(identifierType, identifier, effectiveAt, asAt, filter, identifierTypes, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstruments"></a>
## GetInstruments

> GetInstrumentsResponse GetInstruments(string identifierType, List<string> requestBody, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null, string? scope = null, List<string>? relationshipDefinitionIds = null, string? dataModelScope = null, string? dataModelCode = null)

GetInstruments: Get instruments

Retrieve the definition of one or more instruments, as identified by a collection of unique identifiers.                Note that to retrieve all the instruments in the instrument master, use the List instruments endpoint instead.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var requestBody = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var scope = "\"default\"";  // string? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
GetInstrumentsResponse result = apiInstance.GetInstruments(identifierType, requestBody, effectiveAt, asAt, propertyKeys, scope, relationshipDefinitionIds, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | query | **required** | The unique identifier type to use, for example &#39;Figi&#39;. |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | A list of one or more &lt;i&gt;identifierType&lt;/i&gt; values to use to identify instruments. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the instrument definitions.               Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument definitions.               Defaults to returning the latest version of each instrument definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39; domain to decorate onto               each instrument, or from any domain that supports relationships to decorate onto related entities.               These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39;. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities               onto each instrument in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use. |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use. |

### Return type

[GetInstrumentsResponse](GetInstrumentsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested instruments which could be identified along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetInstrumentsResponse> response = apiInstance.GetInstrumentsWithHttpInfo(identifierType, requestBody, effectiveAt, asAt, propertyKeys, scope, relationshipDefinitionIds, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listinstrumentproperties"></a>
## ListInstrumentProperties

> ResourceListOfProperty ListInstrumentProperties(string identifierType, string identifier, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? scope = null)

ListInstrumentProperties: Get instrument properties (with Pagination)

List all the properties of a particular instrument, as identified by a particular unique identifier.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var scope = "\"default\"";  // string? (optional)
ResourceListOfProperty result = apiInstance.ListInstrumentProperties(identifierType, identifier, effectiveAt, asAt, page, limit, scope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to search, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the instrument&#39;s properties.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the instrument&#39;s properties. Defaults to returning              the latest version of each property if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing commands; this value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the results per page to this number. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |

### Return type

[ResourceListOfProperty](ResourceListOfProperty.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified instrument |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListInstrumentPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfProperty> response = apiInstance.ListInstrumentPropertiesWithHttpInfo(identifierType, identifier, effectiveAt, asAt, page, limit, scope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listinstruments"></a>
## ListInstruments

> PagedResourceListOfInstrument ListInstruments(DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? instrumentPropertyKeys = null, string? scope = null, List<string>? relationshipDefinitionIds = null, string? dataModelScope = null, string? dataModelCode = null, string? membershipType = null)

ListInstruments: List instruments

List all the instruments in the instrument master.                To retrieve a particular set of instruments instead, use the Get instruments endpoint.  The maximum number of instruments that this method can list per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "\"State eq 'Active'\"";  // string? (optional)
var instrumentPropertyKeys = new List<string>?(); // List<string>? (optional)
var scope = "\"default\"";  // string? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var membershipType = "membershipType_example";  // string? (optional)
PagedResourceListOfInstrument result = apiInstance.ListInstruments(asAt, effectiveAt, page, sortBy, limit, filter, instrumentPropertyKeys, scope, relationshipDefinitionIds, dataModelScope, dataModelCode, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list instruments. Defaults to returning the latest               version of each instrument if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list instruments.               Defaults to the current LUSID system datetime if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing instruments; this value is returned from               the previous call. If a pagination token is provided, the &lt;i&gt;sortBy&lt;/i&gt;, &lt;i&gt;filter&lt;/i&gt;, &lt;i&gt;effectiveAt&lt;/i&gt; and               &lt;i&gt;asAt&lt;/i&gt; fields must not have changed since the original request.               For more information, see https://support.lusid.com/knowledgebase/article/KA-01915. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Defaults to filtering out inactive instruments               (that is, those that have been deleted). For more information about filtering results,               see https://support.lusid.com/knowledgebase/article/KA-01914. Default: `&quot;State eq &#39;Active&#39;&quot;` |
| **instrumentPropertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Instrument&#39; domain to decorate onto               instruments, or from any domain that supports relationships to decorate onto related entities.               These must have the format {domain}/{scope}/{code}, for example &#39;Instrument/system/Name&#39;. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities               onto each instrument in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use. |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use. |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[PagedResourceListOfInstrument](PagedResourceListOfInstrument.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested instruments |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListInstrumentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfInstrument> response = apiInstance.ListInstrumentsWithHttpInfo(asAt, effectiveAt, page, sortBy, limit, filter, instrumentPropertyKeys, scope, relationshipDefinitionIds, dataModelScope, dataModelCode, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="queryinstrumentcapabilities"></a>
## QueryInstrumentCapabilities

> InstrumentCapabilities QueryInstrumentCapabilities(LusidInstrument lusidInstrument, string? model = null)

QueryInstrumentCapabilities: Query capabilities of a particular instrument in advance of creating it. These include instrument features, and if model is provided it also includes supported address keys and economic dependencies.

Returns instrument capabilities containing useful information about the instrument and the model. This includes  - features corresponding to the instrument e.g. Optionality:American, Other:InflationLinked  - supported addresses (if model provided) e.g. Valuation/Pv, Valuation/DirtyPriceKey, Valuation/Accrued  - economic dependencies (if model provided) e.g. Cash:USD, Fx:GBP.USD, Rates:GBP.GBPOIS

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var lusidInstrument = new LusidInstrument(); // LusidInstrument
var model = "model_example";  // string? (optional)
InstrumentCapabilities result = apiInstance.QueryInstrumentCapabilities(lusidInstrument, model);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **lusidInstrument** | [LusidInstrument](LusidInstrument.md) | body | **required** | The definition of the instrument. |
| **model** | **string?** | query | optional | A pricing model for the instrument. Defaults to Unknown if not specified. If not specified the SupportedAddresses and EconomicDependencies are not provided. |

### Return type

[InstrumentCapabilities](InstrumentCapabilities.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Capabilities for a given instrument, with more details should the model be provided. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QueryInstrumentCapabilitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentCapabilities> response = apiInstance.QueryInstrumentCapabilitiesWithHttpInfo(lusidInstrument, model);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateinstrumentidentifier"></a>
## UpdateInstrumentIdentifier

> Instrument UpdateInstrumentIdentifier(string identifierType, string identifier, UpdateInstrumentIdentifierRequest updateInstrumentIdentifierRequest, string? scope = null, string? dataModelScope = null, string? dataModelCode = null)

UpdateInstrumentIdentifier: Update instrument identifier

Create, update or delete a particular instrument identifier for an instrument.                To delete the identifier, leave the value unspecified in the request. If not being deleted, the  identifier is updated if it exists and created if it does not.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var identifierType = "identifierType_example";  // string
var identifier = "identifier_example";  // string
var updateInstrumentIdentifierRequest = new UpdateInstrumentIdentifierRequest(); // UpdateInstrumentIdentifierRequest
var scope = "\"default\"";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
Instrument result = apiInstance.UpdateInstrumentIdentifier(identifierType, identifier, updateInstrumentIdentifierRequest, scope, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | The unique identifier type to search, for example &#39;Figi&#39;. |
| **identifier** | **string** | path | **required** | An &lt;i&gt;identifierType&lt;/i&gt; value to use to identify the instrument, for example &#39;BBG000BLNNV0&#39;. |
| **updateInstrumentIdentifierRequest** | [UpdateInstrumentIdentifierRequest](UpdateInstrumentIdentifierRequest.md) | body | **required** | The identifier to update or delete. This need not be the same value as the               &#39;identifier&#39; parameter used to retrieve the instrument. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[Instrument](Instrument.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated instrument definition with the identifier created, updated or deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateInstrumentIdentifierWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Instrument> response = apiInstance.UpdateInstrumentIdentifierWithHttpInfo(identifierType, identifier, updateInstrumentIdentifierRequest, scope, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertinstruments"></a>
## UpsertInstruments

> UpsertInstrumentsResponse UpsertInstruments(Dictionary<string, InstrumentDefinition> requestBody, string? scope = null, string? dataModelScope = null, string? dataModelCode = null)

UpsertInstruments: Upsert instruments

Create or update one or more instruments in the instrument master. An instrument is updated  if it already exists and created if it does not.                In the request, each instrument definition should be keyed by a unique correlation ID. This ID is ephemeral  and not stored by LUSID. It serves only to easily identify each instrument in the response.                Note that an instrument must have at least one unique identifier, which is a combination of a type  (such as 'Figi') and a value (such as 'BBG000BS1N49'). In addition, a random value is automatically  generated for a LUSID Instrument ID (LUID) unique type by the system. For more information, see  https://support.lusid.com/knowledgebase/article/KA-01862.                The response returns both the collection of successfully created or updated instruments, as well as those  that failed. For each failure, a reason is provided. It is important to check the failed set for  unsuccessful results.  The maximum number of instruments that this method can upsert per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var requestBody = new Dictionary<string, InstrumentDefinition>(); // Dictionary<string, InstrumentDefinition>
var scope = "\"default\"";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
UpsertInstrumentsResponse result = apiInstance.UpsertInstruments(requestBody, scope, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, InstrumentDefinition&gt;](InstrumentDefinition.md) | body | **required** | The definitions of the instruments to create or update. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[UpsertInstrumentsResponse](UpsertInstrumentsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successfully created or updated instruments along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertInstrumentsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertInstrumentsResponse> response = apiInstance.UpsertInstrumentsWithHttpInfo(requestBody, scope, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertinstrumentsproperties"></a>
## UpsertInstrumentsProperties

> UpsertInstrumentPropertiesResponse UpsertInstrumentsProperties(List<UpsertInstrumentPropertyRequest> upsertInstrumentPropertyRequest, string? scope = null, string? dataModelScope = null, string? dataModelCode = null)

UpsertInstrumentsProperties: Upsert instruments properties

Create or update one or more properties for particular instruments.                Each instrument property is updated if it exists and created if it does not. For any failures, a reason  is provided.                Properties have an <i>effectiveFrom</i> datetime from which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentsApi>();
var upsertInstrumentPropertyRequest = new List<UpsertInstrumentPropertyRequest>(); // List<UpsertInstrumentPropertyRequest>
var scope = "\"default\"";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
UpsertInstrumentPropertiesResponse result = apiInstance.UpsertInstrumentsProperties(upsertInstrumentPropertyRequest, scope, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertInstrumentPropertyRequest** | [List&lt;UpsertInstrumentPropertyRequest&gt;](UpsertInstrumentPropertyRequest.md) | body | **required** | A list of instruments and associated instrument properties to create or update. |
| **scope** | **string?** | query | optional | The scope in which the instrument lies. When not supplied the scope is &#39;default&#39;. Default: `&quot;default&quot;` |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |

### Return type

[UpsertInstrumentPropertiesResponse](UpsertInstrumentPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The asAt datetime at which the properties were created or updated. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertInstrumentsPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertInstrumentPropertiesResponse> response = apiInstance.UpsertInstrumentsPropertiesWithHttpInfo(upsertInstrumentPropertyRequest, scope, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

