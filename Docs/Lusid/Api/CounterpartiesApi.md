# Finbourne.Sdk.Lusid.Api.CounterpartiesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteCounterpartyAgreement**](#deletecounterpartyagreement) | **DELETE** `/api/api/counterparties/counterpartyagreements/{scope}/{code}` | [EARLY ACCESS] DeleteCounterpartyAgreement: Delete the Counterparty Agreement of given scope and code |
| [**DeleteCreditSupportAnnex**](#deletecreditsupportannex) | **DELETE** `/api/api/counterparties/creditsupportannexes/{scope}/{code}` | [EARLY ACCESS] DeleteCreditSupportAnnex: Delete the Credit Support Annex of given scope and code |
| [**GetCounterpartyAgreement**](#getcounterpartyagreement) | **GET** `/api/api/counterparties/counterpartyagreements/{scope}/{code}` | [EARLY ACCESS] GetCounterpartyAgreement: Get Counterparty Agreement |
| [**GetCreditSupportAnnex**](#getcreditsupportannex) | **GET** `/api/api/counterparties/creditsupportannexes/{scope}/{code}` | [EARLY ACCESS] GetCreditSupportAnnex: Get Credit Support Annex |
| [**ListCounterpartyAgreements**](#listcounterpartyagreements) | **GET** `/api/api/counterparties/counterpartyagreements` | [EARLY ACCESS] ListCounterpartyAgreements: List the set of Counterparty Agreements |
| [**ListCreditSupportAnnexes**](#listcreditsupportannexes) | **GET** `/api/api/counterparties/creditsupportannexes` | [EARLY ACCESS] ListCreditSupportAnnexes: List the set of Credit Support Annexes |
| [**UpsertCounterpartyAgreement**](#upsertcounterpartyagreement) | **POST** `/api/api/counterparties/counterpartyagreements` | [EARLY ACCESS] UpsertCounterpartyAgreement: Upsert Counterparty Agreement |
| [**UpsertCreditSupportAnnex**](#upsertcreditsupportannex) | **POST** `/api/api/counterparties/creditsupportannexes` | [EARLY ACCESS] UpsertCreditSupportAnnex: Upsert Credit Support Annex |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CounterpartiesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
```

---

<a id="deletecounterpartyagreement"></a>
## DeleteCounterpartyAgreement

> AnnulSingleStructuredDataResponse DeleteCounterpartyAgreement(string scope, string code)

[EARLY ACCESS] DeleteCounterpartyAgreement: Delete the Counterparty Agreement of given scope and code

Delete the specified Counterparty Agreement from a single scope.  The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.                It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteCounterpartyAgreement(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Counterparty Agreement to delete. |
| **code** | **string** | path | **required** | The Counterparty Agreement to delete. |

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
<summary>Using the DeleteCounterpartyAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteCounterpartyAgreementWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecreditsupportannex"></a>
## DeleteCreditSupportAnnex

> AnnulSingleStructuredDataResponse DeleteCreditSupportAnnex(string scope, string code)

[EARLY ACCESS] DeleteCreditSupportAnnex: Delete the Credit Support Annex of given scope and code

Delete the specified Credit Support Annex from a single scope.  The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.                It is important to always check for any unsuccessful response.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteCreditSupportAnnex(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Credit Support Annex to delete. |
| **code** | **string** | path | **required** | The Credit Support Annex to delete. |

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
<summary>Using the DeleteCreditSupportAnnexWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteCreditSupportAnnexWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcounterpartyagreement"></a>
## GetCounterpartyAgreement

> GetCounterpartyAgreementResponse GetCounterpartyAgreement(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetCounterpartyAgreement: Get Counterparty Agreement

Get a Counterparty Agreement from a single scope.  The response will return either the Counterparty Agreement that has been stored, or a failure explaining why the request was unsuccessful.  It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetCounterpartyAgreementResponse result = apiInstance.GetCounterpartyAgreement(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Counterparty Agreement to retrieve. |
| **code** | **string** | path | **required** | The name of the Counterparty Agreement to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Counterparty Agreement. Defaults to return the latest version if not specified. |

### Return type

[GetCounterpartyAgreementResponse](GetCounterpartyAgreementResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Counterparty Agreement or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCounterpartyAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetCounterpartyAgreementResponse> response = apiInstance.GetCounterpartyAgreementWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcreditsupportannex"></a>
## GetCreditSupportAnnex

> GetCreditSupportAnnexResponse GetCreditSupportAnnex(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetCreditSupportAnnex: Get Credit Support Annex

Get a Credit Support Annex from a single scope.  The response will return either the Credit Support Annex that has been stored, or a failure explaining why the request was unsuccessful.  It is important to always check for any unsuccessful requests (failures).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetCreditSupportAnnexResponse result = apiInstance.GetCreditSupportAnnex(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Credit Support Annex to retrieve. |
| **code** | **string** | path | **required** | The name of the Credit Support Annex to retrieve the data for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Credit Support Annex . Defaults to return the latest version if not specified. |

### Return type

[GetCreditSupportAnnexResponse](GetCreditSupportAnnexResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved credit support annexes or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCreditSupportAnnexWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetCreditSupportAnnexResponse> response = apiInstance.GetCreditSupportAnnexWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcounterpartyagreements"></a>
## ListCounterpartyAgreements

> ResourceListOfGetCounterpartyAgreementResponse ListCounterpartyAgreements(DateTimeOffset? asAt = null)

[EARLY ACCESS] ListCounterpartyAgreements: List the set of Counterparty Agreements

List the set of Counterparty Agreements at the specified AsAt date/time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfGetCounterpartyAgreementResponse result = apiInstance.ListCounterpartyAgreements(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Counterparty Agreements. Defaults to latest if not specified. |

### Return type

[ResourceListOfGetCounterpartyAgreementResponse](ResourceListOfGetCounterpartyAgreementResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Counterparty Agreements |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCounterpartyAgreementsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetCounterpartyAgreementResponse> response = apiInstance.ListCounterpartyAgreementsWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcreditsupportannexes"></a>
## ListCreditSupportAnnexes

> ResourceListOfGetCreditSupportAnnexResponse ListCreditSupportAnnexes(DateTimeOffset? asAt = null)

[EARLY ACCESS] ListCreditSupportAnnexes: List the set of Credit Support Annexes

List the set of Credit Support Annexes at the specified AsAt date/time

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfGetCreditSupportAnnexResponse result = apiInstance.ListCreditSupportAnnexes(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Credit Support Annexes. Defaults to latest if not specified. |

### Return type

[ResourceListOfGetCreditSupportAnnexResponse](ResourceListOfGetCreditSupportAnnexResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Credit Support Annexes |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCreditSupportAnnexesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfGetCreditSupportAnnexResponse> response = apiInstance.ListCreditSupportAnnexesWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcounterpartyagreement"></a>
## UpsertCounterpartyAgreement

> UpsertSingleStructuredDataResponse UpsertCounterpartyAgreement(UpsertCounterpartyAgreementRequest upsertCounterpartyAgreementRequest)

[EARLY ACCESS] UpsertCounterpartyAgreement: Upsert Counterparty Agreement

Update or insert Counterparty Agreement in a single scope. An item will be updated if it already exists and inserted if it does not.                The response will return the successfully updated or inserted Counterparty Agreement or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var upsertCounterpartyAgreementRequest = new UpsertCounterpartyAgreementRequest(); // UpsertCounterpartyAgreementRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertCounterpartyAgreement(upsertCounterpartyAgreementRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertCounterpartyAgreementRequest** | [UpsertCounterpartyAgreementRequest](UpsertCounterpartyAgreementRequest.md) | body | **required** | The Counterparty Agreement to update or insert |

### Return type

[UpsertSingleStructuredDataResponse](UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted Counterparty Agreement or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCounterpartyAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertCounterpartyAgreementWithHttpInfo(upsertCounterpartyAgreementRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcreditsupportannex"></a>
## UpsertCreditSupportAnnex

> UpsertSingleStructuredDataResponse UpsertCreditSupportAnnex(UpsertCreditSupportAnnexRequest upsertCreditSupportAnnexRequest)

[EARLY ACCESS] UpsertCreditSupportAnnex: Upsert Credit Support Annex

Update or insert Credit Support Annex in a single scope. An item will be updated if it already exists and inserted if it does not.                The response will return the successfully updated or inserted Credit Support Annex or failure message if unsuccessful                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CounterpartiesApi>();
var upsertCreditSupportAnnexRequest = new UpsertCreditSupportAnnexRequest(); // UpsertCreditSupportAnnexRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertCreditSupportAnnex(upsertCreditSupportAnnexRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertCreditSupportAnnexRequest** | [UpsertCreditSupportAnnexRequest](UpsertCreditSupportAnnexRequest.md) | body | **required** | The Credit Support Annex to update or insert |

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
<summary>Using the UpsertCreditSupportAnnexWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertCreditSupportAnnexWithHttpInfo(upsertCreditSupportAnnexRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

