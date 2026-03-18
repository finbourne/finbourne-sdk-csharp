# Finbourne.Sdk.Lusid.Api.RelationshipsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateRelationship**](#createrelationship) | **POST** `/api/api/relationshipdefinitions/{scope}/{code}/relationships` | CreateRelationship: Create Relationship |
| [**DeleteRelationship**](#deleterelationship) | **POST** `/api/api/relationshipdefinitions/{scope}/{code}/relationships/$delete` | [EARLY ACCESS] DeleteRelationship: Delete Relationship |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RelationshipsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipsApi>();
```

---

<a id="createrelationship"></a>
## CreateRelationship

> CompleteRelationship CreateRelationship(string scope, string code, CreateRelationshipRequest createRelationshipRequest)

CreateRelationship: Create Relationship

Create a relationship between two entity objects by their identifiers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createRelationshipRequest = new CreateRelationshipRequest(); // CreateRelationshipRequest
CompleteRelationship result = apiInstance.CreateRelationship(scope, code, createRelationshipRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relationship |
| **code** | **string** | path | **required** | The code of the relationship |
| **createRelationshipRequest** | [CreateRelationshipRequest](CreateRelationshipRequest.md) | body | **required** | The details of the relationship to create. |

### Return type

[CompleteRelationship](CompleteRelationship.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created relationship. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRelationshipWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CompleteRelationship> response = apiInstance.CreateRelationshipWithHttpInfo(scope, code, createRelationshipRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterelationship"></a>
## DeleteRelationship

> DeletedEntityResponse DeleteRelationship(string scope, string code, DeleteRelationshipRequest deleteRelationshipRequest)

[EARLY ACCESS] DeleteRelationship: Delete Relationship

Delete a relationship between two entity objects represented by their identifiers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationshipsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var deleteRelationshipRequest = new DeleteRelationshipRequest(); // DeleteRelationshipRequest
DeletedEntityResponse result = apiInstance.DeleteRelationship(scope, code, deleteRelationshipRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relationship |
| **code** | **string** | path | **required** | The code of the relationship |
| **deleteRelationshipRequest** | [DeleteRelationshipRequest](DeleteRelationshipRequest.md) | body | **required** | The details of the relationship to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the relationship is deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRelationshipWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteRelationshipWithHttpInfo(scope, code, deleteRelationshipRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

