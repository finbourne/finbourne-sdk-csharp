# Finbourne.Sdk.Lusid.Api.CollateralAgreementsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateCollateralAgreement**](#createcollateralagreement) | **POST** `/api/api/collateralagreements/{scope}` | [EXPERIMENTAL] CreateCollateralAgreement: Create a Collateral Agreement. |
| [**DeleteCollateralAgreement**](#deletecollateralagreement) | **DELETE** `/api/api/collateralagreements/{scope}/{code}` | [EXPERIMENTAL] DeleteCollateralAgreement: Delete a Collateral Agreement. |
| [**GetCollateralAgreement**](#getcollateralagreement) | **GET** `/api/api/collateralagreements/{scope}/{code}` | [EXPERIMENTAL] GetCollateralAgreement: Get a Collateral Agreement. |
| [**GetCollateralAgreementApplicability**](#getcollateralagreementapplicability) | **GET** `/api/api/collateralagreements/{scope}/{code}/$applicability` | [EXPERIMENTAL] GetCollateralAgreementApplicability: Preview the portfolios a Collateral Agreement covers. |
| [**ListCollateralAgreements**](#listcollateralagreements) | **GET** `/api/api/collateralagreements` | [EXPERIMENTAL] ListCollateralAgreements: List Collateral Agreements. |
| [**UpsertCollateralAgreement**](#upsertcollateralagreement) | **PUT** `/api/api/collateralagreements/{scope}/{code}` | [EXPERIMENTAL] UpsertCollateralAgreement: Upsert a Collateral Agreement. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CollateralAgreementsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
```

---

<a id="createcollateralagreement"></a>
## CreateCollateralAgreement

> CollateralAgreement CreateCollateralAgreement(string scope, CollateralAgreementRequest collateralAgreementRequest)

[EXPERIMENTAL] CreateCollateralAgreement: Create a Collateral Agreement.

Create a new Collateral Agreement. The scope of the agreement is in the route and its code is in the request body.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
var scope = "scope_example";  // string
var collateralAgreementRequest = new CollateralAgreementRequest(); // CollateralAgreementRequest
CollateralAgreement result = apiInstance.CreateCollateralAgreement(scope, collateralAgreementRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Collateral Agreement. |
| **collateralAgreementRequest** | [CollateralAgreementRequest](../Model/CollateralAgreementRequest.md) | body | **required** | The definition of the Collateral Agreement. |

### Return type

[CollateralAgreement](../Model/CollateralAgreement.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Collateral Agreement. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCollateralAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CollateralAgreement> response = apiInstance.CreateCollateralAgreementWithHttpInfo(scope, collateralAgreementRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecollateralagreement"></a>
## DeleteCollateralAgreement

> DeletedEntityResponse DeleteCollateralAgreement(string scope, string code, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteCollateralAgreement: Delete a Collateral Agreement.

Delete a Collateral Agreement from the given effective datetime. It remains retrievable at earlier effective datetimes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteCollateralAgreement(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Collateral Agreement to be deleted. |
| **code** | **string** | path | **required** | The code of the Collateral Agreement to be deleted. Together with the scope this uniquely identifies the Collateral Agreement. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the Collateral Agreement is deleted. Defaults to the current LUSID system datetime if not specified. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Collateral Agreement was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCollateralAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCollateralAgreementWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcollateralagreement"></a>
## GetCollateralAgreement

> CollateralAgreement GetCollateralAgreement(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetCollateralAgreement: Get a Collateral Agreement.

Retrieve the definition of a particular Collateral Agreement at an effective and asAt datetime.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
CollateralAgreement result = apiInstance.GetCollateralAgreement(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Collateral Agreement. |
| **code** | **string** | path | **required** | The code of the Collateral Agreement. Together with the scope this uniquely identifies the Collateral Agreement. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Collateral Agreement. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Collateral Agreement. Defaults to returning the latest version if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the &#39;CollateralAgreement&#39; domain to decorate onto the Collateral Agreement.              These must take the format {domain}/{scope}/{code}, for example &#39;CollateralAgreement/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[CollateralAgreement](../Model/CollateralAgreement.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Collateral Agreement. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCollateralAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CollateralAgreement> response = apiInstance.GetCollateralAgreementWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcollateralagreementapplicability"></a>
## GetCollateralAgreementApplicability

> CollateralAgreementApplicability GetCollateralAgreementApplicability(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, int? limit = null)

[EXPERIMENTAL] GetCollateralAgreementApplicability: Preview the portfolios a Collateral Agreement covers.

Evaluate the applicability filter of a Collateral Agreement against portfolios, using the same filter syntax as  listing portfolios, and return the portfolios it selects.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
CollateralAgreementApplicability result = apiInstance.GetCollateralAgreementApplicability(scope, code, effectiveAt, asAt, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Collateral Agreement. |
| **code** | **string** | path | **required** | The code of the Collateral Agreement. Together with the scope this uniquely identifies the Collateral Agreement. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to evaluate the agreement and portfolios. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to evaluate the agreement and portfolios. Defaults to returning the latest version if not specified. |
| **limit** | **int?** | query | optional | The maximum number of portfolios to return. Defaults to 100 if not specified. |

### Return type

[CollateralAgreementApplicability](../Model/CollateralAgreementApplicability.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The portfolios the Collateral Agreement covers. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCollateralAgreementApplicabilityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CollateralAgreementApplicability> response = apiInstance.GetCollateralAgreementApplicabilityWithHttpInfo(scope, code, effectiveAt, asAt, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcollateralagreements"></a>
## ListCollateralAgreements

> PagedResourceListOfCollateralAgreement ListCollateralAgreements(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListCollateralAgreements: List Collateral Agreements.

List all the Collateral Agreements matching the given criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfCollateralAgreement result = apiInstance.ListCollateralAgreements(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Collateral Agreements. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list Collateral Agreements. Defaults to returning the latest version of each Collateral Agreement if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Collateral Agreements; this value is returned from the previous call. If a pagination token is provided, the filter and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. The filterable fields are Id.Scope, Id.Code, BaseCurrency, CounterpartyId.Code, CounterpartyId.IdTypeScope, CounterpartyId.IdTypeCode, ApplicabilityFilter, CutLabel, RecipeId.Scope, RecipeId.Code, MinimumTransferAmount, MatchTolerance, Rounding.Amount, Rounding.Deliveries, Rounding.Returns, SettlementLag.Cash, SettlementLag.Securities, Properties and Version. The margin items can be filtered with a single-condition any expression on either VariationMargin or InitialMargin over Code or Calculation.Method. For example, to filter on the counterparty code, specify \&quot;CounterpartyId.Code eq &#39;Acme&#39;\&quot;, and to find agreements with a variation margin item, specify \&quot;VariationMargin any (Code eq &#39;VM1&#39;)\&quot;. For more information about filtering results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the &#39;CollateralAgreement&#39; domain to decorate onto each Collateral Agreement.              These must take the format {domain}/{scope}/{code}, for example &#39;CollateralAgreement/Manager/Id&#39;. |

### Return type

[PagedResourceListOfCollateralAgreement](../Model/PagedResourceListOfCollateralAgreement.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Collateral Agreements. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCollateralAgreementsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCollateralAgreement> response = apiInstance.ListCollateralAgreementsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcollateralagreement"></a>
## UpsertCollateralAgreement

> CollateralAgreement UpsertCollateralAgreement(string scope, string code, UpsertCollateralAgreementRequest upsertCollateralAgreementRequest)

[EXPERIMENTAL] UpsertCollateralAgreement: Upsert a Collateral Agreement.

Create or replace the full definition of a Collateral Agreement from an effective datetime. A change to the  definition becomes a new bitemporal version: the agreement as it was declared at earlier effective datetimes,  and as of earlier asAt datetimes, remains retrievable.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CollateralAgreementsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertCollateralAgreementRequest = new UpsertCollateralAgreementRequest(); // UpsertCollateralAgreementRequest
CollateralAgreement result = apiInstance.UpsertCollateralAgreement(scope, code, upsertCollateralAgreementRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Collateral Agreement. |
| **code** | **string** | path | **required** | The code of the Collateral Agreement. Together with the scope this uniquely identifies the Collateral Agreement. |
| **upsertCollateralAgreementRequest** | [UpsertCollateralAgreementRequest](../Model/UpsertCollateralAgreementRequest.md) | body | **required** | The full definition of the Collateral Agreement from the effective datetime in the request, or the current LUSID system datetime if not specified. |

### Return type

[CollateralAgreement](../Model/CollateralAgreement.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Collateral Agreement as it stands from the effective datetime. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCollateralAgreementWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CollateralAgreement> response = apiInstance.UpsertCollateralAgreementWithHttpInfo(scope, code, upsertCollateralAgreementRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

