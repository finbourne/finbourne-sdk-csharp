# Finbourne.Sdk.Lusid.Api.SequencesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateSequence**](#createsequence) | **POST** `/api/api/sequences/{scope}` | [EARLY ACCESS] CreateSequence: Create a new sequence |
| [**DeleteSequence**](#deletesequence) | **DELETE** `/api/api/sequences/{scope}/{code}` | [EARLY ACCESS] DeleteSequence: Delete a sequence |
| [**GetSequence**](#getsequence) | **GET** `/api/api/sequences/{scope}/{code}` | [EARLY ACCESS] GetSequence: Get a specified sequence |
| [**ListSequences**](#listsequences) | **GET** `/api/api/sequences` | [EARLY ACCESS] ListSequences: List Sequences |
| [**Next**](#next) | **GET** `/api/api/sequences/{scope}/{code}/next` | [EARLY ACCESS] Next: Get next values from sequence |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SequencesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SequencesApi>();
```

---

<a id="createsequence"></a>
## CreateSequence

> SequenceDefinition CreateSequence(string scope, CreateSequenceRequest createSequenceRequest)

[EARLY ACCESS] CreateSequence: Create a new sequence

Create a new sequence

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SequencesApi>();
var scope = "scope_example";  // string
var createSequenceRequest = new CreateSequenceRequest(); // CreateSequenceRequest
SequenceDefinition result = apiInstance.CreateSequence(scope, createSequenceRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the sequence. |
| **createSequenceRequest** | [CreateSequenceRequest](CreateSequenceRequest.md) | body | **required** | Request to create sequence |

### Return type

[SequenceDefinition](SequenceDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Sequence |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateSequenceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SequenceDefinition> response = apiInstance.CreateSequenceWithHttpInfo(scope, createSequenceRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletesequence"></a>
## DeleteSequence

> DeletedEntityResponse DeleteSequence(string scope, string code)

[EARLY ACCESS] DeleteSequence: Delete a sequence

Delete a specific sequence                WARNING! Deleting a sequence is an inherently unsafe operation. It would allow a new sequence using the same pattern to be created, which may result in existing values being returned.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SequencesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteSequence(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the sequence. |
| **code** | **string** | path | **required** | Code of the sequence. This together with stated scope uniquely identifies the sequence. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response of the deleted sequence. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteSequenceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteSequenceWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getsequence"></a>
## GetSequence

> SequenceDefinition GetSequence(string scope, string code)

[EARLY ACCESS] GetSequence: Get a specified sequence

Return the details of a specified sequence

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SequencesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
SequenceDefinition result = apiInstance.GetSequence(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the sequence. |
| **code** | **string** | path | **required** | Code of the sequence. This together with stated scope uniquely              identifies the sequence. |

### Return type

[SequenceDefinition](SequenceDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested sequence |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSequenceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<SequenceDefinition> response = apiInstance.GetSequenceWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listsequences"></a>
## ListSequences

> PagedResourceListOfSequenceDefinition ListSequences(string? page = null, int? limit = null, string? filter = null)

[EARLY ACCESS] ListSequences: List Sequences

List sequences which satisfies filtering criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SequencesApi>();
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfSequenceDefinition result = apiInstance.ListSequences(page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **page** | **string?** | query | optional | The pagination token to use to continue listing sequences from a previous call to list sequences. This  value is returned from the previous call. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 500 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfSequenceDefinition](PagedResourceListOfSequenceDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The sequences matching filtering criteria |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListSequencesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfSequenceDefinition> response = apiInstance.ListSequencesWithHttpInfo(page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="next"></a>
## Next

> NextValueInSequenceResponse Next(string scope, string code, int? batch = null)

[EARLY ACCESS] Next: Get next values from sequence

Get the next set of values from a specified sequence

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SequencesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var batch = 56;  // int? (optional)
NextValueInSequenceResponse result = apiInstance.Next(scope, code, batch);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Scope of the sequence. |
| **code** | **string** | path | **required** | Code of the sequence. This together with stated scope uniquely              identifies the sequence. |
| **batch** | **int?** | query | optional | Number of sequences items to return for the specified sequence. Default to 1 if not specified. |

### Return type

[NextValueInSequenceResponse](NextValueInSequenceResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response containing next available values in specified sequence. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the NextWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<NextValueInSequenceResponse> response = apiInstance.NextWithHttpInfo(scope, code, batch);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

