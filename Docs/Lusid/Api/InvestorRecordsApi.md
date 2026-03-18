# Finbourne.Sdk.Lusid.Api.InvestorRecordsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteInvestorRecord**](#deleteinvestorrecord) | **DELETE** `/api/api/investorrecords/{identifierType}/{identifierValue}` | [EARLY ACCESS] DeleteInvestorRecord: Delete Investor Record |
| [**DeleteInvestorRecordAccessMetadata**](#deleteinvestorrecordaccessmetadata) | **DELETE** `/api/api/investorrecords/{identifierType}/{identifierValue}/metadata/{metadataKey}` | [EARLY ACCESS] DeleteInvestorRecordAccessMetadata: Delete an Investor Record Access Metadata entry. |
| [**GetAllInvestorRecordAccessMetadata**](#getallinvestorrecordaccessmetadata) | **GET** `/api/api/investorrecords/{identifierType}/{identifierValue}/metadata` | [EARLY ACCESS] GetAllInvestorRecordAccessMetadata: Get Access Metadata rules for an Investor Record. |
| [**GetInvestorRecord**](#getinvestorrecord) | **GET** `/api/api/investorrecords/{identifierType}/{identifierValue}` | [EARLY ACCESS] GetInvestorRecord: Get Investor Record |
| [**GetInvestorRecordRelationships**](#getinvestorrecordrelationships) | **GET** `/api/api/investorrecords/{identifierType}/{identifierValue}/relationships` | [EARLY ACCESS] GetInvestorRecordRelationships: Get Investor Record relationships |
| [**ListAllInvestorRecords**](#listallinvestorrecords) | **GET** `/api/api/investorrecords` | [EARLY ACCESS] ListAllInvestorRecords: List Investor Records |
| [**PatchInvestorRecordAccessMetadata**](#patchinvestorrecordaccessmetadata) | **PATCH** `/api/api/investorrecords/{identifierType}/{identifierValue}/metadata` | [EARLY ACCESS] PatchInvestorRecordAccessMetadata: Patch Access Metadata rules for an Investor Record. |
| [**UpsertInvestorRecords**](#upsertinvestorrecords) | **POST** `/api/api/investorrecords/$batchUpsert` | [EARLY ACCESS] UpsertInvestorRecords: Upsert investor records |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<InvestorRecordsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
```

---

<a id="deleteinvestorrecord"></a>
## DeleteInvestorRecord

> DeletedEntityResponse DeleteInvestorRecord(string identifierType, string identifierValue, string scope, string identifierScope)

[EARLY ACCESS] DeleteInvestorRecord: Delete Investor Record

Delete an investor record. Deletion will be valid from the investor record's creation datetime.  This means that the investor record will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var scope = "scope_example";  // string
var identifierScope = "identifierScope_example";  // string
DeletedEntityResponse result = apiInstance.DeleteInvestorRecord(identifierType, identifierValue, scope, identifierScope);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | Code of the investor record identifier type. |
| **identifierValue** | **string** | path | **required** | Code of the investor record under specified identifier type&#39;s scope and code. |
| **scope** | **string** | query | **required** | The scope of the investor record entity. |
| **identifierScope** | **string** | query | **required** | Scope of the investor record identifier type. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting investor record. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInvestorRecordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteInvestorRecordWithHttpInfo(identifierType, identifierValue, scope, identifierScope);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinvestorrecordaccessmetadata"></a>
## DeleteInvestorRecordAccessMetadata

> DeletedEntityResponse DeleteInvestorRecordAccessMetadata(string identifierType, string identifierValue, string metadataKey, string scope, string identifierScope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] DeleteInvestorRecordAccessMetadata: Delete an Investor Record Access Metadata entry.

Deletes the Investor Record Access Metadata entry that exactly matches the provided identifier parts.                It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var metadataKey = "metadataKey_example";  // string
var scope = "scope_example";  // string
var identifierScope = "identifierScope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.DeleteInvestorRecordAccessMetadata(identifierType, identifierValue, metadataKey, scope, identifierScope, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | Code of the investor record identifier type. |
| **identifierValue** | **string** | path | **required** | Code of the investor record under specified identifier type&#39;s scope and code. |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to delete |
| **scope** | **string** | query | **required** | The scope of the investor record entity. |
| **identifierScope** | **string** | query | **required** | Scope of the investor record identifier type. |
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
<summary>Using the DeleteInvestorRecordAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteInvestorRecordAccessMetadataWithHttpInfo(identifierType, identifierValue, metadataKey, scope, identifierScope, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getallinvestorrecordaccessmetadata"></a>
## GetAllInvestorRecordAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; GetAllInvestorRecordAccessMetadata(string identifierType, string identifierValue, string scope, string identifierScope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetAllInvestorRecordAccessMetadata: Get Access Metadata rules for an Investor Record.

Pass the Scope and Code of the Investor Record identifier along with the identifier value parameter to retrieve the associated Access Metadata.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var scope = "scope_example";  // string
var identifierScope = "identifierScope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.GetAllInvestorRecordAccessMetadata(identifierType, identifierValue, scope, identifierScope, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | Code of the investor record identifier type. |
| **identifierValue** | **string** | path | **required** | Code of the investor record under specified identifier type&#39;s scope and code. |
| **scope** | **string** | query | **required** | The scope of the investor record entity. |
| **identifierScope** | **string** | query | **required** | Scope of the investor record identifier type. |
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
| **200** | The access metadata for the Investor Record or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAllInvestorRecordAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.GetAllInvestorRecordAccessMetadataWithHttpInfo(identifierType, identifierValue, scope, identifierScope, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinvestorrecord"></a>
## GetInvestorRecord

> InvestorRecord GetInvestorRecord(string identifierType, string identifierValue, string scope, string identifierScope, List<string>? propertyKeys = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? relationshipDefinitionIds = null)

[EARLY ACCESS] GetInvestorRecord: Get Investor Record

Retrieve the definition of a investor record.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var scope = "scope_example";  // string
var identifierScope = "identifierScope_example";  // string
var propertyKeys = new List<string>?(); // List<string>? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
InvestorRecord result = apiInstance.GetInvestorRecord(identifierType, identifierValue, scope, identifierScope, propertyKeys, effectiveAt, asAt, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | Code of the investor record identifier type. |
| **identifierValue** | **string** | path | **required** | Code of the investor record under specified identifier type&#39;s scope and code. |
| **scope** | **string** | query | **required** | The scope of the investor record entity. |
| **identifierScope** | **string** | query | **required** | Scope of the investor record identifier type. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys or identifier types (as property keys) from the \&quot;InvestorRecord\&quot; domain              to include for found investor record, or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;InvestorRecord/ContactDetails/Address\&quot;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the investor record. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the investor record. Defaults to return the latest version of the investor record if not specified. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the investor record in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[InvestorRecord](InvestorRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested investor record |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInvestorRecordWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InvestorRecord> response = apiInstance.GetInvestorRecordWithHttpInfo(identifierType, identifierValue, scope, identifierScope, propertyKeys, effectiveAt, asAt, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinvestorrecordrelationships"></a>
## GetInvestorRecordRelationships

> ResourceListOfRelationship GetInvestorRecordRelationships(string identifierType, string identifierValue, string scope, string identifierScope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EARLY ACCESS] GetInvestorRecordRelationships: Get Investor Record relationships

Get relationships for a particular Investor Record.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var scope = "scope_example";  // string
var identifierScope = "identifierScope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelationship result = apiInstance.GetInvestorRecordRelationships(identifierType, identifierValue, scope, identifierScope, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | Code of the investor record identifier type. |
| **identifierValue** | **string** | path | **required** | Code of the investor record under specified identifier type&#39;s scope and code. |
| **scope** | **string** | query | **required** | The scope of the investor record entity. |
| **identifierScope** | **string** | query | **required** | Scope of the investor record identifier type. |
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
| **200** | The relationships for the specified investor record. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInvestorRecordRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetInvestorRecordRelationshipsWithHttpInfo(identifierType, identifierValue, scope, identifierScope, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listallinvestorrecords"></a>
## ListAllInvestorRecords

> ResourceListOfInvestorRecord ListAllInvestorRecords(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null, List<string>? relationshipDefinitionIds = null)

[EARLY ACCESS] ListAllInvestorRecords: List Investor Records

List all investor records which the user is entitled to see.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
ResourceListOfInvestorRecord result = apiInstance.ListAllInvestorRecords(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the investor records. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the investor records. Defaults to return the latest version              of each investor records if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing investor records from a previous call to list investor records. This  value is returned from the previous call. If a pagination token is provided the filter, effectiveAt, sortBy  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 5000 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys or identifier types (as property keys) from the \&quot;InvestorRecord\&quot; domain              to include for each investor record, or from any domain that supports relationships to decorate onto related entities.              These take the format {domain}/{scope}/{code} e.g. \&quot;InvestorRecord/ContactDetails/Address\&quot;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto each portfolio in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[ResourceListOfInvestorRecord](ResourceListOfInvestorRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | All existing Investor Records |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAllInvestorRecordsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfInvestorRecord> response = apiInstance.ListAllInvestorRecordsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchinvestorrecordaccessmetadata"></a>
## PatchInvestorRecordAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; PatchInvestorRecordAccessMetadata(string identifierType, string identifierValue, string scope, string identifierScope, List<AccessMetadataOperation> accessMetadataOperation, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] PatchInvestorRecordAccessMetadata: Patch Access Metadata rules for an Investor Record.

Patch Investor Record Access Metadata Rules in a single scope.  The behaviour is defined by the JSON Patch specification.                Currently only 'add' is a supported operation on the patch document    Currently only valid metadata keys are supported paths on the patch document                The response will return any affected Investor Record Access Metadata rules or a failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var identifierType = "identifierType_example";  // string
var identifierValue = "identifierValue_example";  // string
var scope = "scope_example";  // string
var identifierScope = "identifierScope_example";  // string
var accessMetadataOperation = new List<AccessMetadataOperation>(); // List<AccessMetadataOperation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.PatchInvestorRecordAccessMetadata(identifierType, identifierValue, scope, identifierScope, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **identifierType** | **string** | path | **required** | Code of the investor record identifier type. |
| **identifierValue** | **string** | path | **required** | Code of the investor record under specified identifier type&#39;s scope and code. |
| **scope** | **string** | query | **required** | The scope of the investor record entity. |
| **identifierScope** | **string** | query | **required** | Scope of the investor record identifier type. |
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
<summary>Using the PatchInvestorRecordAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.PatchInvestorRecordAccessMetadataWithHttpInfo(identifierType, identifierValue, scope, identifierScope, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertinvestorrecords"></a>
## UpsertInvestorRecords

> UpsertInvestorRecordsResponse UpsertInvestorRecords(string successMode, Dictionary<string, UpsertInvestorRecordRequest> requestBody)

[EARLY ACCESS] UpsertInvestorRecords: Upsert investor records

Creates or updates a collection of Investor Records

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<InvestorRecordsApi>();
var successMode = "successMode_example";  // string
var requestBody = new Dictionary<string, UpsertInvestorRecordRequest>(); // Dictionary<string, UpsertInvestorRecordRequest>
UpsertInvestorRecordsResponse result = apiInstance.UpsertInvestorRecords(successMode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial |
| **requestBody** | [Dictionary&lt;string, UpsertInvestorRecordRequest&gt;](UpsertInvestorRecordRequest.md) | body | **required** | A collection of requests to create or update Investor Records. |

### Return type

[UpsertInvestorRecordsResponse](UpsertInvestorRecordsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successfully created or updated investor records along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertInvestorRecordsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<UpsertInvestorRecordsResponse> response = apiInstance.UpsertInvestorRecordsWithHttpInfo(successMode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

