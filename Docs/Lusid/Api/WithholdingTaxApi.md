# Finbourne.Sdk.Lusid.Api.WithholdingTaxApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchDeleteWithholdingTaxRates**](#batchdeletewithholdingtaxrates) | **POST** `/api/api/withholdingtax/rates/{scope}/{code}/$batchDelete` | [EARLY ACCESS] BatchDeleteWithholdingTaxRates: Batch delete Withholding Tax rate rows from a rate dataset. |
| [**BatchUpsertWithholdingTaxRates**](#batchupsertwithholdingtaxrates) | **POST** `/api/api/withholdingtax/rates/{scope}/{code}/$batchUpsert` | [EARLY ACCESS] BatchUpsertWithholdingTaxRates: Batch upsert Withholding Tax rate rows, applying the write-time gates before any row lands. |
| [**CreateWithholdingTaxDatasetDefinitions**](#createwithholdingtaxdatasetdefinitions) | **POST** `/api/api/withholdingtax/datasetdefinitions` | [EARLY ACCESS] CreateWithholdingTaxDatasetDefinitions: Create the Withholding Tax dataset definitions. |
| [**DeleteWithholdingTaxConfiguration**](#deletewithholdingtaxconfiguration) | **DELETE** `/api/api/withholdingtax/configurations/{scope}/{code}` | [EARLY ACCESS] DeleteWithholdingTaxConfiguration: Delete a Withholding Tax Configuration. |
| [**DeleteWithholdingTaxDatasetDefinition**](#deletewithholdingtaxdatasetdefinition) | **DELETE** `/api/api/withholdingtax/datasetdefinitions/{scope}/{code}` | [EARLY ACCESS] DeleteWithholdingTaxDatasetDefinition: Delete a Withholding Tax dataset definition. |
| [**GetWithholdingTaxConfiguration**](#getwithholdingtaxconfiguration) | **GET** `/api/api/withholdingtax/configurations/{scope}/{code}` | [EARLY ACCESS] GetWithholdingTaxConfiguration: Get a Withholding Tax Configuration. |
| [**GetWithholdingTaxDatasetDefinition**](#getwithholdingtaxdatasetdefinition) | **GET** `/api/api/withholdingtax/datasetdefinitions/{scope}/{code}` | [EARLY ACCESS] GetWithholdingTaxDatasetDefinition: Get a Withholding Tax dataset definition. |
| [**ListWithholdingTaxConfigurations**](#listwithholdingtaxconfigurations) | **GET** `/api/api/withholdingtax/configurations` | [EARLY ACCESS] ListWithholdingTaxConfigurations: List Withholding Tax Configurations. |
| [**ListWithholdingTaxDatasetDefinitions**](#listwithholdingtaxdatasetdefinitions) | **GET** `/api/api/withholdingtax/datasetdefinitions` | [EARLY ACCESS] ListWithholdingTaxDatasetDefinitions: List Withholding Tax dataset definitions. |
| [**PatchWithholdingTaxDatasetDefinition**](#patchwithholdingtaxdatasetdefinition) | **PATCH** `/api/api/withholdingtax/datasetdefinitions/{scope}/{code}` | [EARLY ACCESS] PatchWithholdingTaxDatasetDefinition: Patch a Withholding Tax dataset definition. |
| [**ResolveWithholdingTax**](#resolvewithholdingtax) | **POST** `/api/api/withholdingtax/$resolve` | [EARLY ACCESS] ResolveWithholdingTax: Resolve the Withholding Tax rate that booking would apply. |
| [**UpsertWithholdingTaxConfiguration**](#upsertwithholdingtaxconfiguration) | **POST** `/api/api/withholdingtax/configurations/{scope}/{code}` | [EARLY ACCESS] UpsertWithholdingTaxConfiguration: Upsert a Withholding Tax Configuration. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<WithholdingTaxApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
```

---

<a id="batchdeletewithholdingtaxrates"></a>
## BatchDeleteWithholdingTaxRates

> BatchDeleteRelationalDataResponse BatchDeleteWithholdingTaxRates(string scope, string code, Dictionary<string, DeleteWithholdingTaxRateRequest> requestBody, string? successMode = null, string? ruleSource = null)

[EARLY ACCESS] BatchDeleteWithholdingTaxRates: Batch delete Withholding Tax rate rows from a rate dataset.

Also how a rate with no replacement is expired, there being no effectiveTo field. Deletes are  bitemporal, so rows stay readable at a prior asAt.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, DeleteWithholdingTaxRateRequest>(); // Dictionary<string, DeleteWithholdingTaxRateRequest>
var successMode = "\"Atomic\"";  // string? (optional)
var ruleSource = "ruleSource_example";  // string? (optional)
BatchDeleteRelationalDataResponse result = apiInstance.BatchDeleteWithholdingTaxRates(scope, code, requestBody, successMode, ruleSource);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The Scope of the rate dataset&#39;s relational dataset definition. |
| **code** | **string** | path | **required** | The Code of the rate dataset&#39;s relational dataset definition. |
| **requestBody** | [Dictionary&lt;string, DeleteWithholdingTaxRateRequest&gt;](../Model/DeleteWithholdingTaxRateRequest.md) | body | **required** | The rate rows to delete, keyed by a correlation id echoed back in the response. |
| **successMode** | **string?** | query | optional | Atomic or Partial; defaults to Atomic. In Partial mode failures are returned              in the response body with a 200 status. Default: `&quot;Atomic&quot;` |
| **ruleSource** | **string?** | query | optional | The source of the rows to delete, since it is part of each row&#39;s identity. Omit it              to delete rows that apply at every source; a source&#39;s rows are only deleted when it is given. A row may not              carry ruleSource in its own series identifiers. |

### Return type

[BatchDeleteRelationalDataResponse](../Model/BatchDeleteRelationalDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted rate row metadata. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchDeleteWithholdingTaxRatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchDeleteRelationalDataResponse> response = apiInstance.BatchDeleteWithholdingTaxRatesWithHttpInfo(scope, code, requestBody, successMode, ruleSource);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="batchupsertwithholdingtaxrates"></a>
## BatchUpsertWithholdingTaxRates

> BatchUpsertWithholdingTaxRatesResponse BatchUpsertWithholdingTaxRates(string scope, string code, Dictionary<string, UpsertWithholdingTaxRateRequest> requestBody, string? successMode = null, string? ruleSource = null)

[EARLY ACCESS] BatchUpsertWithholdingTaxRates: Batch upsert Withholding Tax rate rows, applying the write-time gates before any row lands.

Row identity is the series identifiers plus effectiveAt; a rate is superseded by loading a row with a  later effectiveAt for the same series identifiers. One batch carries one rule source, so a feed mixing rows  from a source with rows that apply at every source is loaded in two calls.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, UpsertWithholdingTaxRateRequest>(); // Dictionary<string, UpsertWithholdingTaxRateRequest>
var successMode = "\"Atomic\"";  // string? (optional)
var ruleSource = "ruleSource_example";  // string? (optional)
BatchUpsertWithholdingTaxRatesResponse result = apiInstance.BatchUpsertWithholdingTaxRates(scope, code, requestBody, successMode, ruleSource);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The Scope of the rate dataset&#39;s relational dataset definition. |
| **code** | **string** | path | **required** | The Code of the rate dataset&#39;s relational dataset definition. |
| **requestBody** | [Dictionary&lt;string, UpsertWithholdingTaxRateRequest&gt;](../Model/UpsertWithholdingTaxRateRequest.md) | body | **required** | The rate rows to upsert, keyed by a correlation id echoed back in the response. |
| **successMode** | **string?** | query | optional | Atomic or Partial; defaults to Atomic, because a partly loaded feed silently              under-withholds. In Partial mode failures are returned in the response body with a 200 status. Default: `&quot;Atomic&quot;` |
| **ruleSource** | **string?** | query | optional | The source every row in the batch is attributed to, compared against the              configuration&#39;s source priority. Omit it for rows that apply at every source. A row may not carry ruleSource              in its own series identifiers. |

### Return type

[BatchUpsertWithholdingTaxRatesResponse](../Model/BatchUpsertWithholdingTaxRatesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Withholding Tax rate rows that were upserted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchUpsertWithholdingTaxRatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertWithholdingTaxRatesResponse> response = apiInstance.BatchUpsertWithholdingTaxRatesWithHttpInfo(scope, code, requestBody, successMode, ruleSource);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createwithholdingtaxdatasetdefinitions"></a>
## CreateWithholdingTaxDatasetDefinitions

> WithholdingTaxDatasetDefinitions CreateWithholdingTaxDatasetDefinitions(CreateWithholdingTaxDatasetDefinitionsRequest createWithholdingTaxDatasetDefinitionsRequest)

[EARLY ACCESS] CreateWithholdingTaxDatasetDefinitions: Create the Withholding Tax dataset definitions.

Create the anomaly and the main relational dataset definition for a customer domain, in a single call.                The definitions are constructed rather than accepted as given, so the fields the engine reads by name cannot  be absent, misspelled or created in the wrong field category. LUSID adds the mandatory core to both: taxCountry,  profileType and ruleSource as series identifiers (ruleSource optional), countryRate, treatyRate, betterRate and  enhancedRate as value fields, treatyRAS, betterRAS and enhancedRAS as value fields, and rank as a value field on  the anomaly definition only.                The caller supplies only their own matching dimensions, given per dataset. The two schemas need not be  identical: a dimension present on only one dataset is simply not matched on when the other is queried, an ISIN  dimension on the anomaly dataset alone being the usual case. The request is rejected if it names a dimension  that collides with a mandatory core field, or if it omits a scope or a code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var createWithholdingTaxDatasetDefinitionsRequest = new CreateWithholdingTaxDatasetDefinitionsRequest(); // CreateWithholdingTaxDatasetDefinitionsRequest
WithholdingTaxDatasetDefinitions result = apiInstance.CreateWithholdingTaxDatasetDefinitions(createWithholdingTaxDatasetDefinitionsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createWithholdingTaxDatasetDefinitionsRequest** | [CreateWithholdingTaxDatasetDefinitionsRequest](../Model/CreateWithholdingTaxDatasetDefinitionsRequest.md) | body | **required** | The scope, code and matching dimensions of each of the two datasets to create. |

### Return type

[WithholdingTaxDatasetDefinitions](../Model/WithholdingTaxDatasetDefinitions.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created anomaly and main relational dataset definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateWithholdingTaxDatasetDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WithholdingTaxDatasetDefinitions> response = apiInstance.CreateWithholdingTaxDatasetDefinitionsWithHttpInfo(createWithholdingTaxDatasetDefinitionsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletewithholdingtaxconfiguration"></a>
## DeleteWithholdingTaxConfiguration

> DeletedEntityResponse DeleteWithholdingTaxConfiguration(string scope, string code)

[EARLY ACCESS] DeleteWithholdingTaxConfiguration: Delete a Withholding Tax Configuration.

Delete the Withholding Tax Configuration at the given scope and code. Rejected if a portfolio, fund or share  class still references the configuration, rather than orphaning those references.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteWithholdingTaxConfiguration(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Withholding Tax Configuration to be deleted. |
| **code** | **string** | path | **required** | The code of the Withholding Tax Configuration to be deleted. Together with the scope this uniquely identifies the configuration. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Withholding Tax Configuration was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteWithholdingTaxConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteWithholdingTaxConfigurationWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletewithholdingtaxdatasetdefinition"></a>
## DeleteWithholdingTaxDatasetDefinition

> DeletedEntityResponse DeleteWithholdingTaxDatasetDefinition(string scope, string code)

[EARLY ACCESS] DeleteWithholdingTaxDatasetDefinition: Delete a Withholding Tax dataset definition.

Delete one Withholding Tax relational dataset definition, subject to the platform's own rules on what may be  changed on a populated dataset.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteWithholdingTaxDatasetDefinition(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the dataset definition to be deleted. |
| **code** | **string** | path | **required** | The code of the dataset definition to be deleted. Together with the scope this uniquely identifies the definition. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the relational dataset definition was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteWithholdingTaxDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteWithholdingTaxDatasetDefinitionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getwithholdingtaxconfiguration"></a>
## GetWithholdingTaxConfiguration

> WithholdingTaxConfiguration GetWithholdingTaxConfiguration(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetWithholdingTaxConfiguration: Get a Withholding Tax Configuration.

Retrieve a single Withholding Tax Configuration by scope and code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
WithholdingTaxConfiguration result = apiInstance.GetWithholdingTaxConfiguration(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Withholding Tax Configuration. |
| **code** | **string** | path | **required** | The code of the Withholding Tax Configuration. Together with the scope this uniquely identifies the configuration. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Withholding Tax Configuration. Defaults to returning the latest version if not specified. |

### Return type

[WithholdingTaxConfiguration](../Model/WithholdingTaxConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Withholding Tax Configuration. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetWithholdingTaxConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WithholdingTaxConfiguration> response = apiInstance.GetWithholdingTaxConfigurationWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getwithholdingtaxdatasetdefinition"></a>
## GetWithholdingTaxDatasetDefinition

> WithholdingTaxDataset GetWithholdingTaxDatasetDefinition(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetWithholdingTaxDatasetDefinition: Get a Withholding Tax dataset definition.

Retrieve one Withholding Tax dataset definition by scope and code, in the same shape the create returns: the  matching dimensions the caller supplied. The mandatory core is not returned here; read the full field schema  from the relational dataset definition at the returned href.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
WithholdingTaxDataset result = apiInstance.GetWithholdingTaxDatasetDefinition(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the dataset definition. |
| **code** | **string** | path | **required** | The code of the dataset definition. Together with the scope this uniquely identifies the definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the dataset definition. Defaults to returning the latest version if not specified. |

### Return type

[WithholdingTaxDataset](../Model/WithholdingTaxDataset.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Withholding Tax dataset definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetWithholdingTaxDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WithholdingTaxDataset> response = apiInstance.GetWithholdingTaxDatasetDefinitionWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listwithholdingtaxconfigurations"></a>
## ListWithholdingTaxConfigurations

> PagedResourceListOfWithholdingTaxConfiguration ListWithholdingTaxConfigurations(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EARLY ACCESS] ListWithholdingTaxConfigurations: List Withholding Tax Configurations.

List the Withholding Tax Configurations across every scope the caller is entitled to. To list the  configurations of a single scope, filter on the scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfWithholdingTaxConfiguration result = apiInstance.ListWithholdingTaxConfigurations(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Withholding Tax Configurations. Defaults to returning the latest version of each configuration if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Withholding Tax Configurations; this value is              returned from the previous call. If a pagination token is provided, the filter and asAt fields must not have              changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the scope, specify              \&quot;id.Scope eq &#39;WithholdingTax&#39;\&quot;, and to filter on the code, specify \&quot;id.Code eq &#39;UK-LIFE-BLAGAB&#39;\&quot;. For more              information about filtering results, see              https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfWithholdingTaxConfiguration](../Model/PagedResourceListOfWithholdingTaxConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Withholding Tax Configurations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListWithholdingTaxConfigurationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfWithholdingTaxConfiguration> response = apiInstance.ListWithholdingTaxConfigurationsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listwithholdingtaxdatasetdefinitions"></a>
## ListWithholdingTaxDatasetDefinitions

> PagedResourceListOfWithholdingTaxDataset ListWithholdingTaxDatasetDefinitions(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EARLY ACCESS] ListWithholdingTaxDatasetDefinitions: List Withholding Tax dataset definitions.

List the Withholding Tax dataset definitions across every scope the caller is entitled to, each in the same  shape the create returns. To list the definitions of a single scope, filter on the scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfWithholdingTaxDataset result = apiInstance.ListWithholdingTaxDatasetDefinitions(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the dataset definitions. Defaults to returning the latest version of each definition if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing dataset definitions; this value is returned              from the previous call. If a pagination token is provided, the filter and asAt fields must not have changed              since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the scope, specify              \&quot;scope eq &#39;WithholdingTax&#39;\&quot;, to filter on the code, specify \&quot;code eq &#39;wht-main-rates&#39;\&quot;, and to filter on the              dataset type, specify \&quot;datasetType eq &#39;Anomaly&#39;\&quot;. For more information about filtering results, see              https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfWithholdingTaxDataset](../Model/PagedResourceListOfWithholdingTaxDataset.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Withholding Tax dataset definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListWithholdingTaxDatasetDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfWithholdingTaxDataset> response = apiInstance.ListWithholdingTaxDatasetDefinitionsWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchwithholdingtaxdatasetdefinition"></a>
## PatchWithholdingTaxDatasetDefinition

> WithholdingTaxDataset PatchWithholdingTaxDatasetDefinition(string scope, string code, List<Operation> operation)

[EARLY ACCESS] PatchWithholdingTaxDatasetDefinition: Patch a Withholding Tax dataset definition.

Amend one Withholding Tax relational dataset definition, adding a matching dimension being the common case.  Subject to the platform's own rules on what may be changed on a populated dataset.                Only the matching dimensions the document addresses are affected; a dimension it does not address is left as  it is. Append a dimension with an add on \"/dimensions/-\", insert one at a position with an add on its index,  and remove one with a remove on its index. To amend a dimension, remove it and add it again.                A dimension whose name collides with a mandatory core field is rejected, as is any attempt to add a rate tier:  the tier set is fixed at four and cannot be extended by schema evolution, because the engine could never read  a tier it does not know by name. The mandatory core is not addressable by this endpoint at all.                The amended dataset is returned in the same shape the get and the list return: the matching dimensions alone.  Read the full field schema from the relational dataset definition at the returned href.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: Dimensions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
WithholdingTaxDataset result = apiInstance.PatchWithholdingTaxDatasetDefinition(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the dataset definition to amend. |
| **code** | **string** | path | **required** | The code of the dataset definition to amend. Together with the scope this uniquely identifies the definition. |
| **operation** | [List&lt;Operation&gt;](../Model/Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[WithholdingTaxDataset](../Model/WithholdingTaxDataset.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The amended Withholding Tax dataset. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchWithholdingTaxDatasetDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WithholdingTaxDataset> response = apiInstance.PatchWithholdingTaxDatasetDefinitionWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="resolvewithholdingtax"></a>
## ResolveWithholdingTax

> WithholdingTaxResolution ResolveWithholdingTax(ResolveWithholdingTaxRequest resolveWithholdingTaxRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, int? limit = null)

[EARLY ACCESS] ResolveWithholdingTax: Resolve the Withholding Tax rate that booking would apply.

A read-only lookup that runs the same resolution as booking, without a transaction: it works down the source  priority and, at each source, checks the anomaly dataset before the main dataset. Nothing is booked, and only  rates are returned. Supply a Withholding Tax Configuration to predict what booking will post; replace its  datasets or source priority to ask what would resolve instead. Supply the dimension values directly, or name an  instrument so that the configuration's value sources read them from it, as booking reads a transaction's instrument.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var resolveWithholdingTaxRequest = new ResolveWithholdingTaxRequest(); // ResolveWithholdingTaxRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 100;  // int? (optional)
WithholdingTaxResolution result = apiInstance.ResolveWithholdingTax(resolveWithholdingTaxRequest, effectiveAt, asAt, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **resolveWithholdingTaxRequest** | [ResolveWithholdingTaxRequest](../Model/ResolveWithholdingTaxRequest.md) | body | **required** | The tax identity, the dimension values or the instrument, and the configuration or datasets to resolve against. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to resolve, in place of the transaction&#39;s trade              date. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to read the configuration and the rates. Defaults to the latest version              if not specified. |
| **limit** | **int?** | query | optional | The most combinations of values that couldAlsoMatch tries, fewest values first. Default: `100` |

### Return type

[WithholdingTaxResolution](../Model/WithholdingTaxResolution.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Withholding Tax rate that booking would apply. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ResolveWithholdingTaxWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WithholdingTaxResolution> response = apiInstance.ResolveWithholdingTaxWithHttpInfo(resolveWithholdingTaxRequest, effectiveAt, asAt, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertwithholdingtaxconfiguration"></a>
## UpsertWithholdingTaxConfiguration

> WithholdingTaxConfiguration UpsertWithholdingTaxConfiguration(string scope, string code, UpsertWithholdingTaxConfigurationRequest upsertWithholdingTaxConfigurationRequest)

[EARLY ACCESS] UpsertWithholdingTaxConfiguration: Upsert a Withholding Tax Configuration.

Create or replace the Withholding Tax Configuration at the given scope and code. The write is a full replace  on the object rather than a partial update, so the request must carry the complete configuration.                The write is rejected if either referenced dataset does not exist, if either is missing a mandatory core field  or has one in the wrong field category, if any customer-defined dimension in either dataset has no value source  declaration, or if a declaration names a dimension neither dataset has. Errors name the specific field.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<WithholdingTaxApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertWithholdingTaxConfigurationRequest = new UpsertWithholdingTaxConfigurationRequest(); // UpsertWithholdingTaxConfigurationRequest
WithholdingTaxConfiguration result = apiInstance.UpsertWithholdingTaxConfiguration(scope, code, upsertWithholdingTaxConfigurationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Withholding Tax Configuration. |
| **code** | **string** | path | **required** | The code of the Withholding Tax Configuration. Together with the scope this uniquely identifies the configuration. |
| **upsertWithholdingTaxConfigurationRequest** | [UpsertWithholdingTaxConfigurationRequest](../Model/UpsertWithholdingTaxConfigurationRequest.md) | body | **required** | The complete Withholding Tax Configuration to create or replace. |

### Return type

[WithholdingTaxConfiguration](../Model/WithholdingTaxConfiguration.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The created or replaced Withholding Tax Configuration. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertWithholdingTaxConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<WithholdingTaxConfiguration> response = apiInstance.UpsertWithholdingTaxConfigurationWithHttpInfo(scope, code, upsertWithholdingTaxConfigurationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

