# Finbourne.Sdk.Horizon.Api.InstrumentApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateInstrument**](#createinstrument) | **POST** `/horizon/api/instrument/onboarding/create` | [EARLY ACCESS] CreateInstrument: Creates and masters instruments with third party vendors. |
| [**EnrichInstrument**](#enrichinstrument) | **POST** `/horizon/api/instrument/onboarding/enrich` | [EARLY ACCESS] EnrichInstrument: Enriches an existing LUSID instrument using vendor data. Enrichment included identifiers, properties and market data. |
| [**GetOpenFigiParameterOption**](#getopenfigiparameteroption) | **GET** `/horizon/api/instrument/onboarding/search/openfigi/parameterOptions` | [EARLY ACCESS] GetOpenFigiParameterOption: Get all supported market sector values for OpenFigi search |
| [**RetrievePermIdResult**](#retrievepermidresult) | **GET** `/horizon/api/instrument/onboarding/search/permid/{id}` | [EARLY ACCESS] RetrievePermIdResult: Retrieve PermId results from a previous query. |
| [**SearchOpenFigi**](#searchopenfigi) | **GET** `/horizon/api/instrument/onboarding/search/openfigi` | [EARLY ACCESS] SearchOpenFigi: Search OpenFigi for instruments that match the specified terms. |
| [**Vendors**](#vendors) | **GET** `/horizon/api/instrument/onboarding/vendors` | [EARLY ACCESS] Vendors: Gets the VendorProducts of any supported and licenced integrations for a given market sector and security type. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<InstrumentApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
```

---

<a id="createinstrument"></a>
## CreateInstrument

> OnboardInstrumentResponse CreateInstrument(OnboardInstrumentRequest onboardInstrumentRequest)

[EARLY ACCESS] CreateInstrument: Creates and masters instruments with third party vendors.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
var onboardInstrumentRequest = new OnboardInstrumentRequest(); // OnboardInstrumentRequest
OnboardInstrumentResponse result = apiInstance.CreateInstrument(onboardInstrumentRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **onboardInstrumentRequest** | [OnboardInstrumentRequest](OnboardInstrumentRequest.md) | body | **required** |  |

### Return type

[OnboardInstrumentResponse](OnboardInstrumentResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateInstrumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<OnboardInstrumentResponse> response = apiInstance.CreateInstrumentWithHttpInfo(onboardInstrumentRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="enrichinstrument"></a>
## EnrichInstrument

> EnrichmentResponse EnrichInstrument(string vendorProductKey, Identifiers identifiers)

[EARLY ACCESS] EnrichInstrument: Enriches an existing LUSID instrument using vendor data. Enrichment included identifiers, properties and market data.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
var vendorProductKey = "vendorProductKey_example";  // string
var identifiers = new Identifiers(); // Identifiers
EnrichmentResponse result = apiInstance.EnrichInstrument(vendorProductKey, identifiers);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **vendorProductKey** | **string** | query | **required** |  |
| **identifiers** | [Identifiers](Identifiers.md) | body | **required** |  |

### Return type

[EnrichmentResponse](EnrichmentResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the EnrichInstrumentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<EnrichmentResponse> response = apiInstance.EnrichInstrumentWithHttpInfo(vendorProductKey, identifiers);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getopenfigiparameteroption"></a>
## GetOpenFigiParameterOption

> List&lt;AllowedParameterValue&gt; GetOpenFigiParameterOption(OpenFigiParameterOptionName parameterName)

[EARLY ACCESS] GetOpenFigiParameterOption: Get all supported market sector values for OpenFigi search

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
var parameterName = (OpenFigiParameterOptionName) "IdType";  // OpenFigiParameterOptionName
List<AllowedParameterValue> result = apiInstance.GetOpenFigiParameterOption(parameterName);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **parameterName** | **OpenFigiParameterOptionName** | query | **required** | OpenFigi API Parameters that have a restricted / permitted range of values. |

### Return type

[List&lt;AllowedParameterValue&gt;](AllowedParameterValue.md)

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
<summary>Using the GetOpenFigiParameterOptionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AllowedParameterValue>> response = apiInstance.GetOpenFigiParameterOptionWithHttpInfo(parameterName);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="retrievepermidresult"></a>
## RetrievePermIdResult

> List&lt;PermIdData&gt; RetrievePermIdResult(string id)

[EARLY ACCESS] RetrievePermIdResult: Retrieve PermId results from a previous query.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
var id = "id_example";  // string
List<PermIdData> result = apiInstance.RetrievePermIdResult(id);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **id** | **string** | path | **required** | The execution ID returned by a previous query |

### Return type

[List&lt;PermIdData&gt;](PermIdData.md)

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
<summary>Using the RetrievePermIdResultWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<PermIdData>> response = apiInstance.RetrievePermIdResultWithHttpInfo(id);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="searchopenfigi"></a>
## SearchOpenFigi

> OpenFigiSearchResult SearchOpenFigi(string query, bool usePermId, int? limit = null, string? marketSector = null)

[EARLY ACCESS] SearchOpenFigi: Search OpenFigi for instruments that match the specified terms.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
var query = "query_example";  // string
var usePermId = false;  // bool
var limit = 25;  // int? (optional)
var marketSector = "\"All\"";  // string? (optional)
OpenFigiSearchResult result = apiInstance.SearchOpenFigi(query, usePermId, limit, marketSector);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **query** | **string** | query | **required** |  |
| **usePermId** | **bool** | query | **required** | Should also search PermId for additional information, defaults to &#x60;false&#x60;. Default: `false` |
| **limit** | **int?** | query | optional | Only affects results rom OpenFigi general text search Default: `25` |
| **marketSector** | **string?** | query | optional | The market sector to search, defaults to &#x60;All&#x60;. Default: `&quot;All&quot;` |

### Return type

[OpenFigiSearchResult](OpenFigiSearchResult.md)

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
<summary>Using the SearchOpenFigiWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<OpenFigiSearchResult> response = apiInstance.SearchOpenFigiWithHttpInfo(query, usePermId, limit, marketSector);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="vendors"></a>
## Vendors

> List&lt;VendorProduct&gt; Vendors(string marketSector, string securityType, string generalSecurityType)

[EARLY ACCESS] Vendors: Gets the VendorProducts of any supported and licenced integrations for a given market sector and security type.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InstrumentApi>();
var marketSector = "marketSector_example";  // string
var securityType = "securityType_example";  // string
var generalSecurityType = "generalSecurityType_example";  // string
List<VendorProduct> result = apiInstance.Vendors(marketSector, securityType, generalSecurityType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **marketSector** | **string** | query | **required** |  |
| **securityType** | **string** | query | **required** |  |
| **generalSecurityType** | **string** | query | **required** |  |

### Return type

[List&lt;VendorProduct&gt;](VendorProduct.md)

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
<summary>Using the VendorsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<VendorProduct>> response = apiInstance.VendorsWithHttpInfo(marketSector, securityType, generalSecurityType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

