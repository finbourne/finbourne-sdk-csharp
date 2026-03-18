# Finbourne.Sdk.Lusid.Api.AddressKeyDefinitionApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateAddressKeyDefinition**](#createaddresskeydefinition) | **POST** `/api/api/addresskeydefinitions` | [EARLY ACCESS] CreateAddressKeyDefinition: Create an AddressKeyDefinition. |
| [**GetAddressKeyDefinition**](#getaddresskeydefinition) | **GET** `/api/api/addresskeydefinitions/{key}` | [EARLY ACCESS] GetAddressKeyDefinition: Get an AddressKeyDefinition. |
| [**ListAddressKeyDefinitions**](#listaddresskeydefinitions) | **GET** `/api/api/addresskeydefinitions` | [EARLY ACCESS] ListAddressKeyDefinitions: List AddressKeyDefinitions. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<AddressKeyDefinitionApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyDefinitionApi>();
```

---

<a id="createaddresskeydefinition"></a>
## CreateAddressKeyDefinition

> AddressKeyDefinition CreateAddressKeyDefinition(CreateAddressKeyDefinitionRequest createAddressKeyDefinitionRequest)

[EARLY ACCESS] CreateAddressKeyDefinition: Create an AddressKeyDefinition.

Create the given address key definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyDefinitionApi>();
var createAddressKeyDefinitionRequest = new CreateAddressKeyDefinitionRequest(); // CreateAddressKeyDefinitionRequest
AddressKeyDefinition result = apiInstance.CreateAddressKeyDefinition(createAddressKeyDefinitionRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createAddressKeyDefinitionRequest** | [CreateAddressKeyDefinitionRequest](CreateAddressKeyDefinitionRequest.md) | body | **required** | The request used to create the address key definition. |

### Return type

[AddressKeyDefinition](AddressKeyDefinition.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created address key definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateAddressKeyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AddressKeyDefinition> response = apiInstance.CreateAddressKeyDefinitionWithHttpInfo(createAddressKeyDefinitionRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaddresskeydefinition"></a>
## GetAddressKeyDefinition

> AddressKeyDefinition GetAddressKeyDefinition(string key, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetAddressKeyDefinition: Get an AddressKeyDefinition.

Get the address key definition with the given address key at the specific asAt time.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyDefinitionApi>();
var key = "key_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AddressKeyDefinition result = apiInstance.GetAddressKeyDefinition(key, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **key** | **string** | path | **required** | The address key of the address key definition. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the address key definition. Defaults to return the latest version of the address key definition if not specified. |

### Return type

[AddressKeyDefinition](AddressKeyDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The address key definition with the given address key. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAddressKeyDefinitionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AddressKeyDefinition> response = apiInstance.GetAddressKeyDefinitionWithHttpInfo(key, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listaddresskeydefinitions"></a>
## ListAddressKeyDefinitions

> PagedResourceListOfAddressKeyDefinition ListAddressKeyDefinitions(DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EARLY ACCESS] ListAddressKeyDefinitions: List AddressKeyDefinitions.

Fetch the last pre-AsAt date version of each address key definition.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<AddressKeyDefinitionApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfAddressKeyDefinition result = apiInstance.ListAddressKeyDefinitions(asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the address key definition.              Defaults to return the latest version of the address key definition if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing address key definitions from a previous call to list address key definitions.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[PagedResourceListOfAddressKeyDefinition](PagedResourceListOfAddressKeyDefinition.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A collection of address key definitions. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAddressKeyDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAddressKeyDefinition> response = apiInstance.ListAddressKeyDefinitionsWithHttpInfo(asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

