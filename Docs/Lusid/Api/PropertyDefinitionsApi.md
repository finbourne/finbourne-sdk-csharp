# Finbourne.Sdk.Lusid.Api.PropertyDefinitionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDerivedPropertyDefinition**](#createderivedpropertydefinition) | **POST** `/api/api/propertydefinitions/derived` | [EARLY ACCESS] CreateDerivedPropertyDefinition: Create derived property definition |
| [**CreatePropertyDefinition**](#createpropertydefinition) | **POST** `/api/api/propertydefinitions` | CreatePropertyDefinition: Create property definition |
| [**DeletePropertyDefinition**](#deletepropertydefinition) | **DELETE** `/api/api/propertydefinitions/{domain}/{scope}/{code}` | DeletePropertyDefinition: Delete property definition |
| [**DeletePropertyDefinitionProperties**](#deletepropertydefinitionproperties) | **POST** `/api/api/propertydefinitions/{domain}/{scope}/{code}/properties/$delete` | [EARLY ACCESS] DeletePropertyDefinitionProperties: Delete property definition properties |
| [**GetDerivedFormulaExplanation**](#getderivedformulaexplanation) | **POST** `/api/api/propertydefinitions/derived/$formulaExplanation` | GetDerivedFormulaExplanation: Get explanation of a derived property formula |
| [**GetMultiplePropertyDefinitions**](#getmultiplepropertydefinitions) | **GET** `/api/api/propertydefinitions` | GetMultiplePropertyDefinitions: Get multiple property definitions |
| [**GetPropertyDefinition**](#getpropertydefinition) | **GET** `/api/api/propertydefinitions/{domain}/{scope}/{code}` | GetPropertyDefinition: Get property definition |
| [**GetPropertyDefinitionPropertyTimeSeries**](#getpropertydefinitionpropertytimeseries) | **GET** `/api/api/propertydefinitions/{domain}/{scope}/{code}/properties/time-series` | [EARLY ACCESS] GetPropertyDefinitionPropertyTimeSeries: Get Property Definition Property Time Series |
| [**ListPropertyDefinitions**](#listpropertydefinitions) | **GET** `/api/api/propertydefinitions/$list` | ListPropertyDefinitions: List property definitions |
| [**UpdateDerivedPropertyDefinition**](#updatederivedpropertydefinition) | **PUT** `/api/api/propertydefinitions/derived/{domain}/{scope}/{code}` | [EARLY ACCESS] UpdateDerivedPropertyDefinition: Update a pre-existing derived property definition |
| [**UpdatePropertyDefinition**](#updatepropertydefinition) | **PUT** `/api/api/propertydefinitions/{domain}/{scope}/{code}` | UpdatePropertyDefinition: Update property definition |
| [**UpsertPropertyDefinitionProperties**](#upsertpropertydefinitionproperties) | **POST** `/api/api/propertydefinitions/{domain}/{scope}/{code}/properties` | UpsertPropertyDefinitionProperties: Upsert properties to a property definition |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PropertyDefinitionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
```

---

<a id="createderivedpropertydefinition"></a>
## CreateDerivedPropertyDefinition

> PropertyDefinition CreateDerivedPropertyDefinition(CreateDerivedPropertyDefinitionRequest createDerivedPropertyDefinitionRequest)

[EARLY ACCESS] CreateDerivedPropertyDefinition: Create derived property definition

Define a new derived property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var createDerivedPropertyDefinitionRequest = new CreateDerivedPropertyDefinitionRequest(); // CreateDerivedPropertyDefinitionRequest
PropertyDefinition result = apiInstance.CreateDerivedPropertyDefinition(createDerivedPropertyDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createDerivedPropertyDefinitionRequest** | [CreateDerivedPropertyDefinitionRequest](CreateDerivedPropertyDefinitionRequest.md) | body | **required** | The definition of the new derived property. |

### Return type

[PropertyDefinition](PropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created derived property definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateDerivedPropertyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertyDefinition> response = apiInstance.CreateDerivedPropertyDefinitionWithHttpInfo(createDerivedPropertyDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createpropertydefinition"></a>
## CreatePropertyDefinition

> PropertyDefinition CreatePropertyDefinition(CreatePropertyDefinitionRequest createPropertyDefinitionRequest)

CreatePropertyDefinition: Create property definition

Define a new property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var createPropertyDefinitionRequest = new CreatePropertyDefinitionRequest(); // CreatePropertyDefinitionRequest
PropertyDefinition result = apiInstance.CreatePropertyDefinition(createPropertyDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createPropertyDefinitionRequest** | [CreatePropertyDefinitionRequest](CreatePropertyDefinitionRequest.md) | body | **required** | The definition of the new property. |

### Return type

[PropertyDefinition](PropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created property definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePropertyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertyDefinition> response = apiInstance.CreatePropertyDefinitionWithHttpInfo(createPropertyDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepropertydefinition"></a>
## DeletePropertyDefinition

> DeletedEntityResponse DeletePropertyDefinition(string domain, string scope, string code)

DeletePropertyDefinition: Delete property definition

Delete the definition of the specified property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeletePropertyDefinition(domain, scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The domain of the property to be deleted. |
| **scope** | **string** | path | **required** | The scope of the property to be deleted. |
| **code** | **string** | path | **required** | The code of the property to be deleted. Together with the domain and scope this uniquely              identifies the property. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time that the property definition was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePropertyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePropertyDefinitionWithHttpInfo(domain, scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepropertydefinitionproperties"></a>
## DeletePropertyDefinitionProperties

> DeletedEntityResponse DeletePropertyDefinitionProperties(string domain, string scope, string code, List<string> requestBody, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeletePropertyDefinitionProperties: Delete property definition properties

Delete one or more properties from a single property definition. If the properties are time-variant then an effective date time from which the  properties will be deleted must be specified. If the properties are perpetual then it is invalid to specify an effective date time for deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeletePropertyDefinitionProperties(domain, scope, code, requestBody, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The domain of the property definition to delete properties from. |
| **scope** | **string** | path | **required** | The scope of the property definition to delete properties from. |
| **code** | **string** | path | **required** | The code of the property definition to delete properties from. |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | The property keys of the properties to delete. These must take the format              {domain}/{scope}/{code} e.g \&quot;PropertyDefinition/myScope/someAttributeKey\&quot;. Each property must be from the \&quot;PropertyDefinition\&quot; domain. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete time-variant properties from.              The property must exist at the specified &#39;effectiveAt&#39; datetime. If the &#39;effectiveAt&#39; is not provided or is before              the time-variant property exists then a failure is returned. Do not specify this parameter if an of the properties to delete are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the properties were deleted from the specified definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePropertyDefinitionPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePropertyDefinitionPropertiesWithHttpInfo(domain, scope, code, requestBody, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getderivedformulaexplanation"></a>
## GetDerivedFormulaExplanation

> DerivedPropertyComponent GetDerivedFormulaExplanation(DerivationFormulaExplainRequest derivationFormulaExplainRequest, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null)

GetDerivedFormulaExplanation: Get explanation of a derived property formula

Produces a manifest that shows the nested hierarchy of any source properties and the actions taken upon them to create the derived property.  This can either be done against an existing entity, which will produce a manifest that includes the values of the source properties  at the specified effective date time, or it can be done without providing an entity which will produce a manifest without values.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var derivationFormulaExplainRequest = new DerivationFormulaExplainRequest(); // DerivationFormulaExplainRequest
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DerivedPropertyComponent result = apiInstance.GetDerivedFormulaExplanation(derivationFormulaExplainRequest, asAt, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **derivationFormulaExplainRequest** | [DerivationFormulaExplainRequest](DerivationFormulaExplainRequest.md) | body | **required** | Information about the derivation formula to explain, and optionally, the entity to resolve the formula against. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to resolve the entity. Defaults to returning the latest asAt in LUSID              if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to resolve the entity. Defaults to the current LUSID              system datetime if not specified. |

### Return type

[DerivedPropertyComponent](DerivedPropertyComponent.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested derived property formula components. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDerivedFormulaExplanationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DerivedPropertyComponent> response = apiInstance.GetDerivedFormulaExplanationWithHttpInfo(derivationFormulaExplainRequest, asAt, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getmultiplepropertydefinitions"></a>
## GetMultiplePropertyDefinitions

> ResourceListOfPropertyDefinition GetMultiplePropertyDefinitions(List<string> propertyKeys, DateTimeOffset? asAt = null, string? filter = null, DateTimeOrCutLabel? effectiveAt = null)

GetMultiplePropertyDefinitions: Get multiple property definitions

Retrieve the definition of one or more specified properties.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var propertyKeys = new List<string>(); // List<string>
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
ResourceListOfPropertyDefinition result = apiInstance.GetMultiplePropertyDefinitions(propertyKeys, asAt, filter, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | One or more property keys which identify each property that a definition should              be retrieved for. The format for each property key is {domain}/{scope}/{code}, e.g. &#39;Portfolio/Manager/Id&#39;. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the property definitions. Defaults to return              the latest version of each definition if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to filter on the Lifetime, use \&quot;lifeTime eq &#39;Perpetual&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list properties attached to the Property Definition.              Defaults to the current LUSID system datetime if not specified. |

### Return type

[ResourceListOfPropertyDefinition](ResourceListOfPropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested property definitions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMultiplePropertyDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyDefinition> response = apiInstance.GetMultiplePropertyDefinitionsWithHttpInfo(propertyKeys, asAt, filter, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpropertydefinition"></a>
## GetPropertyDefinition

> PropertyDefinition GetPropertyDefinition(string domain, string scope, string code, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null)

GetPropertyDefinition: Get property definition

Retrieve the definition of a specified property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
PropertyDefinition result = apiInstance.GetPropertyDefinition(domain, scope, code, asAt, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The domain of the specified property. |
| **scope** | **string** | path | **required** | The scope of the specified property. |
| **code** | **string** | path | **required** | The code of the specified property. Together with the domain and scope this uniquely              identifies the property. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the property definition. Defaults to return              the latest version of the definition if not specified. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list properties attached to the Property Definition.              Defaults to the current LUSID system datetime if not specified. |

### Return type

[PropertyDefinition](PropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested property definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPropertyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertyDefinition> response = apiInstance.GetPropertyDefinitionWithHttpInfo(domain, scope, code, asAt, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpropertydefinitionpropertytimeseries"></a>
## GetPropertyDefinitionPropertyTimeSeries

> ResourceListOfPropertyInterval GetPropertyDefinitionPropertyTimeSeries(string domain, string scope, string code, string propertyKey, DateTimeOffset? asAt = null, string? filter = null, string? page = null, int? limit = null)

[EARLY ACCESS] GetPropertyDefinitionPropertyTimeSeries: Get Property Definition Property Time Series

List the complete time series of a property definition property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var propertyKey = "propertyKey_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfPropertyInterval result = apiInstance.GetPropertyDefinitionPropertyTimeSeries(domain, scope, code, propertyKey, asAt, filter, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The domain of the property definition to which the property is attached |
| **scope** | **string** | path | **required** | The scope of the property definition to which the property is attached |
| **code** | **string** | path | **required** | The code of the property definition to which the property is attached |
| **propertyKey** | **string** | query | **required** | The property key of the property whose history to show. This must be from the \&quot;Property Definition\&quot; domain and in the format              {domain}/{scope}/{code}, for example \&quot;PropertyDefinition/myScope/someAttributeKey\&quot;. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to show the history. Defaults to the current datetime if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing properties from a previous call to get property time series.              This value is returned from the previous call. If a pagination token is provided the filter and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |

### Return type

[ResourceListOfPropertyInterval](ResourceListOfPropertyInterval.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time series of the property |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPropertyDefinitionPropertyTimeSeriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyInterval> response = apiInstance.GetPropertyDefinitionPropertyTimeSeriesWithHttpInfo(domain, scope, code, propertyKey, asAt, filter, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpropertydefinitions"></a>
## ListPropertyDefinitions

> PagedResourceListOfPropertyDefinition ListPropertyDefinitions(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

ListPropertyDefinitions: List property definitions

List all the property definitions matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfPropertyDefinition result = apiInstance.ListPropertyDefinitions(effectiveAt, asAt, propertyKeys, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the property definitions. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the property definitions. Defaults to returning the latest version              of each property definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Property Definition&#39; domain to decorate onto              property definitions. These must take the format              {domain}/{scope}/{code} e.g \&quot;PropertyDefinition/myScope/someAttributeKey\&quot;. Each property must be from the \&quot;PropertyDefinition\&quot; domain. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing property definitions; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the display name, specify \&quot;DisplayName eq &#39;DisplayName&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[PagedResourceListOfPropertyDefinition](PagedResourceListOfPropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested property definitions |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPropertyDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPropertyDefinition> response = apiInstance.ListPropertyDefinitionsWithHttpInfo(effectiveAt, asAt, propertyKeys, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatederivedpropertydefinition"></a>
## UpdateDerivedPropertyDefinition

> PropertyDefinition UpdateDerivedPropertyDefinition(string domain, string scope, string code, UpdateDerivedPropertyDefinitionRequest updateDerivedPropertyDefinitionRequest)

[EARLY ACCESS] UpdateDerivedPropertyDefinition: Update a pre-existing derived property definition

This will fail if the property definition does not exist

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateDerivedPropertyDefinitionRequest = new UpdateDerivedPropertyDefinitionRequest(); // UpdateDerivedPropertyDefinitionRequest
PropertyDefinition result = apiInstance.UpdateDerivedPropertyDefinition(domain, scope, code, updateDerivedPropertyDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | Domain of the property definition |
| **scope** | **string** | path | **required** | Scope of the property definition |
| **code** | **string** | path | **required** | Code of the property definition |
| **updateDerivedPropertyDefinitionRequest** | [UpdateDerivedPropertyDefinitionRequest](UpdateDerivedPropertyDefinitionRequest.md) | body | **required** | Information about the derived property definition being updated |

### Return type

[PropertyDefinition](PropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated derived property definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateDerivedPropertyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertyDefinition> response = apiInstance.UpdateDerivedPropertyDefinitionWithHttpInfo(domain, scope, code, updateDerivedPropertyDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatepropertydefinition"></a>
## UpdatePropertyDefinition

> PropertyDefinition UpdatePropertyDefinition(string domain, string scope, string code, UpdatePropertyDefinitionRequest updatePropertyDefinitionRequest)

UpdatePropertyDefinition: Update property definition

Update the definition of a specified existing property. Not all elements within a property definition  are modifiable due to the potential implications for values already stored against the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var updatePropertyDefinitionRequest = new UpdatePropertyDefinitionRequest(); // UpdatePropertyDefinitionRequest
PropertyDefinition result = apiInstance.UpdatePropertyDefinition(domain, scope, code, updatePropertyDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The domain of the property being updated. |
| **scope** | **string** | path | **required** | The scope of the property being updated. |
| **code** | **string** | path | **required** | The code of the property being updated. Together with the domain and scope this uniquely              identifies the property. |
| **updatePropertyDefinitionRequest** | [UpdatePropertyDefinitionRequest](UpdatePropertyDefinitionRequest.md) | body | **required** | The updated definition of the property. |

### Return type

[PropertyDefinition](PropertyDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated property definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePropertyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertyDefinition> response = apiInstance.UpdatePropertyDefinitionWithHttpInfo(domain, scope, code, updatePropertyDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertpropertydefinitionproperties"></a>
## UpsertPropertyDefinitionProperties

> BatchUpsertPropertyDefinitionPropertiesResponse UpsertPropertyDefinitionProperties(string domain, string scope, string code, Dictionary<string, Property> requestBody, string? successMode = null)

UpsertPropertyDefinitionProperties: Upsert properties to a property definition

Create or update properties for a particular property definition

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PropertyDefinitionsApi>();
var domain = "NotDefined";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>(); // Dictionary<string, Property>
var successMode = "\"Partial\"";  // string? (optional)
BatchUpsertPropertyDefinitionPropertiesResponse result = apiInstance.UpsertPropertyDefinitionProperties(domain, scope, code, requestBody, successMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **domain** | **string** | path | **required** | The domain of the specified property. |
| **scope** | **string** | path | **required** | The scope of the specified property. |
| **code** | **string** | path | **required** | The code of the specified property. Together with the domain and scope this uniquely |
| **requestBody** | [Dictionary&lt;string, Property&gt;](Property.md) | body | **required** | The properties to be created or updated. Each property in              the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code}, for example              &#39;PropertyDefinition/Manager/Id&#39;. |
| **successMode** | **string?** | query | optional | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial. Default: `&quot;Partial&quot;` |

### Return type

[BatchUpsertPropertyDefinitionPropertiesResponse](BatchUpsertPropertyDefinitionPropertiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The asAt datetime at which the properties were updated or created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPropertyDefinitionPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchUpsertPropertyDefinitionPropertiesResponse> response = apiInstance.UpsertPropertyDefinitionPropertiesWithHttpInfo(domain, scope, code, requestBody, successMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

