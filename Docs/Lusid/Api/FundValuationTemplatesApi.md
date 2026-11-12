# Finbourne.Sdk.Lusid.Api.FundValuationTemplatesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteValuationAddressKeyTemplate**](#deletevaluationaddresskeytemplate) | **DELETE** `/api/api/fundvaluationtemplates/{scope}/{code}` | [EXPERIMENTAL] DeleteValuationAddressKeyTemplate: Delete a Valuation Template. |
| [**GetValuationAddressKeyTemplate**](#getvaluationaddresskeytemplate) | **GET** `/api/api/fundvaluationtemplates/{scope}/{code}` | [EXPERIMENTAL] GetValuationAddressKeyTemplate: Get a Valuation Template. |
| [**ListValuationAddressKeyTemplates**](#listvaluationaddresskeytemplates) | **GET** `/api/api/fundvaluationtemplates` | [EXPERIMENTAL] ListValuationAddressKeyTemplates: List Valuation Templates. |
| [**UpsertValuationAddressKeyTemplate**](#upsertvaluationaddresskeytemplate) | **PUT** `/api/api/fundvaluationtemplates/{scope}/{code}` | [EXPERIMENTAL] UpsertValuationAddressKeyTemplate: Upsert a Valuation Template. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<FundValuationTemplatesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundValuationTemplatesApi>();
```

---

<a id="deletevaluationaddresskeytemplate"></a>
## DeleteValuationAddressKeyTemplate

> DeletedEntityResponse DeleteValuationAddressKeyTemplate(string scope, string code)

[EXPERIMENTAL] DeleteValuationAddressKeyTemplate: Delete a Valuation Template.

Delete the given Valuation Template. A template that any Fund or NAV Type references cannot be deleted.  If the deleted template is the domain default, the system default defined by LUSID applies again.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundValuationTemplatesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteValuationAddressKeyTemplate(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Valuation Template. |
| **code** | **string** | path | **required** | The code of the Valuation Template to delete. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Valuation Template was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteValuationAddressKeyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteValuationAddressKeyTemplateWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluationaddresskeytemplate"></a>
## GetValuationAddressKeyTemplate

> ValuationAddressKeyTemplate GetValuationAddressKeyTemplate(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetValuationAddressKeyTemplate: Get a Valuation Template.

Retrieve a Valuation Template.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundValuationTemplatesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ValuationAddressKeyTemplate result = apiInstance.GetValuationAddressKeyTemplate(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Valuation Template. |
| **code** | **string** | path | **required** | The code of the Valuation Template. Together with the scope this uniquely identifies the template. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Valuation Template. Defaults to returning the latest version if not specified. |

### Return type

[ValuationAddressKeyTemplate](../Model/ValuationAddressKeyTemplate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Valuation Template. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValuationAddressKeyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationAddressKeyTemplate> response = apiInstance.GetValuationAddressKeyTemplateWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listvaluationaddresskeytemplates"></a>
## ListValuationAddressKeyTemplates

> PagedResourceListOfValuationAddressKeyTemplate ListValuationAddressKeyTemplates(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListValuationAddressKeyTemplates: List Valuation Templates.

List the Valuation Templates matching the given criteria. The list includes the system default, with scope  \"default\" and code \"DefaultTemplate\". If no stored template is the default, the system default applies.  To find the domain default, filter on \"isDefault eq true\".

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundValuationTemplatesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfValuationAddressKeyTemplate result = apiInstance.ListValuationAddressKeyTemplates(asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Valuation Templates. Defaults to returning the latest version of each template if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Valuation Templates; this              value is returned from the previous call. If a pagination token is provided, the filter, sortBy and asAt              fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the display name, specify \&quot;displayName eq &#39;Default keys&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/docs/filtering-information-retrieved-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfValuationAddressKeyTemplate](../Model/PagedResourceListOfValuationAddressKeyTemplate.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Valuation Templates. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListValuationAddressKeyTemplatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfValuationAddressKeyTemplate> response = apiInstance.ListValuationAddressKeyTemplatesWithHttpInfo(asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertvaluationaddresskeytemplate"></a>
## UpsertValuationAddressKeyTemplate

> ValuationAddressKeyTemplate UpsertValuationAddressKeyTemplate(string scope, string code, UpsertValuationAddressKeyTemplateRequest upsertValuationAddressKeyTemplateRequest)

[EXPERIMENTAL] UpsertValuationAddressKeyTemplate: Upsert a Valuation Template.

Create a Valuation Template, or replace the whole content of an existing one. Every Fund and NAV Type that  references the template uses the new content. Set isDefault to make the template the domain default.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<FundValuationTemplatesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var upsertValuationAddressKeyTemplateRequest = new UpsertValuationAddressKeyTemplateRequest(); // UpsertValuationAddressKeyTemplateRequest
ValuationAddressKeyTemplate result = apiInstance.UpsertValuationAddressKeyTemplate(scope, code, upsertValuationAddressKeyTemplateRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Valuation Template. |
| **code** | **string** | path | **required** | The code of the Valuation Template. Together with the scope this uniquely identifies the template. |
| **upsertValuationAddressKeyTemplateRequest** | [UpsertValuationAddressKeyTemplateRequest](../Model/UpsertValuationAddressKeyTemplateRequest.md) | body | **required** | The full content of the Valuation Template. |

### Return type

[ValuationAddressKeyTemplate](../Model/ValuationAddressKeyTemplate.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted Valuation Address Key Template. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertValuationAddressKeyTemplateWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ValuationAddressKeyTemplate> response = apiInstance.UpsertValuationAddressKeyTemplateWithHttpInfo(scope, code, upsertValuationAddressKeyTemplateRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

