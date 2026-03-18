# Finbourne.Sdk.Lusid.Api.PersonsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeletePerson**](#deleteperson) | **DELETE** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}` | DeletePerson: Delete person |
| [**DeletePersonAccessMetadata**](#deletepersonaccessmetadata) | **DELETE** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] DeletePersonAccessMetadata: Delete a Person Access Metadata entry |
| [**DeletePersonIdentifiers**](#deletepersonidentifiers) | **DELETE** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/identifiers` | [EARLY ACCESS] DeletePersonIdentifiers: Delete Person Identifiers |
| [**DeletePersonProperties**](#deletepersonproperties) | **DELETE** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/properties` | [EARLY ACCESS] DeletePersonProperties: Delete Person Properties |
| [**GetAllPersonAccessMetadata**](#getallpersonaccessmetadata) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/metadata` | [EARLY ACCESS] GetAllPersonAccessMetadata: Get Access Metadata rules for a Person |
| [**GetPerson**](#getperson) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}` | [EARLY ACCESS] GetPerson: Get Person |
| [**GetPersonAccessMetadataByKey**](#getpersonaccessmetadatabykey) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] GetPersonAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Person |
| [**GetPersonPropertyTimeSeries**](#getpersonpropertytimeseries) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/properties/time-series` | [EARLY ACCESS] GetPersonPropertyTimeSeries: Get Person Property Time Series |
| [**GetPersonRelations**](#getpersonrelations) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/relations` | [EARLY ACCESS] GetPersonRelations: Get Relations for Person |
| [**GetPersonRelationships**](#getpersonrelationships) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/relationships` | [EARLY ACCESS] GetPersonRelationships: Get Relationships for Person |
| [**ListAllPersons**](#listallpersons) | **GET** `/api/api/persons` | [EARLY ACCESS] ListAllPersons: List All Persons |
| [**ListPersons**](#listpersons) | **GET** `/api/api/persons/{idTypeScope}/{idTypeCode}` | [EARLY ACCESS] ListPersons: List Persons |
| [**PatchPersonAccessMetadata**](#patchpersonaccessmetadata) | **PATCH** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/metadata` | [EARLY ACCESS] PatchPersonAccessMetadata: Patch Access Metadata rules for a Person. |
| [**SetPersonIdentifiers**](#setpersonidentifiers) | **POST** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/identifiers` | [EARLY ACCESS] SetPersonIdentifiers: Set Person Identifiers |
| [**SetPersonProperties**](#setpersonproperties) | **POST** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/properties` | [EARLY ACCESS] SetPersonProperties: Set Person Properties |
| [**UpsertPerson**](#upsertperson) | **POST** `/api/api/persons` | UpsertPerson: Upsert Person |
| [**UpsertPersonAccessMetadata**](#upsertpersonaccessmetadata) | **PUT** `/api/api/persons/{idTypeScope}/{idTypeCode}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] UpsertPersonAccessMetadata: Upsert a Person Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID. |
| [**UpsertPersons**](#upsertpersons) | **POST** `/api/api/persons/$batchUpsert` | [EARLY ACCESS] UpsertPersons: Batch upsert Persons |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PersonsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
```

---

<a id="deleteperson"></a>
## DeletePerson

> DeletedEntityResponse DeletePerson(string idTypeScope, string idTypeCode, string code)

DeletePerson: Delete person

Delete a person. Deletion will be valid from the person's creation datetime.  This means that the person will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeletePerson(idTypeScope, idTypeCode, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | The scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | The code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type scope and code. This together with defined              identifier type uniquely identifies the person to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting person. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePersonWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePersonWithHttpInfo(idTypeScope, idTypeCode, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepersonaccessmetadata"></a>
## DeletePersonAccessMetadata

> DeletedEntityResponse DeletePersonAccessMetadata(string idTypeScope, string idTypeCode, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] DeletePersonAccessMetadata: Delete a Person Access Metadata entry

Deletes the Person Access Metadata entry that exactly matches the provided identifier parts.    It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.DeletePersonAccessMetadata(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. |
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
<summary>Using the DeletePersonAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePersonAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepersonidentifiers"></a>
## DeletePersonIdentifiers

> DeletedEntityResponse DeletePersonIdentifiers(string idTypeScope, string idTypeCode, string code, List<string> propertyKeys, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeletePersonIdentifiers: Delete Person Identifiers

Delete identifiers that belong to the given property keys of the person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeletePersonIdentifiers(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the person. |
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | The property keys of the identifiers to delete. These take the format              {domain}/{scope}/{code} e.g. \&quot;Person/CompanyDetails/Role\&quot;. Each property must be from the \&quot;Person\&quot; domain. Identifiers or identifiers not specified in request will not be changed. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete the identifiers. Defaults to the current LUSID system datetime if not specified.              Must not include an effective datetime if identifiers are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the identifiers were deleted from the specified person |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePersonIdentifiersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePersonIdentifiersWithHttpInfo(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepersonproperties"></a>
## DeletePersonProperties

> DeletedEntityResponse DeletePersonProperties(string idTypeScope, string idTypeCode, string code, List<string> propertyKeys, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeletePersonProperties: Delete Person Properties

Delete all properties that belong to the given property keys of the person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeletePersonProperties(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the person. |
| **propertyKeys** | [List&lt;string&gt;](string.md) | query | **required** | The property keys of the person&#39;s properties to delete. These take the format              {domain}/{scope}/{code} e.g. \&quot;Person/CompanyDetails/Role\&quot;. Each property must be from the \&quot;Person\&quot; domain. Properties or identifiers not specified in request will not be changed. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete time-variant properties from.              The property must exist at the specified &#39;effectiveAt&#39; datetime. If the &#39;effectiveAt&#39; is not provided or is              before the time-variant property exists then a failure is returned. Do not specify this parameter if any of              the properties to delete are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the properties were deleted from the specified person |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePersonPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePersonPropertiesWithHttpInfo(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallpersonaccessmetadata"></a>
## GetAllPersonAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; GetAllPersonAccessMetadata(string idTypeScope, string idTypeCode, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetAllPersonAccessMetadata: Get Access Metadata rules for a Person

Pass the Scope and Code of the Person identifier along with the person code parameter to retrieve the associated Access Metadata

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.GetAllPersonAccessMetadata(idTypeScope, idTypeCode, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. |
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
| **200** | The access metadata for the Person or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllPersonAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.GetAllPersonAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getperson"></a>
## GetPerson

> Person GetPerson(string idTypeScope, string idTypeCode, string code, List<string>? propertyKeys = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? relationshipDefinitionIds = null)

[EARLY ACCESS] GetPerson: Get Person

Retrieve the definition of a person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>?(); // List<string>? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
Person result = apiInstance.GetPerson(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt, asAt, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified scope and code. This together with stated identifier type uniquely              identifies the person. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Person\&quot; domain to decorate onto the person,               or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;Person/ContactDetails/Address\&quot;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the person. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the person. Defaults to return the latest version of the person if not specified. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the person in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[Person](Person.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested person definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPersonWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Person> response = apiInstance.GetPersonWithHttpInfo(idTypeScope, idTypeCode, code, propertyKeys, effectiveAt, asAt, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpersonaccessmetadatabykey"></a>
## GetPersonAccessMetadataByKey

> List&lt;AccessMetadataValue&gt; GetPersonAccessMetadataByKey(string idTypeScope, string idTypeCode, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetPersonAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Person

Get a specific Person Access Metadata by specifying the corresponding identifier parts and Person code                No matching will be performed through this endpoint. To retrieve an entry, it is necessary to specify, exactly, the identifier of the entry

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<AccessMetadataValue> result = apiInstance.GetPersonAccessMetadataByKey(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. |
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
| **200** | The successfully retrieved Person access metadata filtered by metadataKey or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPersonAccessMetadataByKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AccessMetadataValue>> response = apiInstance.GetPersonAccessMetadataByKeyWithHttpInfo(idTypeScope, idTypeCode, code, metadataKey, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpersonpropertytimeseries"></a>
## GetPersonPropertyTimeSeries

> ResourceListOfPropertyInterval GetPersonPropertyTimeSeries(string idTypeScope, string idTypeCode, string code, string propertyKey, DateTimeOffset? asAt = null, string? filter = null, string? page = null, int? limit = null)

[EARLY ACCESS] GetPersonPropertyTimeSeries: Get Person Property Time Series

List the complete time series of a person property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var propertyKey = "propertyKey_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfPropertyInterval result = apiInstance.GetPersonPropertyTimeSeries(idTypeScope, idTypeCode, code, propertyKey, asAt, filter, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely identifies the person. |
| **propertyKey** | **string** | query | **required** | The property key of the property that will have its history shown. These must be in the format {domain}/{scope}/{code} e.g. \&quot;Person/CompanyDetails/Role\&quot;.              Each property must be from the \&quot;Person\&quot; domain. |
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
<summary>Using the GetPersonPropertyTimeSeriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyInterval> response = apiInstance.GetPersonPropertyTimeSeriesWithHttpInfo(idTypeScope, idTypeCode, code, propertyKey, asAt, filter, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpersonrelations"></a>
## GetPersonRelations

> ResourceListOfRelation GetPersonRelations(string idTypeScope, string idTypeCode, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EARLY ACCESS] GetPersonRelations: Get Relations for Person

Get relations for the specified person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelation result = apiInstance.GetPersonRelations(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the person. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to get relations. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the person&#39;s relations. Defaults to return the latest LUSID AsAt time if not specified. |
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
| **200** | The relations for the specified person. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPersonRelationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelation> response = apiInstance.GetPersonRelationsWithHttpInfo(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpersonrelationships"></a>
## GetPersonRelationships

> ResourceListOfRelationship GetPersonRelationships(string idTypeScope, string idTypeCode, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EARLY ACCESS] GetPersonRelationships: Get Relationships for Person

Get relationships for the specified person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelationship result = apiInstance.GetPersonRelationships(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person&#39;s identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person&#39;s identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the person. |
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
| **200** | The relationships for the specified person. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPersonRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetPersonRelationshipsWithHttpInfo(idTypeScope, idTypeCode, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listallpersons"></a>
## ListAllPersons

> ResourceListOfPerson ListAllPersons(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

[EARLY ACCESS] ListAllPersons: List All Persons

List all persons which the user is entitled to see.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
ResourceListOfPerson result = apiInstance.ListAllPersons(effectiveAt, asAt, page, limit, filter, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the people. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the people. Defaults to return the latest version              of each people if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing persons from a previous call to list persons. This              value is returned from the previous call. If a pagination token is provided the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 5000 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to filter on the display name, use \&quot;displayName eq &#39;John&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Person\&quot; domain to decorate onto each person,               or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;Person/ContactDetails/Address\&quot;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the persons in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[ResourceListOfPerson](ResourceListOfPerson.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Existing people |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAllPersonsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPerson> response = apiInstance.ListAllPersonsWithHttpInfo(effectiveAt, asAt, page, limit, filter, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpersons"></a>
## ListPersons

> PagedResourceListOfPerson ListPersons(string idTypeScope, string idTypeCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

[EARLY ACCESS] ListPersons: List Persons

List persons which have identifiers of a specific identifier type's scope and code, and satisfies filter criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
PagedResourceListOfPerson result = apiInstance.ListPersons(idTypeScope, idTypeCode, effectiveAt, asAt, page, limit, filter, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the people. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the people. Defaults to return the latest version              of each people if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing persons from a previous call to list persons. This              value is returned from the previous call. If a pagination token is provided the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to filter on the LUPID, use \&quot;lusidPersonId eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Person\&quot; domain to decorate onto each person,               or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;Person/ContactDetails/Address\&quot;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the persons in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[PagedResourceListOfPerson](PagedResourceListOfPerson.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | People in specified scope |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPersonsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPerson> response = apiInstance.ListPersonsWithHttpInfo(idTypeScope, idTypeCode, effectiveAt, asAt, page, limit, filter, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchpersonaccessmetadata"></a>
## PatchPersonAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; PatchPersonAccessMetadata(string idTypeScope, string idTypeCode, string code, List<AccessMetadataOperation> accessMetadataOperation, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] PatchPersonAccessMetadata: Patch Access Metadata rules for a Person.

Patch Person Access Metadata Rules in a single scope.  The behaviour is defined by the JSON Patch specification.                Currently only 'add' is a supported operation on the patch document.    Currently only valid metadata keys are supported paths on the patch document.                The response will return any affected Person Access Metadata rules or a failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var accessMetadataOperation = new List<AccessMetadataOperation>(); // List<AccessMetadataOperation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.PatchPersonAccessMetadata(idTypeScope, idTypeCode, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. |
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
<summary>Using the PatchPersonAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.PatchPersonAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setpersonidentifiers"></a>
## SetPersonIdentifiers

> Person SetPersonIdentifiers(string idTypeScope, string idTypeCode, string code, SetPersonIdentifiersRequest setPersonIdentifiersRequest)

[EARLY ACCESS] SetPersonIdentifiers: Set Person Identifiers

Set identifiers of the person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var setPersonIdentifiersRequest = new SetPersonIdentifiersRequest(); // SetPersonIdentifiersRequest
Person result = apiInstance.SetPersonIdentifiers(idTypeScope, idTypeCode, code, setPersonIdentifiersRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the person. |
| **setPersonIdentifiersRequest** | [SetPersonIdentifiersRequest](SetPersonIdentifiersRequest.md) | body | **required** | Request containing identifiers to set for the person. Identifiers not specified in request will not be changed. |

### Return type

[Person](Person.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Person with updated identifiers. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPersonIdentifiersWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Person> response = apiInstance.SetPersonIdentifiersWithHttpInfo(idTypeScope, idTypeCode, code, setPersonIdentifiersRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setpersonproperties"></a>
## SetPersonProperties

> Person SetPersonProperties(string idTypeScope, string idTypeCode, string code, SetPersonPropertiesRequest setPersonPropertiesRequest)

[EARLY ACCESS] SetPersonProperties: Set Person Properties

Set properties of the person.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var setPersonPropertiesRequest = new SetPersonPropertiesRequest(); // SetPersonPropertiesRequest
Person result = apiInstance.SetPersonProperties(idTypeScope, idTypeCode, code, setPersonPropertiesRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier type. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier type. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. This together with stated identifier type uniquely              identifies the person. |
| **setPersonPropertiesRequest** | [SetPersonPropertiesRequest](SetPersonPropertiesRequest.md) | body | **required** | Request containing properties to set for the person. Properties not specified in request will not be changed. |

### Return type

[Person](Person.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Person with updated properties or identifiers. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPersonPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Person> response = apiInstance.SetPersonPropertiesWithHttpInfo(idTypeScope, idTypeCode, code, setPersonPropertiesRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertperson"></a>
## UpsertPerson

> Person UpsertPerson(UpsertPersonRequest upsertPersonRequest)

UpsertPerson: Upsert Person

Create or update a new person under the specified scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var upsertPersonRequest = new UpsertPersonRequest(); // UpsertPersonRequest
Person result = apiInstance.UpsertPerson(upsertPersonRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **upsertPersonRequest** | [UpsertPersonRequest](UpsertPersonRequest.md) | body | **required** | Request to create or update a person. |

### Return type

[Person](Person.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created or updated person |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPersonWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Person> response = apiInstance.UpsertPersonWithHttpInfo(upsertPersonRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertpersonaccessmetadata"></a>
## UpsertPersonAccessMetadata

> ResourceListOfAccessMetadataValueOf UpsertPersonAccessMetadata(string idTypeScope, string idTypeCode, string code, string metadataKey, UpsertPersonAccessMetadataRequest upsertPersonAccessMetadataRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] UpsertPersonAccessMetadata: Upsert a Person Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID.

Update or insert one Person Access Metadata entry in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Person Access Metadata rule or failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var idTypeScope = "idTypeScope_example";  // string
var idTypeCode = "idTypeCode_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var upsertPersonAccessMetadataRequest = new UpsertPersonAccessMetadataRequest(); // UpsertPersonAccessMetadataRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfAccessMetadataValueOf result = apiInstance.UpsertPersonAccessMetadata(idTypeScope, idTypeCode, code, metadataKey, upsertPersonAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **idTypeScope** | **string** | path | **required** | Scope of the person identifier. |
| **idTypeCode** | **string** | path | **required** | Code of the person identifier. |
| **code** | **string** | path | **required** | Code of the person under specified identifier type&#39;s scope and code. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **upsertPersonAccessMetadataRequest** | [UpsertPersonAccessMetadataRequest](UpsertPersonAccessMetadataRequest.md) | body | **required** | The Person Access Metadata entry to upsert |
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
<summary>Using the UpsertPersonAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAccessMetadataValueOf> response = apiInstance.UpsertPersonAccessMetadataWithHttpInfo(idTypeScope, idTypeCode, code, metadataKey, upsertPersonAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertpersons"></a>
## UpsertPersons

> UpsertPersonsResponse UpsertPersons(string successMode, Dictionary<string, UpsertPersonRequest> requestBody)

[EARLY ACCESS] UpsertPersons: Batch upsert Persons

Create or updates a collection of person(s).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PersonsApi>();
var successMode = "successMode_example";  // string
var requestBody = new Dictionary<string, UpsertPersonRequest>(); // Dictionary<string, UpsertPersonRequest>
UpsertPersonsResponse result = apiInstance.UpsertPersons(successMode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial |
| **requestBody** | [Dictionary&lt;string, UpsertPersonRequest&gt;](UpsertPersonRequest.md) | body | **required** | A collection of requests to create or update Person(s). |

### Return type

[UpsertPersonsResponse](UpsertPersonsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created or updated person(s) |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPersonsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertPersonsResponse> response = apiInstance.UpsertPersonsWithHttpInfo(successMode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

