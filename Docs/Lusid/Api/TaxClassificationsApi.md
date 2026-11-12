# Finbourne.Sdk.Lusid.Api.TaxClassificationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetTaxClassification**](#gettaxclassification) | **GET** `/api/api/tax/classifications/{scope}/{luid}` | [EARLY ACCESS] GetTaxClassification: Get a tax classification. |
| [**GetTaxQualifyingInvestmentsHistory**](#gettaxqualifyinginvestmentshistory) | **GET** `/api/api/tax/classifications/{scope}/{luid}/qualifyinginvestments` | [EARLY ACCESS] GetTaxQualifyingInvestmentsHistory: Get the qualifying investments history of an instrument. |
| [**ListTaxClassificationExceptions**](#listtaxclassificationexceptions) | **GET** `/api/api/tax/classifications/exceptions` | [EARLY ACCESS] ListTaxClassificationExceptions: List tax classification exceptions. |
| [**ListTaxClassifications**](#listtaxclassifications) | **GET** `/api/api/tax/classifications` | [EARLY ACCESS] ListTaxClassifications: List tax classifications. |
| [**RemoveTaxTreatmentOverride**](#removetaxtreatmentoverride) | **DELETE** `/api/api/tax/classifications/{scope}/{luid}/override` | [EARLY ACCESS] RemoveTaxTreatmentOverride: Remove a tax treatment override. |
| [**UpsertTaxTreatmentOverride**](#upserttaxtreatmentoverride) | **POST** `/api/api/tax/classifications/{scope}/{luid}/override` | [EARLY ACCESS] UpsertTaxTreatmentOverride: Upsert a tax treatment override. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TaxClassificationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
```

---

<a id="gettaxclassification"></a>
## GetTaxClassification

> TaxClassificationDetail GetTaxClassification(string scope, string luid, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetTaxClassification: Get a tax classification.

Gets one instrument's tax classification together with the ordered decision trace that produced it and the  bitemporal history of every input and override field behind it.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
var scope = "scope_example";  // string
var luid = "luid_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TaxClassificationDetail result = apiInstance.GetTaxClassification(scope, luid, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the instrument. |
| **luid** | **string** | path | **required** | The LUSID instrument identifier of the instrument. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | Optional. The effective datetime or cut label at which to classify. Defaults to the current time. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The as-at datetime at which to read the classification inputs. Defaults to the latest. |

### Return type

[TaxClassificationDetail](../Model/TaxClassificationDetail.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The tax classification of the instrument with its decision trace and field history. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTaxClassificationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaxClassificationDetail> response = apiInstance.GetTaxClassificationWithHttpInfo(scope, luid, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettaxqualifyinginvestmentshistory"></a>
## GetTaxQualifyingInvestmentsHistory

> QualifyingInvestmentsHistory GetTaxQualifyingInvestmentsHistory(string scope, string luid, DateTimeOffset? fromDate = null, DateTimeOffset? toDate = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetTaxQualifyingInvestmentsHistory: Get the qualifying investments history of an instrument.

Returns the daily qualifying investments (60 percent non-equity) test observations of a collective investment  scheme over the requested window, together with every crossing: a pair of consecutive observations on which  the test result flipped.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
var scope = "scope_example";  // string
var luid = "luid_example";  // string
var fromDate = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var toDate = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
QualifyingInvestmentsHistory result = apiInstance.GetTaxQualifyingInvestmentsHistory(scope, luid, fromDate, toDate, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the instrument. |
| **luid** | **string** | path | **required** | The LUSID instrument identifier of the scheme. |
| **fromDate** | **DateTimeOffset?** | query | optional | Optional. The first date of the window, inclusive. Defaults to one year before the toDate. The window may span at most ten years. |
| **toDate** | **DateTimeOffset?** | query | optional | Optional. The last date of the window, inclusive. Defaults to the asAt date. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The as-at datetime at which to read the observations. Defaults to the latest. |

### Return type

[QualifyingInvestmentsHistory](../Model/QualifyingInvestmentsHistory.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The qualifying investments observations and crossings of the instrument. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTaxQualifyingInvestmentsHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<QualifyingInvestmentsHistory> response = apiInstance.GetTaxQualifyingInvestmentsHistoryWithHttpInfo(scope, luid, fromDate, toDate, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtaxclassificationexceptions"></a>
## ListTaxClassificationExceptions

> ResourceListOfTaxClassificationExceptionRecord ListTaxClassificationExceptions(string scope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] ListTaxClassificationExceptions: List tax classification exceptions.

Lists every instrument in the scope that could not be classified at the given time, with the kind of  exception (missing inputs, conflicting set-up, conflicting override, qualifying investments crossing) and a  message naming the fields involved.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
var scope = "scope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfTaxClassificationExceptionRecord result = apiInstance.ListTaxClassificationExceptions(scope, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | query | **required** | The scope of the instruments. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | Optional. The effective datetime or cut label at which to classify. Defaults to the current time. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The as-at datetime at which to read the classification inputs. Defaults to the latest. |

### Return type

[ResourceListOfTaxClassificationExceptionRecord](../Model/ResourceListOfTaxClassificationExceptionRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The instruments that could not be classified and the reason for each. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTaxClassificationExceptionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTaxClassificationExceptionRecord> response = apiInstance.ListTaxClassificationExceptionsWithHttpInfo(scope, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtaxclassifications"></a>
## ListTaxClassifications

> ResourceListOfTaxClassification ListTaxClassifications(string scope, string? treatment = null, string? status = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] ListTaxClassifications: List tax classifications.

Lists the tax classification of every instrument in the scope at the given effective and as-at time. Each  entry carries the treatment leaf the instrument resolved to, the treatment it implies, whether it was  system-derived or overridden, and the rule that fired. Narrow the list with the treatment and status filters.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
var scope = "scope_example";  // string
var treatment = "treatment_example";  // string? (optional)
var status = "status_example";  // string? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfTaxClassification result = apiInstance.ListTaxClassifications(scope, treatment, status, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | query | **required** | The scope of the instruments to classify. |
| **treatment** | **string?** | query | optional | Optional. Only return instruments with this treatment. Available values: ChargeableGains, LoanRelationship, Excluded, Unclassified. |
| **status** | **string?** | query | optional | Optional. Only return instruments with this classification status. Available values: Classified, Overridden, Rejected, Unclassified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | Optional. The effective datetime or cut label at which to classify. Defaults to the current time. |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The as-at datetime at which to read the classification inputs. Defaults to the latest. |

### Return type

[ResourceListOfTaxClassification](../Model/ResourceListOfTaxClassification.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The tax classifications of the instruments in the scope. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTaxClassificationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfTaxClassification> response = apiInstance.ListTaxClassificationsWithHttpInfo(scope, treatment, status, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removetaxtreatmentoverride"></a>
## RemoveTaxTreatmentOverride

> DeletedEntityResponse RemoveTaxTreatmentOverride(string scope, string luid, DateTimeOffset? effectiveAt = null)

[EARLY ACCESS] RemoveTaxTreatmentOverride: Remove a tax treatment override.

Removes the user override from the given effective date onward, returning the instrument to its  system-derived treatment leaf from that date.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
var scope = "scope_example";  // string
var luid = "luid_example";  // string
var effectiveAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.RemoveTaxTreatmentOverride(scope, luid, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the instrument. |
| **luid** | **string** | path | **required** | The LUSID instrument identifier of the instrument. |
| **effectiveAt** | **DateTimeOffset?** | query | optional | Optional. The effective datetime from which the override no longer applies. Defaults to the current time. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime from which the override was removed. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemoveTaxTreatmentOverrideWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.RemoveTaxTreatmentOverrideWithHttpInfo(scope, luid, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttaxtreatmentoverride"></a>
## UpsertTaxTreatmentOverride

> TaxClassification UpsertTaxTreatmentOverride(string scope, string luid, UpsertTaxTreatmentOverrideRequest upsertTaxTreatmentOverrideRequest)

[EARLY ACCESS] UpsertTaxTreatmentOverride: Upsert a tax treatment override.

Replaces the system-derived treatment leaf of the instrument with the given one from the request's effective  date onward. The response is the classification as it now stands at that effective date.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TaxClassificationsApi>();
var scope = "scope_example";  // string
var luid = "luid_example";  // string
var upsertTaxTreatmentOverrideRequest = new UpsertTaxTreatmentOverrideRequest(); // UpsertTaxTreatmentOverrideRequest
TaxClassification result = apiInstance.UpsertTaxTreatmentOverride(scope, luid, upsertTaxTreatmentOverrideRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the instrument. |
| **luid** | **string** | path | **required** | The LUSID instrument identifier of the instrument. |
| **upsertTaxTreatmentOverrideRequest** | [UpsertTaxTreatmentOverrideRequest](../Model/UpsertTaxTreatmentOverrideRequest.md) | body | **required** | The treatment leaf to apply and the effective date it applies from. |

### Return type

[TaxClassification](../Model/TaxClassification.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The classification of the instrument after the override was applied. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTaxTreatmentOverrideWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TaxClassification> response = apiInstance.UpsertTaxTreatmentOverrideWithHttpInfo(scope, luid, upsertTaxTreatmentOverrideRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

