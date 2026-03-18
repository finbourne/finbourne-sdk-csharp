# Finbourne.Sdk.Lusid.Api.CustomEntitiesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteCustomEntity**](#deletecustomentity) | **DELETE** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}` | DeleteCustomEntity: Delete a Custom Entity instance. |
| [**DeleteCustomEntityAccessMetadata**](#deletecustomentityaccessmetadata) | **DELETE** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/metadata/{metadataKey}` | [EARLY ACCESS] DeleteCustomEntityAccessMetadata: Delete a Custom Entity Access Metadata entry |
| [**GetAllCustomEntityAccessMetadata**](#getallcustomentityaccessmetadata) | **GET** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/metadata` | [EARLY ACCESS] GetAllCustomEntityAccessMetadata: Get all the Access Metadata rules for a Custom Entity |
| [**GetAllCustomEntityProperties**](#getallcustomentityproperties) | **GET** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/properties` | [EARLY ACCESS] GetAllCustomEntityProperties: Get all properties related to a Custom Entity instance. |
| [**GetCustomEntity**](#getcustomentity) | **GET** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}` | GetCustomEntity: Get a Custom Entity instance. |
| [**GetCustomEntityAccessMetadataByKey**](#getcustomentityaccessmetadatabykey) | **GET** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/metadata/{metadataKey}` | [EARLY ACCESS] GetCustomEntityAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Custom Entity |
| [**GetCustomEntityRelationships**](#getcustomentityrelationships) | **GET** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/relationships` | [EARLY ACCESS] GetCustomEntityRelationships: Get Relationships for Custom Entity |
| [**ListCustomEntities**](#listcustomentities) | **GET** `/api/api/customentities/{entityType}` | ListCustomEntities: List Custom Entities of the specified entityType. |
| [**PatchCustomEntityAccessMetadata**](#patchcustomentityaccessmetadata) | **PATCH** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/metadata` | [EARLY ACCESS] PatchCustomEntityAccessMetadata: Patch Access Metadata rules for a Custom Entity. |
| [**UpsertCustomEntities**](#upsertcustomentities) | **POST** `/api/api/customentities/{entityType}/$batchUpsert` | [EARLY ACCESS] UpsertCustomEntities: Batch upsert instances of Custom Entities |
| [**UpsertCustomEntity**](#upsertcustomentity) | **POST** `/api/api/customentities/{entityType}` | UpsertCustomEntity: Upsert a Custom Entity instance |
| [**UpsertCustomEntityAccessMetadata**](#upsertcustomentityaccessmetadata) | **PUT** `/api/api/customentities/{entityType}/{identifierType}/{identifierValue}/metadata/{metadataKey}` | [EARLY ACCESS] UpsertCustomEntityAccessMetadata: Upsert a Custom Entity Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CustomEntitiesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
```

---

<a id="deletecustomentity"></a>
## DeleteCustomEntity

> DeletedEntityResponse DeleteCustomEntity(string entityType, string identifierType, string identifierValue, string identifierScope)

DeleteCustomEntity: Delete a Custom Entity instance.

Delete a Custom Entity instance by a specific entity type.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var identifierScope = "identifierScope_example";  // string
DeletedEntityResponse result = apiInstance.DeleteCustomEntity(entityType, identifierType, identifierValue, identifierScope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of Custom Entity to remove. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delete a Custom Entity instance. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCustomEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCustomEntityWithHttpInfo(entityType, identifierType, identifierValue, identifierScope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecustomentityaccessmetadata"></a>
## DeleteCustomEntityAccessMetadata

> DeletedEntityResponse DeleteCustomEntityAccessMetadata(string entityType, string identifierType, string identifierValue, string metadataKey, string identifierScope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] DeleteCustomEntityAccessMetadata: Delete a Custom Entity Access Metadata entry

Deletes the Custom Entity Access Metadata entry that exactly matches the provided identifier parts.    It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var metadataKey = "metadataKey_example";  // string
var identifierScope = "identifierScope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.DeleteCustomEntityAccessMetadata(entityType, identifierType, identifierValue, metadataKey, identifierScope, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to delete. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the Access Metadata. |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective datetime until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; datetime of the Access Metadata. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the CustomEntity or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCustomEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCustomEntityAccessMetadataWithHttpInfo(entityType, identifierType, identifierValue, metadataKey, identifierScope, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallcustomentityaccessmetadata"></a>
## GetAllCustomEntityAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; GetAllCustomEntityAccessMetadata(string entityType, string identifierType, string identifierValue, string identifierScope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetAllCustomEntityAccessMetadata: Get all the Access Metadata rules for a Custom Entity

Get all the Custom Entity access metadata for the specified identifier scope, code and value

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var identifierScope = "identifierScope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.GetAllCustomEntityAccessMetadata(entityType, identifierType, identifierValue, identifierScope, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get the entities. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Access Metadata. Defaults to returning the latest version of the metadata if not specified. |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the CustomEntity or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllCustomEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.GetAllCustomEntityAccessMetadataWithHttpInfo(entityType, identifierType, identifierValue, identifierScope, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallcustomentityproperties"></a>
## GetAllCustomEntityProperties

> CustomEntityProperties GetAllCustomEntityProperties(string entityType, string identifierType, string identifierValue, string identifierScope, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] GetAllCustomEntityProperties: Get all properties related to a Custom Entity instance.

Returns only properties that a user has permissions to read             and that are applicable to the specific entity type as per PropertyDefinition CustomEntityTypes.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var identifierScope = "identifierScope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
CustomEntityProperties result = apiInstance.GetAllCustomEntityProperties(entityType, identifierType, identifierValue, identifierScope, asAt, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of Custom Entity. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the Custom Entity properties. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime at which to get the Custom Entity properties. Defaults to the current LUSID system datetime if not specified. |

### Return type

[CustomEntityProperties](CustomEntityProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get all properties for a custom entity instance. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllCustomEntityPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityProperties> response = apiInstance.GetAllCustomEntityPropertiesWithHttpInfo(entityType, identifierType, identifierValue, identifierScope, asAt, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcustomentity"></a>
## GetCustomEntity

> CustomEntityResponse GetCustomEntity(string entityType, string identifierType, string identifierValue, string identifierScope, DateTimeOffset? asAt = null, DateTimeOrCutLabel? effectiveAt = null, List<string>? relatedEntityPropertyKeys = null, List<string>? relationshipDefinitionIds = null, List<string>? propertyKeys = null)

GetCustomEntity: Get a Custom Entity instance.

Retrieve a Custom Entity instance by a specific entity type at a point in AsAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var identifierScope = "identifierScope_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var relatedEntityPropertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
CustomEntityResponse result = apiInstance.GetCustomEntity(entityType, identifierType, identifierValue, identifierScope, asAt, effectiveAt, relatedEntityPropertyKeys, relationshipDefinitionIds, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of Custom Entity to retrieve. An entityType can be created using the \&quot;CreateCustomEntityDefinition\&quot; endpoint for CustomEntityDefinitions. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **asAt** | **DateTimeOffset?** | query | optional | The AsAt datetime at which to retrieve the Custom Entity instance. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get the Custom Entity instance. Defaults to the current LUSID system datetime if not specified. |
| **relatedEntityPropertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from any domain that supports relationships              to decorate onto related entities. These must take the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the entity in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;CustomEntity&#39; domain to decorate onto              the custom entities of any type supported by that property (defined within the property definition CustomEntityTypes).              These must have the format {domain}/{scope}/{code}, for example &#39;CustomEntity/someScope/id&#39;. |

### Return type

[CustomEntityResponse](CustomEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get a custom entity instance. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustomEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityResponse> response = apiInstance.GetCustomEntityWithHttpInfo(entityType, identifierType, identifierValue, identifierScope, asAt, effectiveAt, relatedEntityPropertyKeys, relationshipDefinitionIds, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcustomentityaccessmetadatabykey"></a>
## GetCustomEntityAccessMetadataByKey

> List&lt;AccessMetadataValue&gt; GetCustomEntityAccessMetadataByKey(string entityType, string identifierType, string identifierValue, string metadataKey, string identifierScope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetCustomEntityAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Custom Entity

Get Custom Entity access metadata for the specified metadata key

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var metadataKey = "metadataKey_example";  // string
var identifierScope = "identifierScope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<AccessMetadataValue> result = apiInstance.GetCustomEntityAccessMetadataByKey(entityType, identifierType, identifierValue, metadataKey, identifierScope, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get the entities. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Access Metadata. Defaults to returning the latest version of the metadata if not specified. |

### Return type

[List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the CustomEntity or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustomEntityAccessMetadataByKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AccessMetadataValue>> response = apiInstance.GetCustomEntityAccessMetadataByKeyWithHttpInfo(entityType, identifierType, identifierValue, metadataKey, identifierScope, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcustomentityrelationships"></a>
## GetCustomEntityRelationships

> ResourceListOfRelationship GetCustomEntityRelationships(string entityType, string identifierScope, string identifierType, string identifierValue, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EARLY ACCESS] GetCustomEntityRelationships: Get Relationships for Custom Entity

Get relationships for the specified Custom Entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierScope = "identifierScope_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelationship result = apiInstance.GetCustomEntityRelationships(entityType, identifierScope, identifierType, identifierValue, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of entity get relationships for. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get relationships. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relationships. Defaults to return the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter relationships. Users should provide null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifiers types (as property keys) used for referencing Persons or Legal Entities. These take the format              {domain}/{scope}/{code} e.g. \&quot;Person/CompanyDetails/Role\&quot;. They must be from the \&quot;Person\&quot; or \&quot;LegalEntity\&quot; domain.              Only identifier types stated will be used to look up relevant entities in relationships. If not applicable, provide an empty array. |

### Return type

[ResourceListOfRelationship](ResourceListOfRelationship.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relationships for the specified custom entity. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustomEntityRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetCustomEntityRelationshipsWithHttpInfo(entityType, identifierScope, identifierType, identifierValue, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcustomentities"></a>
## ListCustomEntities

> PagedResourceListOfCustomEntityResponse ListCustomEntities(string entityType, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, int? limit = null, string? filter = null, List<string>? sortBy = null, string? page = null, List<string>? relatedEntityPropertyKeys = null, List<string>? relationshipDefinitionIds = null, List<string>? propertyKeys = null)

ListCustomEntities: List Custom Entities of the specified entityType.

List all the Custom Entities matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var page = "page_example";  // string? (optional)
var relatedEntityPropertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfCustomEntityResponse result = apiInstance.ListCustomEntities(entityType, effectiveAt, asAt, limit, filter, sortBy, page, relatedEntityPropertyKeys, relationshipDefinitionIds, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of Custom Entity to list. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the entities. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the entities. Defaults to returning the latest version              of each portfolio if not specified. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing entities; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **relatedEntityPropertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from any domain that supports relationships              to decorate onto related entities. These must take the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the entities in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;CustomEntity&#39; domain to decorate onto              the custom entities of any type supported by that property (defined within the property definition CustomEntityTypes).              These must have the format {domain}/{scope}/{code}, for example &#39;CustomEntity/someScope/id&#39;. |

### Return type

[PagedResourceListOfCustomEntityResponse](PagedResourceListOfCustomEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List custom entities of the specified entityType. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCustomEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCustomEntityResponse> response = apiInstance.ListCustomEntitiesWithHttpInfo(entityType, effectiveAt, asAt, limit, filter, sortBy, page, relatedEntityPropertyKeys, relationshipDefinitionIds, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchcustomentityaccessmetadata"></a>
## PatchCustomEntityAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; PatchCustomEntityAccessMetadata(string entityType, string identifierType, string identifierValue, string identifierScope, List<AccessMetadataOperation> accessMetadataOperation, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] PatchCustomEntityAccessMetadata: Patch Access Metadata rules for a Custom Entity.

Patch Custom Entity Access Metadata Rules in a single scope.  The behaviour is defined by the JSON Patch specification.                Currently only 'add' is a supported operation on the patch document    Currently only valid metadata keys are supported paths on the patch document                The response will return any affected Custom Entity Access Metadata rules or a failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var identifierScope = "identifierScope_example";  // string
var accessMetadataOperation = new List<AccessMetadataOperation>(); // List<AccessMetadataOperation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.PatchCustomEntityAccessMetadata(entityType, identifierType, identifierValue, identifierScope, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **accessMetadataOperation** | [List&lt;AccessMetadataOperation&gt;](AccessMetadataOperation.md) | body | **required** | The Json Patch document |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which the Access Metadata will be effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective datetime until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; datetime of the Access Metadata |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the CustomEntity or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchCustomEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.PatchCustomEntityAccessMetadataWithHttpInfo(entityType, identifierType, identifierValue, identifierScope, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcustomentities"></a>
## UpsertCustomEntities

> UpsertCustomEntitiesResponse UpsertCustomEntities(string entityType, string successMode, Dictionary<string, CustomEntityRequest> requestBody)

[EARLY ACCESS] UpsertCustomEntities: Batch upsert instances of Custom Entities

Note: If using partial failure modes, then it is important to check the response body for failures as any failures will still return a 200 status code

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var successMode = "successMode_example";  // string
var requestBody = new Dictionary<string, CustomEntityRequest>(); // Dictionary<string, CustomEntityRequest>
UpsertCustomEntitiesResponse result = apiInstance.UpsertCustomEntities(entityType, successMode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity to be created. An entityType can be created using the \&quot;CreateCustomEntityDefinition\&quot; endpoint for CustomEntityDefinitions. |
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial |
| **requestBody** | [Dictionary&lt;string, CustomEntityRequest&gt;](CustomEntityRequest.md) | body | **required** | The payload describing the Custom Entity instances |

### Return type

[UpsertCustomEntitiesResponse](UpsertCustomEntitiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted custom entity instance |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCustomEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertCustomEntitiesResponse> response = apiInstance.UpsertCustomEntitiesWithHttpInfo(entityType, successMode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcustomentity"></a>
## UpsertCustomEntity

> CustomEntityResponse UpsertCustomEntity(string entityType, CustomEntityRequest customEntityRequest)

UpsertCustomEntity: Upsert a Custom Entity instance

Insert the Custom Entity if it does not exist or update the Custom Entity with the supplied state if it does exist.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var customEntityRequest = new CustomEntityRequest(); // CustomEntityRequest
CustomEntityResponse result = apiInstance.UpsertCustomEntity(entityType, customEntityRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity to be created. An entityType can be created using the \&quot;CreateCustomEntityDefinition\&quot; endpoint for CustomEntityDefinitions. |
| **customEntityRequest** | [CustomEntityRequest](CustomEntityRequest.md) | body | **required** | The payload describing the Custom Entity instance. |

### Return type

[CustomEntityResponse](CustomEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The upserted custom entity instance |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCustomEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomEntityResponse> response = apiInstance.UpsertCustomEntityWithHttpInfo(entityType, customEntityRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertcustomentityaccessmetadata"></a>
## UpsertCustomEntityAccessMetadata

> List&lt;AccessMetadataValue&gt; UpsertCustomEntityAccessMetadata(string entityType, string identifierType, string identifierValue, string metadataKey, string identifierScope, UpsertCustomEntityAccessMetadataRequest upsertCustomEntityAccessMetadataRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] UpsertCustomEntityAccessMetadata: Upsert a Custom Entity Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID.

Update or insert one Custom Entity Access Metadata entry in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Custom Entity Access Metadata rule or failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomEntitiesApi>();
var entityType = "entityType_example";  // string
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var metadataKey = "metadataKey_example";  // string
var identifierScope = "identifierScope_example";  // string
var upsertCustomEntityAccessMetadataRequest = new UpsertCustomEntityAccessMetadataRequest(); // UpsertCustomEntityAccessMetadataRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<AccessMetadataValue> result = apiInstance.UpsertCustomEntityAccessMetadata(entityType, identifierType, identifierValue, metadataKey, identifierScope, upsertCustomEntityAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The type of the Custom Entity. |
| **identifierType** | **string** | path | **required** | An identifier type attached to the Custom Entity instance. |
| **identifierValue** | **string** | path | **required** | The identifier value. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **identifierScope** | **string** | query | **required** | The identifier scope. |
| **upsertCustomEntityAccessMetadataRequest** | [UpsertCustomEntityAccessMetadataRequest](UpsertCustomEntityAccessMetadataRequest.md) | body | **required** | The Custom Entity Access Metadata entry to upsert |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which the Access Metadata will be effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective datetime until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; datetime of the Access Metadata |

### Return type

[List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the CustomEntity or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertCustomEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AccessMetadataValue>> response = apiInstance.UpsertCustomEntityAccessMetadataWithHttpInfo(entityType, identifierType, identifierValue, metadataKey, identifierScope, upsertCustomEntityAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

