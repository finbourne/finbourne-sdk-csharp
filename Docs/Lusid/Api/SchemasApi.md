# Finbourne.Sdk.Lusid.Api.SchemasApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetEntitySchema**](#getentityschema) | **GET** `/api/api/schemas/entities/{entity}` | [EARLY ACCESS] GetEntitySchema: Get schema |
| [**GetPropertySchema**](#getpropertyschema) | **GET** `/api/api/schemas/properties` | [EARLY ACCESS] GetPropertySchema: Get property schema |
| [**GetValueTypes**](#getvaluetypes) | **GET** `/api/api/schemas/types` | [EARLY ACCESS] GetValueTypes: Get value types |
| [**ListEntities**](#listentities) | **GET** `/api/api/schemas/entities` | [EARLY ACCESS] ListEntities: List entities |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SchemasApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchemasApi>();
```

---

<a id="getentityschema"></a>
## GetEntitySchema

> Schema GetEntitySchema(string entity)

[EARLY ACCESS] GetEntitySchema: Get schema

Gets the schema and meta-data for a given entity

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchemasApi>();
var entity = "entity_example";  // string
Schema result = apiInstance.GetEntitySchema(entity);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entity** | **string** | path | **required** | The name of a valid entity |

### Return type

[Schema](Schema.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetEntitySchemaWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Schema> response = apiInstance.GetEntitySchemaWithHttpInfo(entity);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpropertyschema"></a>
## GetPropertySchema

> PropertySchema GetPropertySchema(List<string>? propertyKeys = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetPropertySchema: Get property schema

Get the schemas for the provided list of property keys.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchemasApi>();
var propertyKeys = new List<string>?(); // List<string>? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PropertySchema result = apiInstance.GetPropertySchema(propertyKeys, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | One or more property keys for which the schema is requested |
| **asAt** | **DateTimeOffset?** | query | optional | Optional. The AsAt date of the data |

### Return type

[PropertySchema](PropertySchema.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPropertySchemaWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PropertySchema> response = apiInstance.GetPropertySchemaWithHttpInfo(propertyKeys, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getvaluetypes"></a>
## GetValueTypes

> ResourceListOfValueType GetValueTypes(List<string>? sortBy = null, int? limit = null)

[EARLY ACCESS] GetValueTypes: Get value types

Gets the available value types for which a schema is available.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchemasApi>();
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
ResourceListOfValueType result = apiInstance.GetValueTypes(sortBy, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | Optional. Order the results by these fields. Use use the &#39;-&#39; sign to denote descending order e.g. -MyFieldName |
| **limit** | **int?** | query | optional | Optional. When paginating, limit the number of returned results to this many. |

### Return type

[ResourceListOfValueType](ResourceListOfValueType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetValueTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfValueType> response = apiInstance.GetValueTypesWithHttpInfo(sortBy, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listentities"></a>
## ListEntities

> ResourceListOfString ListEntities()

[EARLY ACCESS] ListEntities: List entities

List all available entities for which schema information is available.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SchemasApi>();
ResourceListOfString result = apiInstance.ListEntities();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfString](ResourceListOfString.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfString> response = apiInstance.ListEntitiesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

