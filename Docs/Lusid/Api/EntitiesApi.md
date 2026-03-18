# Finbourne.Sdk.Lusid.Api.EntitiesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetCustomEntityByEntityUniqueId**](#getcustomentitybyentityuniqueid) | **GET** `/api/api/entities/customentities/{entityUniqueId}` | GetCustomEntityByEntityUniqueId: Get a Custom Entity instance by its EntityUniqueId |
| [**GetDataTypeByEntityUniqueId**](#getdatatypebyentityuniqueid) | **GET** `/api/api/entities/datatypes/{entityUniqueId}` | GetDataTypeByEntityUniqueId: Get DataType by EntityUniqueId |
| [**GetEntityHistory**](#getentityhistory) | **GET** `/api/api/entities/{entityType}/{entityUniqueId}/history` | GetEntityHistory: List an entity&#39;s history information |
| [**GetInstrumentByEntityUniqueId**](#getinstrumentbyentityuniqueid) | **GET** `/api/api/entities/instruments/{entityUniqueId}` | GetInstrumentByEntityUniqueId: Get instrument by EntityUniqueId |
| [**GetPortfolioByEntityUniqueId**](#getportfoliobyentityuniqueid) | **GET** `/api/api/entities/portfolios/{entityUniqueId}` | GetPortfolioByEntityUniqueId: Get portfolio by EntityUniqueId |
| [**GetPortfolioChanges**](#getportfoliochanges) | **GET** `/api/api/entities/changes/portfolios` | GetPortfolioChanges: Get the next change to each portfolio in a scope. |
| [**GetPropertyDefinitionByEntityUniqueId**](#getpropertydefinitionbyentityuniqueid) | **GET** `/api/api/entities/propertydefinitions/{entityUniqueId}` | GetPropertyDefinitionByEntityUniqueId: Get property definition by EntityUniqueId |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<EntitiesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
```

---

<a id="getcustomentitybyentityuniqueid"></a>
## GetCustomEntityByEntityUniqueId

> CustomEntityEntity GetCustomEntityByEntityUniqueId(string entityUniqueId, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? previews = null)

GetCustomEntityByEntityUniqueId: Get a Custom Entity instance by its EntityUniqueId

Retrieve a particular Custom Entity instance.  If the Custom Entity is deleted, this will return the state of the Custom Entity immediately prior to deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var previews = new List<string>?(); // List<string>? (optional)
CustomEntityEntity result = apiInstance.GetCustomEntityByEntityUniqueId(entityUniqueId, effectiveAt, asAt, previews);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The universally unique identifier of the Custom Entity. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Custom Entity. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Custom Entity. Defaults to returning the latest version of the Custom Entity if not specified. |
| **previews** | [List&lt;string&gt;?](string.md) | query | optional | The ids of the staged modifications to be previewed in the response. |

### Return type

[CustomEntityEntity](CustomEntityEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested CustomEntity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustomEntityByEntityUniqueIdWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityEntity> response = apiInstance.GetCustomEntityByEntityUniqueIdWithHttpInfo(entityUniqueId, effectiveAt, asAt, previews);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getdatatypebyentityuniqueid"></a>
## GetDataTypeByEntityUniqueId

> DataTypeEntity GetDataTypeByEntityUniqueId(string entityUniqueId, DateTimeOffset? asAt = null, List<string>? previews = null)

GetDataTypeByEntityUniqueId: Get DataType by EntityUniqueId

Retrieve the definition of a particular DataType.  If the DataType is deleted, this will return the state of the DataType immediately prior to deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var previews = new List<string>?(); // List<string>? (optional)
DataTypeEntity result = apiInstance.GetDataTypeByEntityUniqueId(entityUniqueId, asAt, previews);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The universally unique identifier of the DataType definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the DataType definition. Defaults to returning the latest version of the DataType definition if not specified. |
| **previews** | [List&lt;string&gt;?](string.md) | query | optional | The ids of the staged modifications to be previewed in the response. |

### Return type

[DataTypeEntity](DataTypeEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested DataType entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetDataTypeByEntityUniqueIdWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DataTypeEntity> response = apiInstance.GetDataTypeByEntityUniqueIdWithHttpInfo(entityUniqueId, asAt, previews);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getentityhistory"></a>
## GetEntityHistory

> ResourceListOfChangeInterval GetEntityHistory(string entityType, string entityUniqueId, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

GetEntityHistory: List an entity's history information

Retrieve a page of an entity's change history up to a particular point in AsAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var entityType = "entityType_example";  // string
var entityUniqueId = "entityUniqueId_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
ResourceListOfChangeInterval result = apiInstance.GetEntityHistory(entityType, entityUniqueId, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the entity to list the change history for. |
| **entityUniqueId** | **string** | path | **required** | The universally unique identifier of the entity. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list change history information. Defaults to return the change history at the latest datetime if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing change history information from a previous call to list change              history information. This value is returned from the previous call. If a pagination token is provided the filter, sortBy              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |

### Return type

[ResourceListOfChangeInterval](ResourceListOfChangeInterval.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The change history of the provided entity. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetEntityHistoryWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfChangeInterval> response = apiInstance.GetEntityHistoryWithHttpInfo(entityType, entityUniqueId, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstrumentbyentityuniqueid"></a>
## GetInstrumentByEntityUniqueId

> InstrumentEntity GetInstrumentByEntityUniqueId(string entityUniqueId, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? previews = null, string? dataModelScope = null, string? dataModelCode = null)

GetInstrumentByEntityUniqueId: Get instrument by EntityUniqueId

Retrieve the definition of a particular instrument.  If the instrument is deleted, this will return the state of the instrument immediately prior to deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var previews = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
InstrumentEntity result = apiInstance.GetInstrumentByEntityUniqueId(entityUniqueId, effectiveAt, asAt, previews, dataModelScope, dataModelCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The universally unique identifier of the instrument definition. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Instrument definition. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument definition. Defaults to returning the latest version of the instrument definition if not specified. |
| **previews** | [List&lt;string&gt;?](string.md) | query | optional | The ids of the staged modifications to be previewed in the response. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use. |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use. |

### Return type

[InstrumentEntity](InstrumentEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested instrument entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstrumentByEntityUniqueIdWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstrumentEntity> response = apiInstance.GetInstrumentByEntityUniqueIdWithHttpInfo(entityUniqueId, effectiveAt, asAt, previews, dataModelScope, dataModelCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliobyentityuniqueid"></a>
## GetPortfolioByEntityUniqueId

> PortfolioEntity GetPortfolioByEntityUniqueId(string entityUniqueId, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? previews = null)

GetPortfolioByEntityUniqueId: Get portfolio by EntityUniqueId

Retrieve the definition of a particular portfolio.  If the portfolio is deleted, this will return the state of the portfolio immediately prior to deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var previews = new List<string>?(); // List<string>? (optional)
PortfolioEntity result = apiInstance.GetPortfolioByEntityUniqueId(entityUniqueId, effectiveAt, asAt, previews);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The universally unique identifier of the portfolio definition. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the portfolio definition. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio definition. Defaults to returning the latest version of the portfolio definition if not specified. |
| **previews** | [List&lt;string&gt;?](string.md) | query | optional | The ids of the staged modifications to be previewed in the response. |

### Return type

[PortfolioEntity](PortfolioEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioByEntityUniqueIdWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioEntity> response = apiInstance.GetPortfolioByEntityUniqueIdWithHttpInfo(entityUniqueId, effectiveAt, asAt, previews);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliochanges"></a>
## GetPortfolioChanges

> ResourceListOfChange GetPortfolioChanges(string scope, DateTimeOrCutLabel effectiveAt, DateTimeOffset? asAt = null)

GetPortfolioChanges: Get the next change to each portfolio in a scope.

Gets the time of the next (earliest effective at) modification (correction and/or amendment) to each portfolio in a scope relative to a point in bitemporal time.  Includes changes from parent portfolios in different scopes.  Excludes changes from subscriptions (e.g corporate actions).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var scope = "scope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfChange result = apiInstance.GetPortfolioChanges(scope, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | query | **required** | The scope |
| **effectiveAt** | **DateTimeOrCutLabel** | query | **required** | The effective date of the origin. |
| **asAt** | **DateTimeOffset?** | query | optional | The as-at date of the origin. |

### Return type

[ResourceListOfChange](ResourceListOfChange.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | The details of the input related failure |  -  |
| **200** | A list of portfolio changes in the requested scope relative to the specified time. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioChangesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfChange> response = apiInstance.GetPortfolioChangesWithHttpInfo(scope, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpropertydefinitionbyentityuniqueid"></a>
## GetPropertyDefinitionByEntityUniqueId

> PropertyDefinitionEntity GetPropertyDefinitionByEntityUniqueId(string entityUniqueId, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? previews = null)

GetPropertyDefinitionByEntityUniqueId: Get property definition by EntityUniqueId

Retrieve a particular property definition.  If the property definition is deleted, this will return the state of the property definition immediately prior to deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<EntitiesApi>();
var entityUniqueId = "entityUniqueId_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var previews = new List<string>?(); // List<string>? (optional)
PropertyDefinitionEntity result = apiInstance.GetPropertyDefinitionByEntityUniqueId(entityUniqueId, effectiveAt, asAt, previews);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityUniqueId** | **string** | path | **required** | The universally unique identifier of the property definition. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to retrieve the property definition. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the property definition. Defaults to returning the latest version of the property definition if not specified. |
| **previews** | [List&lt;string&gt;?](string.md) | query | optional | The ids of the staged modifications to be previewed in the response. |

### Return type

[PropertyDefinitionEntity](PropertyDefinitionEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested property definition entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPropertyDefinitionByEntityUniqueIdWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertyDefinitionEntity> response = apiInstance.GetPropertyDefinitionByEntityUniqueIdWithHttpInfo(entityUniqueId, effectiveAt, asAt, previews);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

