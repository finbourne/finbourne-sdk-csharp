# Finbourne.Sdk.Lusid.Api.AggregatedReturnsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeleteReturnsEntity**](#deletereturnsentity) | **DELETE** `/api/api/returns/{scope}/{code}` | [EXPERIMENTAL] DeleteReturnsEntity: Delete returns entity. |
| [**GetReturnsEntity**](#getreturnsentity) | **GET** `/api/api/returns/{scope}/{code}` | [EXPERIMENTAL] GetReturnsEntity: Get returns entity. |
| [**ListReturnsEntities**](#listreturnsentities) | **GET** `/api/api/returns` | [EXPERIMENTAL] ListReturnsEntities: List returns entities. |
| [**UpsertReturnsEntity**](#upsertreturnsentity) | **POST** `/api/api/returns` | [EXPERIMENTAL] UpsertReturnsEntity: Upsert returns entity. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AggregatedReturnsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
```

---

<a id="deletereturnsentity"></a>
## DeleteReturnsEntity

> DeletedEntityResponse DeleteReturnsEntity(string scope, string code)

[EXPERIMENTAL] DeleteReturnsEntity: Delete returns entity.

Delete returns entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteReturnsEntity(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Returns entity scope. |
| **code** | **string** | path | **required** | Returns entity code. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time that the returns entity was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteReturnsEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteReturnsEntityWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getreturnsentity"></a>
## GetReturnsEntity

> ReturnsEntity GetReturnsEntity(string scope, string code, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetReturnsEntity: Get returns entity.

Get returns entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ReturnsEntity result = apiInstance.GetReturnsEntity(scope, code, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | Returns entity scope. |
| **code** | **string** | path | **required** | Returns entity code. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the returns entity. Defaults to return              the latest version of the definition if not specified. |

### Return type

[ReturnsEntity](ReturnsEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested returns entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetReturnsEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReturnsEntity> response = apiInstance.GetReturnsEntityWithHttpInfo(scope, code, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listreturnsentities"></a>
## ListReturnsEntities

> ResourceListOfReturnsEntity ListReturnsEntities(DateTimeOffset? asAt = null)

[EXPERIMENTAL] ListReturnsEntities: List returns entities.

List returns entities.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfReturnsEntity result = apiInstance.ListReturnsEntities(asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the relation definitions. Defaults to return              the latest version of each definition if not specified. |

### Return type

[ResourceListOfReturnsEntity](ResourceListOfReturnsEntity.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested returns entities |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListReturnsEntitiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfReturnsEntity> response = apiInstance.ListReturnsEntitiesWithHttpInfo(asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertreturnsentity"></a>
## UpsertReturnsEntity

> ReturnsEntity UpsertReturnsEntity(ReturnsEntity returnsEntity)

[EXPERIMENTAL] UpsertReturnsEntity: Upsert returns entity.

Upsert returns entity.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AggregatedReturnsApi>();
var returnsEntity = new ReturnsEntity(); // ReturnsEntity
ReturnsEntity result = apiInstance.UpsertReturnsEntity(returnsEntity);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **returnsEntity** | [ReturnsEntity](ReturnsEntity.md) | body | **required** | Definition of the returns entity. |

### Return type

[ReturnsEntity](ReturnsEntity.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The upserted returns entity |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertReturnsEntityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ReturnsEntity> response = apiInstance.UpsertReturnsEntityWithHttpInfo(returnsEntity);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

