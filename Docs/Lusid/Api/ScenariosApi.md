# Finbourne.Sdk.Lusid.Api.ScenariosApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateScenarioFromTemplate**](#createscenariofromtemplate) | **POST** `/api/api/scenarios/{scope}/$fromTemplate` | [EARLY ACCESS] CreateScenarioFromTemplate: [EARLY ACCESS] CreateScenarioFromTemplate: Create a Scenario from a pre-built template. |
| [**DeleteScenario**](#deletescenario) | **DELETE** `/api/api/scenarios/{scope}/{code}` | [EARLY ACCESS] DeleteScenario: Delete a Scenario, assuming that it is present. |
| [**GetScenario**](#getscenario) | **GET** `/api/api/scenarios/{scope}/{code}` | [EARLY ACCESS] GetScenario: Get Scenario |
| [**ListScenarioTemplates**](#listscenariotemplates) | **GET** `/api/api/scenarios/$templates` | [EARLY ACCESS] ListScenarioTemplates: [EARLY ACCESS] ListScenarioTemplates: List the pre-built scenario templates. |
| [**ListScenarioVersions**](#listscenarioversions) | **GET** `/api/api/scenarios/{scope}/{code}/versions` | [EARLY ACCESS] ListScenarioVersions: List the versions of a Scenario |
| [**ListScenarios**](#listscenarios) | **GET** `/api/api/scenarios` | [EARLY ACCESS] ListScenarios: List Scenarios |
| [**ListScenariosForScope**](#listscenariosforscope) | **GET** `/api/api/scenarios/{scope}` | [EARLY ACCESS] ListScenariosForScope: List Scenarios for a scope |
| [**PreviewScenario**](#previewscenario) | **POST** `/api/api/scenarios/$preview` | [EARLY ACCESS] PreviewScenario: Preview a Scenario |
| [**SolveReverseStress**](#solvereversestress) | **POST** `/api/api/scenarios/$reversestress` | [EARLY ACCESS] SolveReverseStress: Solve a reverse stress test |
| [**UpsertScenario**](#upsertscenario) | **POST** `/api/api/scenarios` | [EARLY ACCESS] UpsertScenario: Upsert a Scenario. This creates or updates the scenario definition in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ScenariosApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
```

---

<a id="createscenariofromtemplate"></a>
## CreateScenarioFromTemplate

> UpsertSingleStructuredDataResponse CreateScenarioFromTemplate(string scope, CreateScenarioFromTemplateRequest createScenarioFromTemplateRequest)

[EARLY ACCESS] CreateScenarioFromTemplate: [EARLY ACCESS] CreateScenarioFromTemplate: Create a Scenario from a pre-built template.

Creates and stores a scenario built from a pre-defined parameterised template, for example a  parallel rates shift or an equity crash. The template determines the scenario's shifts; the  parameters supply the targets (e.g. currency or instrument) and optionally override the default  shift size. The created scenario is stored in the given scope and behaves exactly like a  hand-built scenario.                Use ListScenarioTemplates to discover the available templates and, for each, the parameters it  accepts, their defaults and their units. A parameter the template does not read is rejected  rather than ignored, and parameter names are case-sensitive.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var createScenarioFromTemplateRequest = new CreateScenarioFromTemplateRequest(); // CreateScenarioFromTemplateRequest
UpsertSingleStructuredDataResponse result = apiInstance.CreateScenarioFromTemplate(scope, createScenarioFromTemplateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create the scenario |
| **createScenarioFromTemplateRequest** | [CreateScenarioFromTemplateRequest](../Model/CreateScenarioFromTemplateRequest.md) | body | **required** | The template, code and parameters to create the scenario from |

### Return type

[UpsertSingleStructuredDataResponse](../Model/UpsertSingleStructuredDataResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully created scenario or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateScenarioFromTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.CreateScenarioFromTemplateWithHttpInfo(scope, createScenarioFromTemplateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletescenario"></a>
## DeleteScenario

> AnnulSingleStructuredDataResponse DeleteScenario(string scope, string code)

[EARLY ACCESS] DeleteScenario: Delete a Scenario, assuming that it is present.

Delete the specified Scenario definition from a single scope.                The response will return either detail of the deleted item, or an explanation (failure) as to why this did not succeed.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
AnnulSingleStructuredDataResponse result = apiInstance.DeleteScenario(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Scenario to delete. |
| **code** | **string** | path | **required** | The Scenario to delete. |

### Return type

[AnnulSingleStructuredDataResponse](../Model/AnnulSingleStructuredDataResponse.md)

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
<summary>Using the DeleteScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AnnulSingleStructuredDataResponse> response = apiInstance.DeleteScenarioWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getscenario"></a>
## GetScenario

> GetScenarioResponse GetScenario(string scope, string code, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetScenario: Get Scenario

Get a Scenario definition from a single scope.                The response will return either the scenario that has been stored, or a failure explaining why the request was unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetScenarioResponse result = apiInstance.GetScenario(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Scenario to retrieve. |
| **code** | **string** | path | **required** | The code of the Scenario to retrieve. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Scenario. Defaults to return the latest version if not specified. |

### Return type

[GetScenarioResponse](../Model/GetScenarioResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Scenario |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetScenarioResponse> response = apiInstance.GetScenarioWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listscenariotemplates"></a>
## ListScenarioTemplates

> ResourceListOfScenarioTemplateDefinition ListScenarioTemplates()

[EARLY ACCESS] ListScenarioTemplates: [EARLY ACCESS] ListScenarioTemplates: List the pre-built scenario templates.

Lists every template CreateScenarioFromTemplate accepts, with each template's parameters: the  parameter's name (case-sensitive), whether it is required, what it means, the default used when  it is omitted and the unit a numeric value is read in. The units differ between templates -  basis points, percentage points or a fraction - so read them per template rather than assuming  one convention. The list is static application metadata: it does not vary by tenant, scope or  date, so the endpoint takes no parameters.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
ResourceListOfScenarioTemplateDefinition result = apiInstance.ListScenarioTemplates();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfScenarioTemplateDefinition](../Model/ResourceListOfScenarioTemplateDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The available scenario templates |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListScenarioTemplatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfScenarioTemplateDefinition> response = apiInstance.ListScenarioTemplatesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listscenarioversions"></a>
## ListScenarioVersions

> PagedResourceListOfVersion ListScenarioVersions(string scope, string code, DateTimeOffset? asAt = null, int? limit = null, string? page = null)

[EARLY ACCESS] ListScenarioVersions: List the versions of a Scenario

List the AsAt versions of a single Scenario definition, newest first: one entry per change,  with the version number, the AsAt datetime it was written, and the user that wrote it.                Scenarios are perpetual (AsAt-only), so a version's AsAt datetime identifies it completely:  pass it as the asAt on GetScenario to view that version, or as the scenario reference's  asAt on a valuation to price under it.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfVersion result = apiInstance.ListScenarioVersions(scope, code, asAt, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Scenario to list versions for. |
| **code** | **string** | path | **required** | The code of the Scenario to list versions for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime to cap the version history at. Defaults to all versions up to now. |
| **limit** | **int?** | query | optional | Maximum number of results to return. Defaults to 100. |
| **page** | **string?** | query | optional | Pagination token from a previous result to fetch the next page. |

### Return type

[PagedResourceListOfVersion](../Model/PagedResourceListOfVersion.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The versions of the scenario, newest first |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListScenarioVersionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfVersion> response = apiInstance.ListScenarioVersionsWithHttpInfo(scope, code, asAt, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listscenarios"></a>
## ListScenarios

> PagedResourceListOfGetScenarioResponse ListScenarios(DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EARLY ACCESS] ListScenarios: List Scenarios

List scenario definitions across all scopes at the specified date/time. Each item carries  its scope and code. Scenarios the caller is not entitled to read are omitted.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfGetScenarioResponse result = apiInstance.ListScenarios(asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the scenarios. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set, e.g. \&quot;scope eq &#39;MyScope&#39;\&quot;. |
| **limit** | **int?** | query | optional | Maximum number of results to return. Defaults to 100. |
| **page** | **string?** | query | optional | Pagination token from a previous result to fetch the next page. |

### Return type

[PagedResourceListOfGetScenarioResponse](../Model/PagedResourceListOfGetScenarioResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested scenarios |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListScenariosWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGetScenarioResponse> response = apiInstance.ListScenariosWithHttpInfo(asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listscenariosforscope"></a>
## ListScenariosForScope

> PagedResourceListOfGetScenarioResponse ListScenariosForScope(string scope, DateTimeOffset? asAt = null, string? filter = null, int? limit = null, string? page = null)

[EARLY ACCESS] ListScenariosForScope: List Scenarios for a scope

List the set of scenario definitions in a single scope at the specified date/time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scope = "scope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfGetScenarioResponse result = apiInstance.ListScenariosForScope(scope, asAt, filter, limit, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to list scenarios for. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the scenarios. Defaults to latest if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. |
| **limit** | **int?** | query | optional | Maximum number of results to return. Defaults to 100. |
| **page** | **string?** | query | optional | Pagination token from a previous result to fetch the next page. |

### Return type

[PagedResourceListOfGetScenarioResponse](../Model/PagedResourceListOfGetScenarioResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested scenarios |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListScenariosForScopeWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGetScenarioResponse> response = apiInstance.ListScenariosForScopeWithHttpInfo(scope, asAt, filter, limit, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="previewscenario"></a>
## PreviewScenario

> ScenarioPreviewResponse PreviewScenario(ScenarioPreviewRequest scenarioPreviewRequest)

[EARLY ACCESS] PreviewScenario: Preview a Scenario

Preview what a scenario would do to a portfolio's market data, without running a valuation.                The portfolio's market data dependencies are resolved through the given recipe and the scenario's  shifts are applied; the response lists every market data target the shifts changed, with values  before and after, plus any market data that matched a shift but could not honour it. Supply  either a reference to a stored scenario, or inline shift definitions to test a definition before  saving it.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var scenarioPreviewRequest = new ScenarioPreviewRequest(); // ScenarioPreviewRequest
ScenarioPreviewResponse result = apiInstance.PreviewScenario(scenarioPreviewRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scenarioPreviewRequest** | [ScenarioPreviewRequest](../Model/ScenarioPreviewRequest.md) | body | **required** | The recipe, portfolios, effective date and scenario (stored reference or inline shifts) to preview |

### Return type

[ScenarioPreviewResponse](../Model/ScenarioPreviewResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The preview of the scenario&#39;s effect on the portfolio&#39;s market data, or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PreviewScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ScenarioPreviewResponse> response = apiInstance.PreviewScenarioWithHttpInfo(scenarioPreviewRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="solvereversestress"></a>
## SolveReverseStress

> ReverseStressResponse SolveReverseStress(ReverseStressRequest reverseStressRequest)

[EARLY ACCESS] SolveReverseStress: Solve a reverse stress test

Solve for how far the market has to move to produce a given change in portfolio value.                A scenario supplies the direction the market moves in: which risk factors move, and in what  proportion to each other. The solve is over a single factor its shifts are multiplied by, so the  answer is a multiple of the scenario rather than a set of shifts in its own right - a factor of  two means twice every shift the scenario states.                A ladder of factors is valued first, all in one valuation so the rungs share market data  resolution, then the bracketing pair is interpolated and the interpolated factor valued again to  confirm it. The whole ladder is returned: a reverse stress is only meaningful where the change in  value moves in one direction with the factor, and the ladder is what shows whether it does.                The solve is refused rather than approximated where it cannot be trusted: a scenario carrying a  shift with no size to scale (a model option, or a market data routing override), a measure that  cannot be computed under a scenario, or a valuation that could not price every holding.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var reverseStressRequest = new ReverseStressRequest(); // ReverseStressRequest
ReverseStressResponse result = apiInstance.SolveReverseStress(reverseStressRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **reverseStressRequest** | [ReverseStressRequest](../Model/ReverseStressRequest.md) | body | **required** | The recipe, portfolios, effective date, scenario direction and target change in value |

### Return type

[ReverseStressResponse](../Model/ReverseStressResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The solved scale with the evaluated ladder, or any failure |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SolveReverseStressWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReverseStressResponse> response = apiInstance.SolveReverseStressWithHttpInfo(reverseStressRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertscenario"></a>
## UpsertScenario

> UpsertSingleStructuredDataResponse UpsertScenario(UpsertScenarioRequest upsertScenarioRequest)

[EARLY ACCESS] UpsertScenario: Upsert a Scenario. This creates or updates the scenario definition in LUSID.

Update or insert one Scenario definition. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted scenario or failure message if unsuccessful.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScenariosApi>();
var upsertScenarioRequest = new UpsertScenarioRequest(); // UpsertScenarioRequest
UpsertSingleStructuredDataResponse result = apiInstance.UpsertScenario(upsertScenarioRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertScenarioRequest** | [UpsertScenarioRequest](../Model/UpsertScenarioRequest.md) | body | **required** | The Scenario to update or insert |

### Return type

[UpsertSingleStructuredDataResponse](../Model/UpsertSingleStructuredDataResponse.md)

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
<summary>Using the UpsertScenarioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertSingleStructuredDataResponse> response = apiInstance.UpsertScenarioWithHttpInfo(upsertScenarioRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

