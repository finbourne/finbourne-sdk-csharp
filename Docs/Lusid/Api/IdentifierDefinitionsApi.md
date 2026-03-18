# Finbourne.Sdk.Lusid.Api.IdentifierDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateIdentifierDefinition**](#createidentifierdefinition) | **POST** `/api/api/identifierdefinitions` | [EXPERIMENTAL] CreateIdentifierDefinition: Create an Identifier Definition |
| [**DeleteIdentifierDefinition**](#deleteidentifierdefinition) | **DELETE** `/api/api/identifierdefinitions/{domain}/{identifierScope}/{identifierType}` | [EXPERIMENTAL] DeleteIdentifierDefinition: Delete a particular Identifier Definition |
| [**GetIdentifierDefinition**](#getidentifierdefinition) | **GET** `/api/api/identifierdefinitions/{domain}/{identifierScope}/{identifierType}` | [EXPERIMENTAL] GetIdentifierDefinition: Get a single Identifier Definition |
| [**ListIdentifierDefinitions**](#listidentifierdefinitions) | **GET** `/api/api/identifierdefinitions` | [EXPERIMENTAL] ListIdentifierDefinitions: List Identifier Definitions |
| [**UpdateIdentifierDefinition**](#updateidentifierdefinition) | **PUT** `/api/api/identifierdefinitions/{domain}/{identifierScope}/{identifierType}` | [EXPERIMENTAL] UpdateIdentifierDefinition: Update Identifier Definition defined by domain, identifierScope, and identifierType |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<IdentifierDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentifierDefinitionsApi>();
```

---

<a id="createidentifierdefinition"></a>
## CreateIdentifierDefinition

> IdentifierDefinition CreateIdentifierDefinition(CreateIdentifierDefinitionRequest? createIdentifierDefinitionRequest = null)

[EXPERIMENTAL] CreateIdentifierDefinition: Create an Identifier Definition

Define a new Identifier Definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentifierDefinitionsApi>();
var createIdentifierDefinitionRequest = new CreateIdentifierDefinitionRequest?(); // CreateIdentifierDefinitionRequest? (optional)
IdentifierDefinition result = apiInstance.CreateIdentifierDefinition(createIdentifierDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createIdentifierDefinitionRequest** | [CreateIdentifierDefinitionRequest?](CreateIdentifierDefinitionRequest?.md) | body | optional | The request defining the new definition |

### Return type

[IdentifierDefinition](IdentifierDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created Identifier Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateIdentifierDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IdentifierDefinition> response = apiInstance.CreateIdentifierDefinitionWithHttpInfo(createIdentifierDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteidentifierdefinition"></a>
## DeleteIdentifierDefinition

> DeletedEntityResponse DeleteIdentifierDefinition(string domain, string identifierScope, string identifierType)

[EXPERIMENTAL] DeleteIdentifierDefinition: Delete a particular Identifier Definition

The deletion will take effect from the Identifier Definition deletion datetime.  i.e. will no longer exist at any asAt datetime after the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentifierDefinitionsApi>();
var domain = "NotDefined";  // string
var identifierScope = "identifierScope_example";  // string
var identifierType = "identifierType_example";  // string
DeletedEntityResponse result = apiInstance.DeleteIdentifierDefinition(domain, identifierScope, identifierType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The type of entity to which the identifier relates |
| **identifierScope** | **string** | path | **required** | The scope that the identifier exists in |
| **identifierType** | **string** | path | **required** | What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the identifier definition |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The deleted entity metadata |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteIdentifierDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteIdentifierDefinitionWithHttpInfo(domain, identifierScope, identifierType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getidentifierdefinition"></a>
## GetIdentifierDefinition

> IdentifierDefinition GetIdentifierDefinition(string domain, string identifierScope, string identifierType, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetIdentifierDefinition: Get a single Identifier Definition

Get a single Identifier Definition using domain, identifierScope, identifierType, and an optional asAt              - defaulting to latest if not specified

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentifierDefinitionsApi>();
var domain = "NotDefined";  // string
var identifierScope = "identifierScope_example";  // string
var identifierType = "identifierType_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
IdentifierDefinition result = apiInstance.GetIdentifierDefinition(domain, identifierScope, identifierType, asAt, effectiveAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The type of entity to which the identifier relates. |
| **identifierScope** | **string** | path | **required** | The scope that the identifier exists in |
| **identifierType** | **string** | path | **required** | What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the identifier definition |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Identifier Definition. Defaults to return              the latest version of the definition if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the Identifier Definitions.              Since Identifier Definitions exist for all effective time, this will only apply to properties (if requested)              on the Identifier Definition. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;IdentifierDefinition&#39; domain to decorate onto the Identifier Definition.              These must take the format {domain}/{scope}/{code}. If no properties are specified, then no properties will be returned. |

### Return type

[IdentifierDefinition](IdentifierDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Identifier Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetIdentifierDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IdentifierDefinition> response = apiInstance.GetIdentifierDefinitionWithHttpInfo(domain, identifierScope, identifierType, asAt, effectiveAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listidentifierdefinitions"></a>
## ListIdentifierDefinitions

> PagedResourceListOfIdentifierDefinition ListIdentifierDefinitions(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListIdentifierDefinitions: List Identifier Definitions

Retrieves all Identifier Definitions that fit the filter, in a specific order if sortBy is provided  Supports pagination

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentifierDefinitionsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfIdentifierDefinition result = apiInstance.ListIdentifierDefinitions(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the Identifier Definitions.              Since Identifier Definitions exist for all effective time, this will only apply to properties (if requested)              on the Identifier Definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Identifier Definitions. Defaults to return the latest              version of the Identifier Definitions if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Identifier Definitions from a previous call to list              Identifier Definitions. This value is returned from the previous call. If a pagination token is provided the sortBy,              filter, effectiveAt, and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many per page. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;IdentifierDefinition&#39; domain to decorate onto the Identifier Definition.              These must take the format {domain}/{scope}/{code}. |

### Return type

[PagedResourceListOfIdentifierDefinition](PagedResourceListOfIdentifierDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested list of Identifier Definitions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListIdentifierDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfIdentifierDefinition> response = apiInstance.ListIdentifierDefinitionsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateidentifierdefinition"></a>
## UpdateIdentifierDefinition

> IdentifierDefinition UpdateIdentifierDefinition(string domain, string identifierScope, string identifierType, UpdateIdentifierDefinitionRequest? updateIdentifierDefinitionRequest = null)

[EXPERIMENTAL] UpdateIdentifierDefinition: Update Identifier Definition defined by domain, identifierScope, and identifierType

Overwrites an existing Identifier Definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IdentifierDefinitionsApi>();
var domain = "NotDefined";  // string
var identifierScope = "identifierScope_example";  // string
var identifierType = "identifierType_example";  // string
var updateIdentifierDefinitionRequest = new UpdateIdentifierDefinitionRequest?(); // UpdateIdentifierDefinitionRequest? (optional)
IdentifierDefinition result = apiInstance.UpdateIdentifierDefinition(domain, identifierScope, identifierType, updateIdentifierDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The type of entity to which the identifier relates |
| **identifierScope** | **string** | path | **required** | The scope that the identifier exists in |
| **identifierType** | **string** | path | **required** | What the identifier represents. Together with \&quot;domain\&quot; and \&quot;identifierScope\&quot; this uniquely identifies the Identifier Definition |
| **updateIdentifierDefinitionRequest** | [UpdateIdentifierDefinitionRequest?](UpdateIdentifierDefinitionRequest?.md) | body | optional | The request containing the updated details of the Identifier Definition. |

### Return type

[IdentifierDefinition](IdentifierDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated version of the requested Identifier Definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateIdentifierDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IdentifierDefinition> response = apiInstance.UpdateIdentifierDefinitionWithHttpInfo(domain, identifierScope, identifierType, updateIdentifierDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

