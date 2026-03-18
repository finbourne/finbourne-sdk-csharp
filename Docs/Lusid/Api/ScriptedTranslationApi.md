# Finbourne.Sdk.Lusid.Api.ScriptedTranslationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetTranslationDialect**](#gettranslationdialect) | **GET** `/api/api/scriptedtranslation/dialects/{scope}/{vendor}/{sourceSystem}/{entityType}/{serialisationFormat}/{version}` | [EARLY ACCESS] GetTranslationDialect: Get a dialect. |
| [**GetTranslationScript**](#gettranslationscript) | **GET** `/api/api/scriptedtranslation/scripts/{scope}/{code}/{version}` | [EARLY ACCESS] GetTranslationScript: Retrieve a translation script by its identifier. |
| [**ListDialectIds**](#listdialectids) | **GET** `/api/api/scriptedtranslation/dialects/ids` | [EARLY ACCESS] ListDialectIds: List dialect identifiers matching an optional filter. |
| [**ListTranslationScriptIds**](#listtranslationscriptids) | **GET** `/api/api/scriptedtranslation/scripts/ids` | [EARLY ACCESS] ListTranslationScriptIds: List translation script identifiers. |
| [**TranslateEntities**](#translateentities) | **POST** `/api/api/scriptedtranslation/translateentities` | [EARLY ACCESS] TranslateEntities: Translate a collection of entities with a specified translation script. |
| [**TranslateEntitiesInlined**](#translateentitiesinlined) | **POST** `/api/api/scriptedtranslation/translateentitiesinlined` | [EARLY ACCESS] TranslateEntitiesInlined: Translate a collection of entities, inlining the body of the translation script. |
| [**UpsertTranslationDialect**](#upserttranslationdialect) | **POST** `/api/api/scriptedtranslation/dialects` | [EARLY ACCESS] UpsertTranslationDialect: Upsert a Dialect. |
| [**UpsertTranslationScript**](#upserttranslationscript) | **POST** `/api/api/scriptedtranslation/scripts` | [EARLY ACCESS] UpsertTranslationScript: Upsert a translation script. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ScriptedTranslationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
```

---

<a id="gettranslationdialect"></a>
## GetTranslationDialect

> Dialect GetTranslationDialect(string scope, string vendor, string sourceSystem, string entityType, string serialisationFormat, string version, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetTranslationDialect: Get a dialect.

Get the dialect with the given identifier at the specific asAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var scope = "scope_example";  // string
var vendor = "vendor_example";  // string
var sourceSystem = "sourceSystem_example";  // string
var entityType = "entityType_example";  // string
var serialisationFormat = "serialisationFormat_example";  // string
var version = "version_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dialect result = apiInstance.GetTranslationDialect(scope, vendor, sourceSystem, entityType, serialisationFormat, version, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the dialect. |
| **vendor** | **string** | path | **required** | The vendor of the dialect, the entity that created it. e.g. ISDA, FINBOURNE. |
| **sourceSystem** | **string** | path | **required** | The source system of the dialect, the system that understands it. e.g. LUSID, QuantLib. |
| **entityType** | **string** | path | **required** | The type of entity this dialect describes e.g. Instrument. |
| **serialisationFormat** | **string** | path | **required** | The serialisation format of a document in this dialect. e.g. JSON, XML. |
| **version** | **string** | path | **required** | The semantic version of the dialect: MAJOR.MINOR.PATCH. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the dialect. Defaults to return the latest version of the dialect if not specified. |

### Return type

[Dialect](Dialect.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The dialect with the given ID. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTranslationDialectWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dialect> response = apiInstance.GetTranslationDialectWithHttpInfo(scope, vendor, sourceSystem, entityType, serialisationFormat, version, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettranslationscript"></a>
## GetTranslationScript

> TranslationScript GetTranslationScript(string scope, string code, string version, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetTranslationScript: Retrieve a translation script by its identifier.

Retrieves a translation script to be used for translating financial entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var version = "version_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
TranslationScript result = apiInstance.GetTranslationScript(scope, code, version, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the translation script. |
| **code** | **string** | path | **required** | Code of the translation script. |
| **version** | **string** | path | **required** | Semantic version of the translation script. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the translation script. Defaults to latest. |

### Return type

[TranslationScript](TranslationScript.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested translation script. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTranslationScriptWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TranslationScript> response = apiInstance.GetTranslationScriptWithHttpInfo(scope, code, version, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listdialectids"></a>
## ListDialectIds

> PagedResourceListOfDialectId ListDialectIds(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EARLY ACCESS] ListDialectIds: List dialect identifiers matching an optional filter.

List the stored dialects' identifiers with pagination and filtering at the specified asAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfDialectId result = apiInstance.ListDialectIds(asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the dialects.              Defaults to return the latest version of the dialect if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing dialect IDs from a previous call to list dialect IDs.              This value is returned from the previous call. If a pagination token is provided the filter and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfDialectId](PagedResourceListOfDialectId.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of dialect IDs. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListDialectIdsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfDialectId> response = apiInstance.ListDialectIdsWithHttpInfo(asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listtranslationscriptids"></a>
## ListTranslationScriptIds

> PagedResourceListOfTranslationScriptId ListTranslationScriptIds(DateTimeOffset? asAt = null, int? limit = null, string? filter = null, string? page = null)

[EARLY ACCESS] ListTranslationScriptIds: List translation script identifiers.

List translation script ids.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
PagedResourceListOfTranslationScriptId result = apiInstance.ListTranslationScriptIds(asAt, limit, filter, page);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the script identifiers. Defaults to latest. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For example, Id.Version.Major eq 1 to list IDs with major version 1              or Id.Scope eq &#39;my-scripts&#39; to list result only for a particular scope. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing translation script IDs; this              value is returned from the previous call. If a pagination token is provided, the filter field              must not have changed since the original request. |

### Return type

[PagedResourceListOfTranslationScriptId](PagedResourceListOfTranslationScriptId.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested translation script IDs. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListTranslationScriptIdsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfTranslationScriptId> response = apiInstance.ListTranslationScriptIdsWithHttpInfo(asAt, limit, filter, page);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="translateentities"></a>
## TranslateEntities

> TranslateEntitiesResponse TranslateEntities(TranslateEntitiesRequest translateEntitiesRequest)

[EARLY ACCESS] TranslateEntities: Translate a collection of entities with a specified translation script.

Run the provided translation request. The entities to translate are specified in the request body as a  dictionary with (ephemeral) unique correlation IDs. The script to use and optional dialect to validate  results against are sourced from the database.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var translateEntitiesRequest = new TranslateEntitiesRequest(); // TranslateEntitiesRequest
TranslateEntitiesResponse result = apiInstance.TranslateEntities(translateEntitiesRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **translateEntitiesRequest** | [TranslateEntitiesRequest](TranslateEntitiesRequest.md) | body | **required** | The entities to translate, along with identifiers for the script and (optional) dialect to use. |

### Return type

[TranslateEntitiesResponse](TranslateEntitiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The translated entities along with any errors for entities that failed to be translated indexed by their correlation IDs. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the TranslateEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TranslateEntitiesResponse> response = apiInstance.TranslateEntitiesWithHttpInfo(translateEntitiesRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="translateentitiesinlined"></a>
## TranslateEntitiesInlined

> TranslateEntitiesResponse TranslateEntitiesInlined(TranslateEntitiesInlinedRequest translateEntitiesInlinedRequest)

[EARLY ACCESS] TranslateEntitiesInlined: Translate a collection of entities, inlining the body of the translation script.

Run the provided translation request. The entities to translate, script to use and dialect to validate results against  are all specified in the request body. The entities are given as a dictionary with (ephemeral) unique correlation IDs.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var translateEntitiesInlinedRequest = new TranslateEntitiesInlinedRequest(); // TranslateEntitiesInlinedRequest
TranslateEntitiesResponse result = apiInstance.TranslateEntitiesInlined(translateEntitiesInlinedRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **translateEntitiesInlinedRequest** | [TranslateEntitiesInlinedRequest](TranslateEntitiesInlinedRequest.md) | body | **required** | The entities to translate, along with the script to use and an optional schema for validation. |

### Return type

[TranslateEntitiesResponse](TranslateEntitiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The translated entities along with any errors for entities that failed to be translated indexed by their correlation IDs. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the TranslateEntitiesInlinedWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TranslateEntitiesResponse> response = apiInstance.TranslateEntitiesInlinedWithHttpInfo(translateEntitiesInlinedRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttranslationdialect"></a>
## UpsertTranslationDialect

> Dialect UpsertTranslationDialect(UpsertDialectRequest upsertDialectRequest)

[EARLY ACCESS] UpsertTranslationDialect: Upsert a Dialect.

Upsert the given dialect.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var upsertDialectRequest = new UpsertDialectRequest(); // UpsertDialectRequest
Dialect result = apiInstance.UpsertTranslationDialect(upsertDialectRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertDialectRequest** | [UpsertDialectRequest](UpsertDialectRequest.md) | body | **required** | The dialect to upsert. |

### Return type

[Dialect](Dialect.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted dialect. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTranslationDialectWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dialect> response = apiInstance.UpsertTranslationDialectWithHttpInfo(upsertDialectRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upserttranslationscript"></a>
## UpsertTranslationScript

> TranslationScript UpsertTranslationScript(UpsertTranslationScriptRequest upsertTranslationScriptRequest)

[EARLY ACCESS] UpsertTranslationScript: Upsert a translation script.

Upserts a translation script to be used for translating financial entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ScriptedTranslationApi>();
var upsertTranslationScriptRequest = new UpsertTranslationScriptRequest(); // UpsertTranslationScriptRequest
TranslationScript result = apiInstance.UpsertTranslationScript(upsertTranslationScriptRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertTranslationScriptRequest** | [UpsertTranslationScriptRequest](UpsertTranslationScriptRequest.md) | body | **required** | The translation script to be upserted. |

### Return type

[TranslationScript](TranslationScript.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully created translation script. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertTranslationScriptWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TranslationScript> response = apiInstance.UpsertTranslationScriptWithHttpInfo(upsertTranslationScriptRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

