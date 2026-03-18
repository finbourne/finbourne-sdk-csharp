# Finbourne.Sdk.Lusid.Api.LegalEntitiesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteLegalEntity**](#deletelegalentity) | **DELETE** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}` | DeleteLegalEntity: Delete Legal Entity |
| [**DeleteLegalEntityAccessMetadata**](#deletelegalentityaccessmetadata) | **DELETE** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/metadata/{metadataKey}` | DeleteLegalEntityAccessMetadata: Delete a Legal Entity Access Metadata entry |
| [**DeleteLegalEntityIdentifiers**](#deletelegalentityidentifiers) | **DELETE** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/identifiers` | [EARLY ACCESS] DeleteLegalEntityIdentifiers: Delete Legal Entity Identifiers |
| [**DeleteLegalEntityProperties**](#deletelegalentityproperties) | **DELETE** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/properties` | [EARLY ACCESS] DeleteLegalEntityProperties: Delete Legal Entity Properties |
| [**GetAllLegalEntityAccessMetadata**](#getalllegalentityaccessmetadata) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/metadata` | GetAllLegalEntityAccessMetadata: Get Access Metadata rules for a Legal Entity |
| [**GetLegalEntity**](#getlegalentity) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}` | GetLegalEntity: Get Legal Entity |
| [**GetLegalEntityAccessMetadataByKey**](#getlegalentityaccessmetadatabykey) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] GetLegalEntityAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Legal Entity |
| [**GetLegalEntityPropertyTimeSeries**](#getlegalentitypropertytimeseries) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/properties/time-series` | GetLegalEntityPropertyTimeSeries: Get Legal Entity Property Time Series |
| [**GetLegalEntityRelations**](#getlegalentityrelations) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/relations` | GetLegalEntityRelations: Get Relations for Legal Entity |
| [**GetLegalEntityRelationships**](#getlegalentityrelationships) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/relationships` | GetLegalEntityRelationships: Get Relationships for Legal Entity |
| [**ListAllLegalEntities**](#listalllegalentities) | **GET** `/api/api/legalentities` | ListAllLegalEntities: List Legal Entities |
| [**ListLegalEntities**](#listlegalentities) | **GET** `/api/api/legalentities/{idTypeScope}/{idTypeCode}` | ListLegalEntities: List Legal Entities |
| [**PatchLegalEntityAccessMetadata**](#patchlegalentityaccessmetadata) | **PATCH** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/metadata` | [EARLY ACCESS] PatchLegalEntityAccessMetadata: Patch Access Metadata rules for a Legal Entity. |
| [**SetLegalEntityIdentifiers**](#setlegalentityidentifiers) | **POST** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/identifiers` | [EARLY ACCESS] SetLegalEntityIdentifiers: Set Legal Entity Identifiers |
| [**SetLegalEntityProperties**](#setlegalentityproperties) | **POST** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/properties` | SetLegalEntityProperties: Set Legal Entity Properties |
| [**UpsertLegalEntities**](#upsertlegalentities) | **POST** `/api/api/legalentities/$batchUpsert` | [EARLY ACCESS] UpsertLegalEntities: Batch upsert Legal Entities |
| [**UpsertLegalEntity**](#upsertlegalentity) | **POST** `/api/api/legalentities` | UpsertLegalEntity: Upsert Legal Entity |
| [**UpsertLegalEntityAccessMetadata**](#upsertlegalentityaccessmetadata) | **PUT** `/api/api/legalentities/{idTypeScope}/{idTypeCode}/{code}/metadata/{metadataKey}` | UpsertLegalEntityAccessMetadata: Upsert a Legal Entity Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<LegalEntitiesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
```

---

<a id="deletelegalentity"></a>
## DeleteLegalEntity

> DeletedEntityResponse DeleteLegalEntity(string idTypeScope, string idTypeCode, string code)

DeleteLegalEntity: Delete Legal Entity

Delete a legal entity. Deletion will be valid from the legal entity's creation datetime.  This means that the legal entity will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteLegalEntity(idTypeScope, idTypeCode, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | The scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | The code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with defined              identifier type uniquely identifies the legal entity to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting legal entity. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteLegalEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteLegalEntityWithHttpInfo(idTypeScope, idTypeCode, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletelegalentityaccessmetadata"></a>
## DeleteLegalEntityAccessMetadata

> DeletedEntityResponse DeleteLegalEntityAccessMetadata(string idTypeScope, string idTypeCode, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

DeleteLegalEntityAccessMetadata: Delete a Legal Entity Access Metadata entry

Deletes the Legal Entity Access Metadata entry that exactly matches the provided identifier parts.    It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.DeleteLegalEntityAccessMetadata(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the Legal Entity identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the Legal Entity identifier. |
| **code** | **string** | path | **required** | Code of the Legal Entity under specified identifier type&#39;s scope and code. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date to delete at, if this is not supplied, it will delete all data found |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the delete is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Access Metadata with the given metadataKey has been deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteLegalEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteLegalEntityAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletelegalentityidentifiers"></a>
## DeleteLegalEntityIdentifiers

> DeletedEntityResponse DeleteLegalEntityIdentifiers(string idTypeScope, string idTypeCode, string code, List<string> propertyKeys, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeleteLegalEntityIdentifiers: Delete Legal Entity Identifiers

Delete identifiers that belong to the given property keys of the legal entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteLegalEntityIdentifiers(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | The property keys of the identifiers to delete. These take the format              {domain}/{scope}/{code} e.g. \&quot;LegalEntity/CreditAgency/Identifier\&quot;. Each property must be from the \&quot;LegalEntity\&quot; domain. Identifiers or identifiers not specified in request will not be changed. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete the identifiers. Defaults to the current LUSID system datetime if not specified.              Must not include an effective datetime if identifiers are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the identifiers were deleted from the specified legal entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteLegalEntityIdentifiersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteLegalEntityIdentifiersWithHttpInfo(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletelegalentityproperties"></a>
## DeleteLegalEntityProperties

> DeletedEntityResponse DeleteLegalEntityProperties(string idTypeScope, string idTypeCode, string code, List<string> propertyKeys, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeleteLegalEntityProperties: Delete Legal Entity Properties

Delete all properties that belong to the given property keys of the legal entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteLegalEntityProperties(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | The property keys of the legal entities properties to delete. These take the format              {domain}/{scope}/{code} e.g. \&quot;LegalEntity/CompanyDetails/Role\&quot;. Each property must be from the \&quot;LegalEntity\&quot; domain. Properties or identifiers not specified in request will not be changed. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete time-variant properties from.              The property must exist at the specified &#39;effectiveAt&#39; datetime. If the &#39;effectiveAt&#39; is not provided or is              before the time-variant property exists then a failure is returned. Do not specify this parameter if any of              the properties to delete are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the properties were deleted from the specified legal entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteLegalEntityPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteLegalEntityPropertiesWithHttpInfo(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getalllegalentityaccessmetadata"></a>
## GetAllLegalEntityAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; GetAllLegalEntityAccessMetadata(string idTypeScope, string idTypeCode, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

GetAllLegalEntityAccessMetadata: Get Access Metadata rules for a Legal Entity

Pass the Scope and Code of the Legal Entity identifier along with the Legal Entity code parameter to retrieve the associated Access Metadata

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.GetAllLegalEntityAccessMetadata(idTypeScope, idTypeCode, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the Legal Entity identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the Legal Entity identifier. |
| **code** | **string** | path | **required** | Code of the Legal Entity under specified identifier type&#39;s scope and code. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the Access Metadata |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Access Metadata |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the Legal Entity or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllLegalEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.GetAllLegalEntityAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegalentity"></a>
## GetLegalEntity

> LegalEntity GetLegalEntity(string idTypeScope, string idTypeCode, string code, List<string>? propertyKeys = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? relationshipDefinitionIds = null)

GetLegalEntity: Get Legal Entity

Retrieve the definition of a legal entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>?(); // List<string>? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
LegalEntity result = apiInstance.GetLegalEntity(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt, asAt, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys or identifier types (as property keys) from the \&quot;LegalEntity\&quot; domain              to include for found legal entity, or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;LegalEntity/ContactDetails/Address\&quot;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the legal entity. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the legal entity. Defaults to return the latest version of the legal entity if not specified. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the legal entity in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[LegalEntity](LegalEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested legal entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegalEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LegalEntity> response = apiInstance.GetLegalEntityWithHttpInfo(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt, asAt, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegalentityaccessmetadatabykey"></a>
## GetLegalEntityAccessMetadataByKey

> List&lt;AccessMetadataValue&gt; GetLegalEntityAccessMetadataByKey(string idTypeScope, string idTypeCode, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetLegalEntityAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Legal Entity

Get a specific Legal Entity Access Metadata by specifying the corresponding identifier parts and Legal Entity code                No matching will be performed through this endpoint. To retrieve an entry, it is necessary to specify, exactly, the identifier of the entry

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<AccessMetadataValue> result = apiInstance.GetLegalEntityAccessMetadataByKey(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the Legal Entity identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the Legal Entity identifier. |
| **code** | **string** | path | **required** | Code of the Legal Entity under specified identifier type&#39;s scope and code. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the Access Metadata |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Access Metadata |

### Return type

[List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Legal Entity access metadata filtered by metadataKey or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegalEntityAccessMetadataByKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AccessMetadataValue>> response = apiInstance.GetLegalEntityAccessMetadataByKeyWithHttpInfo(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegalentitypropertytimeseries"></a>
## GetLegalEntityPropertyTimeSeries

> ResourceListOfPropertyInterval GetLegalEntityPropertyTimeSeries(string idTypeScope, string idTypeCode, string code, string propertyKey, DateTimeOffset? asAt = null, string? filter = null, string? page = null, int? limit = null)

GetLegalEntityPropertyTimeSeries: Get Legal Entity Property Time Series

List the complete time series of a legal entity property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKey = "propertyKey_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfPropertyInterval result = apiInstance.GetLegalEntityPropertyTimeSeries(idTypeScope, idTypeCode, code, propertyKey, asAt, filter, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely identifies the legal entity. |
| **propertyKey** | **string** | query | **required** | The property key of the property that will have its history shown. These must be in the format {domain}/{scope}/{code} e.g. \&quot;LegalEntity/ContactDetails/Address\&quot;.              Each property must be from the \&quot;LegalEntity\&quot; domain. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the person&#39;s property history. Defaults to return the current datetime if not supplied. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
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
<summary>Using the GetLegalEntityPropertyTimeSeriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyInterval> response = apiInstance.GetLegalEntityPropertyTimeSeriesWithHttpInfo(idTypeScope, idTypeCode, code, propertyKey, asAt, filter, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegalentityrelations"></a>
## GetLegalEntityRelations

> ResourceListOfRelation GetLegalEntityRelations(string idTypeScope, string idTypeCode, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

GetLegalEntityRelations: Get Relations for Legal Entity

Get relations for the specified Legal Entity

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelation result = apiInstance.GetLegalEntityRelations(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get relations. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the legal entity&#39;s relations. Defaults to return the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the relations. Users should provide null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifiers types (as property keys) used for referencing Persons or Legal Entities. These take the format              {domain}/{scope}/{code} e.g. \&quot;Person/CompanyDetails/Role\&quot;. They must be from the \&quot;Person\&quot; or \&quot;LegalEntity\&quot; domain.              Only identifier types stated will be used to look up relevant entities in relations. If not applicable, provide an empty array. |

### Return type

[ResourceListOfRelation](ResourceListOfRelation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relations for the specific legal entity. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegalEntityRelationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelation> response = apiInstance.GetLegalEntityRelationsWithHttpInfo(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getlegalentityrelationships"></a>
## GetLegalEntityRelationships

> ResourceListOfRelationship GetLegalEntityRelationships(string idTypeScope, string idTypeCode, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

GetLegalEntityRelationships: Get Relationships for Legal Entity

Get Relationships for the specified Legal Entity

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelationship result = apiInstance.GetLegalEntityRelationships(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity&#39;s identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity&#39;s identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get relationships. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relationships. Defaults to return the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter relationships. Users should provide null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifier types (as property keys) used for referencing Persons or Legal Entities.              These can be specified from the &#39;Person&#39; or &#39;LegalEntity&#39; domains and have the format {domain}/{scope}/{code}, for example              &#39;Person/CompanyDetails/Role&#39;. An Empty array may be used to return all related Entities. |

### Return type

[ResourceListOfRelationship](ResourceListOfRelationship.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relationships for the specified legal entity. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetLegalEntityRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetLegalEntityRelationshipsWithHttpInfo(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listalllegalentities"></a>
## ListAllLegalEntities

> ResourceListOfLegalEntity ListAllLegalEntities(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

ListAllLegalEntities: List Legal Entities

List all legal entities which the user is entitled to see.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
ResourceListOfLegalEntity result = apiInstance.ListAllLegalEntities(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the legal entities. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the legal entities. Defaults to return the latest version              of each legal entities if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing legal entities from a previous call to list legal entities. This  value is returned from the previous call. If a pagination token is provided the filter, effectiveAt, sortBy  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 5000 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys or identifier types (as property keys) from the \&quot;LegalEntity\&quot; domain              to include for each legal entity, or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;LegalEntity/ContactDetails/Address\&quot;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto each portfolio in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[ResourceListOfLegalEntity](ResourceListOfLegalEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | All existing Legal Entities |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAllLegalEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfLegalEntity> response = apiInstance.ListAllLegalEntitiesWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listlegalentities"></a>
## ListLegalEntities

> PagedResourceListOfLegalEntity ListLegalEntities(string idTypeScope, string idTypeCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

ListLegalEntities: List Legal Entities

List legal entities which has identifier of specific identifier type's scope and code, and satisfies filter criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
PagedResourceListOfLegalEntity result = apiInstance.ListLegalEntities(idTypeScope, idTypeCode, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the people. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the people. Defaults to return the latest version              of each people if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing legal entities from a previous call to list legal entities. This  value is returned from the previous call. If a pagination token is provided the filter, effectiveAt, sortBy  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys or identifier types (as property keys) from the \&quot;LegalEntity\&quot; domain              to include for each legal entity, or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;LegalEntity/ContactDetails/Address\&quot;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto each portfolio in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[PagedResourceListOfLegalEntity](PagedResourceListOfLegalEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Legal Entities with specified identifier type |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListLegalEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfLegalEntity> response = apiInstance.ListLegalEntitiesWithHttpInfo(idTypeScope, idTypeCode, effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchlegalentityaccessmetadata"></a>
## PatchLegalEntityAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; PatchLegalEntityAccessMetadata(string idTypeScope, string idTypeCode, string code, List<AccessMetadataOperation> accessMetadataOperation, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] PatchLegalEntityAccessMetadata: Patch Access Metadata rules for a Legal Entity.

Patch Legal Entity Access Metadata Rules in a single scope.  The behaviour is defined by the JSON Patch specification.                Currently only 'add' is a supported operation on the patch document    Currently only valid metadata keys are supported paths on the patch document                The response will return any affected Legal Entity Access Metadata rules or a failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var accessMetadataOperation = new List<AccessMetadataOperation>(); // List<AccessMetadataOperation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.PatchLegalEntityAccessMetadata(idTypeScope, idTypeCode, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the Legal Entity identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the Legal Entity identifier. |
| **code** | **string** | path | **required** | Code of the Legal Entity under specified identifier type&#39;s scope and code. |
| **accessMetadataOperation** | [List&lt;AccessMetadataOperation&gt;](AccessMetadataOperation.md) | body | **required** | The Json Patch document |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to upsert the Access Metadata |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective datetime until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; datetime of the Access Metadata |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully patched items. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchLegalEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.PatchLegalEntityAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setlegalentityidentifiers"></a>
## SetLegalEntityIdentifiers

> LegalEntity SetLegalEntityIdentifiers(string idTypeScope, string idTypeCode, string code, SetLegalEntityIdentifiersRequest setLegalEntityIdentifiersRequest)

[EARLY ACCESS] SetLegalEntityIdentifiers: Set Legal Entity Identifiers

Set identifiers of the Legal Entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var setLegalEntityIdentifiersRequest = new SetLegalEntityIdentifiersRequest(); // SetLegalEntityIdentifiersRequest
LegalEntity result = apiInstance.SetLegalEntityIdentifiers(idTypeScope, idTypeCode, code, setLegalEntityIdentifiersRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **setLegalEntityIdentifiersRequest** | [SetLegalEntityIdentifiersRequest](SetLegalEntityIdentifiersRequest.md) | body | **required** | Request containing identifiers to set for the legal entity. Identifiers not specified in request will not be changed. |

### Return type

[LegalEntity](LegalEntity.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Legal Entity with updated identifiers |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetLegalEntityIdentifiersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LegalEntity> response = apiInstance.SetLegalEntityIdentifiersWithHttpInfo(idTypeScope, idTypeCode, code, setLegalEntityIdentifiersRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setlegalentityproperties"></a>
## SetLegalEntityProperties

> LegalEntity SetLegalEntityProperties(string idTypeScope, string idTypeCode, string code, SetLegalEntityPropertiesRequest setLegalEntityPropertiesRequest)

SetLegalEntityProperties: Set Legal Entity Properties

Set properties of the legal entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var setLegalEntityPropertiesRequest = new SetLegalEntityPropertiesRequest(); // SetLegalEntityPropertiesRequest
LegalEntity result = apiInstance.SetLegalEntityProperties(idTypeScope, idTypeCode, code, setLegalEntityPropertiesRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the legal entity identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the legal entity identifier type. |
| **code** | **string** | path | **required** | Code of the legal entity under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the legal entity. |
| **setLegalEntityPropertiesRequest** | [SetLegalEntityPropertiesRequest](SetLegalEntityPropertiesRequest.md) | body | **required** | Request containing properties to set for the legal entity. Properties not specified in request will not be changed. |

### Return type

[LegalEntity](LegalEntity.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Legal Entity with updated properties |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetLegalEntityPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LegalEntity> response = apiInstance.SetLegalEntityPropertiesWithHttpInfo(idTypeScope, idTypeCode, code, setLegalEntityPropertiesRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertlegalentities"></a>
## UpsertLegalEntities

> UpsertLegalEntitiesResponse UpsertLegalEntities(string successMode, Dictionary<string, UpsertLegalEntityRequest> requestBody)

[EARLY ACCESS] UpsertLegalEntities: Batch upsert Legal Entities

Creates or updates a collection of Legal Entities

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var successMode = "successMode_example";  // string
var requestBody = new Dictionary<string, UpsertLegalEntityRequest>(); // Dictionary<string, UpsertLegalEntityRequest>
UpsertLegalEntitiesResponse result = apiInstance.UpsertLegalEntities(successMode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial |
| **requestBody** | [Dictionary&lt;string, UpsertLegalEntityRequest&gt;](UpsertLegalEntityRequest.md) | body | **required** | A collection of requests to create or update Legal Entities. |

### Return type

[UpsertLegalEntitiesResponse](UpsertLegalEntitiesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successfully created or updated legal entities along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertLegalEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertLegalEntitiesResponse> response = apiInstance.UpsertLegalEntitiesWithHttpInfo(successMode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertlegalentity"></a>
## UpsertLegalEntity

> LegalEntity UpsertLegalEntity(UpsertLegalEntityRequest upsertLegalEntityRequest)

UpsertLegalEntity: Upsert Legal Entity

Create or update a legal entity

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var upsertLegalEntityRequest = new UpsertLegalEntityRequest(); // UpsertLegalEntityRequest
LegalEntity result = apiInstance.UpsertLegalEntity(upsertLegalEntityRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertLegalEntityRequest** | [UpsertLegalEntityRequest](UpsertLegalEntityRequest.md) | body | **required** | Request to create or update a legal entity. |

### Return type

[LegalEntity](LegalEntity.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created or updated legal entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertLegalEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<LegalEntity> response = apiInstance.UpsertLegalEntityWithHttpInfo(upsertLegalEntityRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertlegalentityaccessmetadata"></a>
## UpsertLegalEntityAccessMetadata

> ResourceListOfAccessMetadataValueOf UpsertLegalEntityAccessMetadata(string idTypeScope, string idTypeCode, string code, string metadataKey, UpsertLegalEntityAccessMetadataRequest upsertLegalEntityAccessMetadataRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

UpsertLegalEntityAccessMetadata: Upsert a Legal Entity Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID.

Update or insert one Legal Entity Access Metadata entry in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Legal Entity Access Metadata rule or failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<LegalEntitiesApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var upsertLegalEntityAccessMetadataRequest = new UpsertLegalEntityAccessMetadataRequest(); // UpsertLegalEntityAccessMetadataRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfAccessMetadataValueOf result = apiInstance.UpsertLegalEntityAccessMetadata(idTypeScope, idTypeCode, code, metadataKey, upsertLegalEntityAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the Legal Entity identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the Legal Entity identifier. |
| **code** | **string** | path | **required** | Code of the Legal Entity under specified identifier type&#39;s scope and code. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **upsertLegalEntityAccessMetadataRequest** | [UpsertLegalEntityAccessMetadataRequest](UpsertLegalEntityAccessMetadataRequest.md) | body | **required** | The Legal Entity Access Metadata entry to upsert |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to upsert the Access Metadata |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective datetime until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; datetime of the Access Metadata |

### Return type

[ResourceListOfAccessMetadataValueOf](ResourceListOfAccessMetadataValueOf.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted item or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertLegalEntityAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAccessMetadataValueOf> response = apiInstance.UpsertLegalEntityAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, metadataKey, upsertLegalEntityAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

