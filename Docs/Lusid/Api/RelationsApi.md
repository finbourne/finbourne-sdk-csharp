# Finbourne.Sdk.Lusid.Api.RelationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateRelation**](#createrelation) | **POST** `/api/api/relations/{scope}/{code}` | [EXPERIMENTAL] CreateRelation: Create Relation |
| [**DeleteRelation**](#deleterelation) | **POST** `/api/api/relations/{scope}/{code}/$delete` | [EXPERIMENTAL] DeleteRelation: Delete a relation |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<RelationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationsApi>();
```

---

<a id="createrelation"></a>
## CreateRelation

> CompleteRelation CreateRelation(string scope, string code, CreateRelationRequest createRelationRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] CreateRelation: Create Relation

Create a relation between two entity objects by their identifiers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var createRelationRequest = new CreateRelationRequest(); // CreateRelationRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
CompleteRelation result = apiInstance.CreateRelation(scope, code, createRelationRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relation definition |
| **code** | **string** | path | **required** | The code of the relation definition |
| **createRelationRequest** | [CreateRelationRequest](CreateRelationRequest.md) | body | **required** | The details of the relation to create. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the relation should be effective from. Defaults to the current LUSID system datetime if not specified. |

### Return type

[CompleteRelation](CompleteRelation.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created relation. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateRelationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CompleteRelation> response = apiInstance.CreateRelationWithHttpInfo(scope, code, createRelationRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleterelation"></a>
## DeleteRelation

> DeletedEntityResponse DeleteRelation(string scope, string code, DeleteRelationRequest deleteRelationRequest, DateTimeOrCutLabel? effectiveAt = null)

[EXPERIMENTAL] DeleteRelation: Delete a relation

Delete a relation between two entity objects represented by their identifiers

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<RelationsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var deleteRelationRequest = new DeleteRelationRequest(); // DeleteRelationRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteRelation(scope, code, deleteRelationRequest, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the relation definition |
| **code** | **string** | path | **required** | The code of the relation definition |
| **deleteRelationRequest** | [DeleteRelationRequest](DeleteRelationRequest.md) | body | **required** | The details of the relation to delete. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which the relation should the deletion be effective from. Defaults to the current LUSID system datetime if not specified. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the relation is deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteRelationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteRelationWithHttpInfo(scope, code, deleteRelationRequest, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

