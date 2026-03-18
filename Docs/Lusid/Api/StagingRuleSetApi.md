# Finbourne.Sdk.Lusid.Api.StagingRuleSetApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateStagingRuleSet**](#createstagingruleset) | **POST** `/api/api/stagingrulesets/{entityType}` | CreateStagingRuleSet: Create a StagingRuleSet |
| [**DeleteStagingRuleSet**](#deletestagingruleset) | **DELETE** `/api/api/stagingrulesets/{entityType}` | DeleteStagingRuleSet: Delete a StagingRuleSet |
| [**GetStagingRuleSet**](#getstagingruleset) | **GET** `/api/api/stagingrulesets/{entityType}` | GetStagingRuleSet: Get a StagingRuleSet |
| [**ListStagingRuleSets**](#liststagingrulesets) | **GET** `/api/api/stagingrulesets` | ListStagingRuleSets: List StagingRuleSets |
| [**UpdateStagingRuleSet**](#updatestagingruleset) | **PUT** `/api/api/stagingrulesets/{entityType}` | UpdateStagingRuleSet: Update a StagingRuleSet |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<StagingRuleSetApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagingRuleSetApi>();
```

---

<a id="createstagingruleset"></a>
## CreateStagingRuleSet

> StagingRuleSet CreateStagingRuleSet(string entityType, CreateStagingRuleSetRequest createStagingRuleSetRequest)

CreateStagingRuleSet: Create a StagingRuleSet

Create a new staging rule set.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagingRuleSetApi>();
var entityType = "entityType_example";  // string
var createStagingRuleSetRequest = new CreateStagingRuleSetRequest(); // CreateStagingRuleSetRequest
StagingRuleSet result = apiInstance.CreateStagingRuleSet(entityType, createStagingRuleSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type for which to create the staging rule set. |
| **createStagingRuleSetRequest** | [CreateStagingRuleSetRequest](CreateStagingRuleSetRequest.md) | body | **required** | Request to create a staging rule set. |

### Return type

[StagingRuleSet](StagingRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created staging rule set |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateStagingRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StagingRuleSet> response = apiInstance.CreateStagingRuleSetWithHttpInfo(entityType, createStagingRuleSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletestagingruleset"></a>
## DeleteStagingRuleSet

> DeletedEntityResponse DeleteStagingRuleSet(string entityType)

DeleteStagingRuleSet: Delete a StagingRuleSet

Delete a staging rule set of a specific entity type. Deletion will be valid from the staging rule set's creation datetime.  This means that the staging rule set will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagingRuleSetApi>();
var entityType = "entityType_example";  // string
DeletedEntityResponse result = apiInstance.DeleteStagingRuleSet(entityType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type for which to delete the staging rule set. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting staging rule set |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteStagingRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteStagingRuleSetWithHttpInfo(entityType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getstagingruleset"></a>
## GetStagingRuleSet

> StagingRuleSet GetStagingRuleSet(string entityType, DateTimeOffset? asAt = null)

GetStagingRuleSet: Get a StagingRuleSet

Get the staging rule set for the given entity type at the specific asAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagingRuleSetApi>();
var entityType = "entityType_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
StagingRuleSet result = apiInstance.GetStagingRuleSet(entityType, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type for which to retrieve the staging rule set. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the staging rule set. Defaults to return the latest              version of the staging rule set if not specified. |

### Return type

[StagingRuleSet](StagingRuleSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested staging rule set |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetStagingRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StagingRuleSet> response = apiInstance.GetStagingRuleSetWithHttpInfo(entityType, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="liststagingrulesets"></a>
## ListStagingRuleSets

> PagedResourceListOfStagingRuleSet ListStagingRuleSets(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null)

ListStagingRuleSets: List StagingRuleSets

List all the staging rule sets matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagingRuleSetApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfStagingRuleSet result = apiInstance.ListStagingRuleSets(asAt, page, sortBy, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the staging rule sets. Defaults to return the latest              version of the staging rule sets if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing staging rule sets from a previous call to list              staging rule sets. This value is returned from the previous call. If a pagination token is provided the sortBy,              filter, effectiveAt, and asAt fields must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfStagingRuleSet](PagedResourceListOfStagingRuleSet.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A list of staging rule sets |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListStagingRuleSetsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfStagingRuleSet> response = apiInstance.ListStagingRuleSetsWithHttpInfo(asAt, page, sortBy, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatestagingruleset"></a>
## UpdateStagingRuleSet

> StagingRuleSet UpdateStagingRuleSet(string entityType, UpdateStagingRuleSetRequest updateStagingRuleSetRequest)

UpdateStagingRuleSet: Update a StagingRuleSet

Update an existing staging rule set.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<StagingRuleSetApi>();
var entityType = "entityType_example";  // string
var updateStagingRuleSetRequest = new UpdateStagingRuleSetRequest(); // UpdateStagingRuleSetRequest
StagingRuleSet result = apiInstance.UpdateStagingRuleSet(entityType, updateStagingRuleSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **entityType** | **string** | path | **required** | The entity type for which to update the staging rule set. |
| **updateStagingRuleSetRequest** | [UpdateStagingRuleSetRequest](UpdateStagingRuleSetRequest.md) | body | **required** | Request to update a staging rule set. |

### Return type

[StagingRuleSet](StagingRuleSet.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated staging rule set |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateStagingRuleSetWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<StagingRuleSet> response = apiInstance.UpdateStagingRuleSetWithHttpInfo(entityType, updateStagingRuleSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

