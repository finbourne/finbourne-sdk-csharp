# Finbourne.Sdk.Lusid.Api.WithholdingTaxApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWithholdingTaxDatasetDefinitions**](#createwithholdingtaxdatasetdefinitions) | **POST** `/api/api/withholdingtax/datasetdefinitions` | [EARLY ACCESS] CreateWithholdingTaxDatasetDefinitions: Create the Withholding Tax dataset definitions. |
| [**DeleteWithholdingTaxConfiguration**](#deletewithholdingtaxconfiguration) | **DELETE** `/api/api/withholdingtax/configurations/{scope}/{code}` | [EARLY ACCESS] DeleteWithholdingTaxConfiguration: Delete a Withholding Tax Configuration. |
| [**DeleteWithholdingTaxDatasetDefinition**](#deletewithholdingtaxdatasetdefinition) | **DELETE** `/api/api/withholdingtax/datasetdefinitions/{scope}/{code}` | [EARLY ACCESS] DeleteWithholdingTaxDatasetDefinition: Delete a Withholding Tax dataset definition. |
| [**GetWithholdingTaxConfiguration**](#getwithholdingtaxconfiguration) | **GET** `/api/api/withholdingtax/configurations/{scope}/{code}` | [EARLY ACCESS] GetWithholdingTaxConfiguration: Get a Withholding Tax Configuration. |
| [**GetWithholdingTaxDatasetDefinition**](#getwithholdingtaxdatasetdefinition) | **GET** `/api/api/withholdingtax/datasetdefinitions/{scope}/{code}` | [EARLY ACCESS] GetWithholdingTaxDatasetDefinition: Get a Withholding Tax dataset definition. |
| [**ListWithholdingTaxConfigurations**](#listwithholdingtaxconfigurations) | **GET** `/api/api/withholdingtax/configurations` | [EARLY ACCESS] ListWithholdingTaxConfigurations: List Withholding Tax Configurations. |
| [**ListWithholdingTaxDatasetDefinitions**](#listwithholdingtaxdatasetdefinitions) | **GET** `/api/api/withholdingtax/datasetdefinitions` | [EARLY ACCESS] ListWithholdingTaxDatasetDefinitions: List Withholding Tax dataset definitions. |
| [**PatchWithholdingTaxDatasetDefinition**](#patchwithholdingtaxdatasetdefinition) | **PATCH** `/api/api/withholdingtax/datasetdefinitions/{scope}/{code}` | [EARLY ACCESS] PatchWithholdingTaxDatasetDefinition: Patch a Withholding Tax dataset definition. |
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

<a id="createwithholdingtaxdatasetdefinitions"></a>
## CreateWithholdingTaxDatasetDefinitions

> WithholdingTaxDatasetDefinitions CreateWithholdingTaxDatasetDefinitions(CreateWithholdingTaxDatasetDefinitionsRequest createWithholdingTaxDatasetDefinitionsRequest)

[EARLY ACCESS] CreateWithholdingTaxDatasetDefinitions: Create the Withholding Tax dataset definitions.

Create the anomaly and the main relational dataset definition for a customer domain, in a single call.                The definitions are constructed rather than accepted as given, so the fields the engine reads by name cannot  be absent, misspelled or created in the wrong field category. LUSID adds the mandatory core to both: taxCountry  and profileType as series identifiers, countryRate, treatyRate, betterRate and enhancedRate as value fields,  treatyRAS, betterRAS and enhancedRAS as value fields, and rank as a value field on the anomaly definition only.                The caller supplies only their own matching dimensions, given per dataset. The two schemas need not be  identical: a dimension present on only one dataset is simply not matched on when the other is queried, an ISIN  dimension on the anomaly dataset alone being the usual case. The request is rejected if it names a dimension  that collides with a mandatory core field, or if it omits a scope or a code.

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
| **filter** | **string?** | query | optional | Expression to filter the results. For example, to filter on the scope, specify              \&quot;scope eq &#39;WithholdingTax&#39;\&quot;, and to filter on the code, specify \&quot;code eq &#39;wht-main-rates&#39;\&quot;. For more              information about filtering results, see              https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
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

Amend one Withholding Tax relational dataset definition, adding a matching dimension being the common case.  Subject to the platform's own rules on what may be changed on a populated dataset.                Only the matching dimensions the document addresses are affected; a dimension it does not address is left as  it is. Append a dimension with an add on \"/dimensions/-\", and amend one in place with an add on its index.                A dimension whose name collides with a mandatory core field is rejected, as is any attempt to add a rate tier:  the tier set is fixed at four and cannot be extended by schema evolution, because the engine could never read  a tier it does not know by name. The mandatory core is not addressable by this endpoint at all.                The amended dataset is returned in the same shape the get and the list return: the matching dimensions alone.  Read the full field schema from the relational dataset definition at the returned href.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: Dimensions.

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

