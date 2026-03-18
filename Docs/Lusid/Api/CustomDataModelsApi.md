# Finbourne.Sdk.Lusid.Api.CustomDataModelsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**BatchAmend**](#batchamend) | **POST** `/api/api/datamodel/$batchamend` | [EXPERIMENTAL] BatchAmend: Batch amend entities Custom Data Model membership. |
| [**CreateCustomDataModel**](#createcustomdatamodel) | **POST** `/api/api/datamodel/{entityType}` | [EXPERIMENTAL] CreateCustomDataModel: Create a Custom Data Model |
| [**DeleteCustomDataModel**](#deletecustomdatamodel) | **DELETE** `/api/api/datamodel/{entityType}/{scope}/{code}` | [EXPERIMENTAL] DeleteCustomDataModel: Delete a Custom Data Model |
| [**GetCustomDataModel**](#getcustomdatamodel) | **GET** `/api/api/datamodel/{entityType}/{scope}/{code}` | [EXPERIMENTAL] GetCustomDataModel: Get a Custom Data Model |
| [**ListDataModelHierarchies**](#listdatamodelhierarchies) | **GET** `/api/api/datamodel/hierarchies` | [EXPERIMENTAL] ListDataModelHierarchies: List Custom Data Model hierarchies. |
| [**ListSupportedEntityTypes**](#listsupportedentitytypes) | **GET** `/api/api/datamodel/entitytype` | [EXPERIMENTAL] ListSupportedEntityTypes: List the currently supported entity types for use in Custom Data Models. |
| [**UpdateCustomDataModel**](#updatecustomdatamodel) | **PUT** `/api/api/datamodel/{entityType}/{scope}/{code}` | [EXPERIMENTAL] UpdateCustomDataModel: Update a Custom Data Model |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CustomDataModelsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
```

---

<a id="batchamend"></a>
## BatchAmend

> BatchAmendCustomDataModelMembershipResponse BatchAmend(string successMode, Dictionary<string, MembershipAmendmentRequest> requestBody)

[EXPERIMENTAL] BatchAmend: Batch amend entities Custom Data Model membership.

Add/Remove entities to/from a Custom Data Model in a single operation.                Each amendment request must be keyed by a unique correlation ID.  This id is ephemeral and is not stored by LUSID.  It serves only as a way to easily identify each amendment in the response.                Note: If using partial failure modes, then it is important to check the response body for failures as any  failures will still return a 200 status code.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
var successMode = "\"Partial\"";  // string
var requestBody = new Dictionary<string, MembershipAmendmentRequest>(); // Dictionary<string, MembershipAmendmentRequest>
BatchAmendCustomDataModelMembershipResponse result = apiInstance.BatchAmend(successMode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **successMode** | **string** | query | **required** | Whether the batch request should fail Atomically or in a Partial fashion - Allowed Values: Atomic, Partial. Default: `&quot;Partial&quot;` |
| **requestBody** | [Dictionary&lt;string, MembershipAmendmentRequest&gt;](MembershipAmendmentRequest.md) | body | **required** | The payload describing the amendments to make for the given Custom Data Model. |

### Return type

[BatchAmendCustomDataModelMembershipResponse](BatchAmendCustomDataModelMembershipResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The batch amendment operation was successful |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BatchAmendWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<BatchAmendCustomDataModelMembershipResponse> response = apiInstance.BatchAmendWithHttpInfo(successMode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createcustomdatamodel"></a>
## CreateCustomDataModel

> CustomDataModel CreateCustomDataModel(string entityType, CreateCustomDataModelRequest? createCustomDataModelRequest = null)

[EXPERIMENTAL] CreateCustomDataModel: Create a Custom Data Model

Creates a Custom Data Model.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
var entityType = "entityType_example";  // string
var createCustomDataModelRequest = new CreateCustomDataModelRequest?(); // CreateCustomDataModelRequest? (optional)
CustomDataModel result = apiInstance.CreateCustomDataModel(entityType, createCustomDataModelRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type of the Data Model. |
| **createCustomDataModelRequest** | [CreateCustomDataModelRequest?](CreateCustomDataModelRequest?.md) | body | optional | The request containing the details of the Data Model. |

### Return type

[CustomDataModel](CustomDataModel.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created Data Model |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCustomDataModelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomDataModel> response = apiInstance.CreateCustomDataModelWithHttpInfo(entityType, createCustomDataModelRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecustomdatamodel"></a>
## DeleteCustomDataModel

> DeletedEntityResponse DeleteCustomDataModel(string entityType, string scope, string code)

[EXPERIMENTAL] DeleteCustomDataModel: Delete a Custom Data Model

Delete a Custom Data Model. The data model will remain viewable at previous as at times, but will no longer  be part of any hierarchies.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
var entityType = "entityType_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteCustomDataModel(entityType, scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type of the Data Model. |
| **scope** | **string** | path | **required** | The scope of the specified Data Model. |
| **code** | **string** | path | **required** | The code of the specified Data Model. |

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
<summary>Using the DeleteCustomDataModelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCustomDataModelWithHttpInfo(entityType, scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcustomdatamodel"></a>
## GetCustomDataModel

> CustomDataModel GetCustomDataModel(string entityType, string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetCustomDataModel: Get a Custom Data Model

Retrieves a Custom Data Model at a given as at time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
var entityType = "entityType_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CustomDataModel result = apiInstance.GetCustomDataModel(entityType, scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type of the Data Model. |
| **scope** | **string** | path | **required** | The scope of the specified Data Model. |
| **code** | **string** | path | **required** | The code of the specified Data Model. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Data Model. Defaults to return              the latest version of the Data Model if not specified. |

### Return type

[CustomDataModel](CustomDataModel.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Data Model |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCustomDataModelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomDataModel> response = apiInstance.GetCustomDataModelWithHttpInfo(entityType, scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listdatamodelhierarchies"></a>
## ListDataModelHierarchies

> ResourceListOfDataModelSummary ListDataModelHierarchies(DateTimeOffset? asAt = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListDataModelHierarchies: List Custom Data Model hierarchies.

Lists the data model summaries within their hierarchical structure.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
ResourceListOfDataModelSummary result = apiInstance.ListDataModelHierarchies(asAt, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Data Model. Defaults to return              the latest version of the Data Model if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[ResourceListOfDataModelSummary](ResourceListOfDataModelSummary.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | All data model hierarchies. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListDataModelHierarchiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfDataModelSummary> response = apiInstance.ListDataModelHierarchiesWithHttpInfo(asAt, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listsupportedentitytypes"></a>
## ListSupportedEntityTypes

> ResourceListOfString ListSupportedEntityTypes()

[EXPERIMENTAL] ListSupportedEntityTypes: List the currently supported entity types for use in Custom Data Models.

Lists the currently supported entity types available to bind with Custom Data Models.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
ResourceListOfString result = apiInstance.ListSupportedEntityTypes();
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
| **200** | All supported entity types. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListSupportedEntityTypesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfString> response = apiInstance.ListSupportedEntityTypesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatecustomdatamodel"></a>
## UpdateCustomDataModel

> CustomDataModel UpdateCustomDataModel(string entityType, string scope, string code, UpdateCustomDataModelRequest? updateCustomDataModelRequest = null)

[EXPERIMENTAL] UpdateCustomDataModel: Update a Custom Data Model

Updates a Custom Data Model.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CustomDataModelsApi>();
var entityType = "entityType_example";  // string
var scope = "scope_example";  // string
var code = "code_example";  // string
var updateCustomDataModelRequest = new UpdateCustomDataModelRequest?(); // UpdateCustomDataModelRequest? (optional)
CustomDataModel result = apiInstance.UpdateCustomDataModel(entityType, scope, code, updateCustomDataModelRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type of the Data Model. |
| **scope** | **string** | path | **required** | The scope of the specified Data Model. |
| **code** | **string** | path | **required** | The code of the specified Data Model. |
| **updateCustomDataModelRequest** | [UpdateCustomDataModelRequest?](UpdateCustomDataModelRequest?.md) | body | optional | The request containing the details of the Data Model. |

### Return type

[CustomDataModel](CustomDataModel.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Data Model |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateCustomDataModelWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CustomDataModel> response = apiInstance.UpdateCustomDataModelWithHttpInfo(entityType, scope, code, updateCustomDataModelRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

