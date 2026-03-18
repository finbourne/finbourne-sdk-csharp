# Finbourne.Sdk.Identity.Api.NetworkZonesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateNetworkZone**](#createnetworkzone) | **POST** `/identity/api/networkzones` | [EARLY ACCESS] CreateNetworkZone: Creates a network zone |
| [**DeleteNetworkZone**](#deletenetworkzone) | **DELETE** `/identity/api/networkzones/{code}` | [EARLY ACCESS] DeleteNetworkZone: Deletes a network zone |
| [**GetNetworkZone**](#getnetworkzone) | **GET** `/identity/api/networkzones/{code}` | [EARLY ACCESS] GetNetworkZone: Retrieve a Network Zone |
| [**ListNetworkZones**](#listnetworkzones) | **GET** `/identity/api/networkzones` | [EARLY ACCESS] ListNetworkZones: Lists all network zones for a domain |
| [**UpdateNetworkZone**](#updatenetworkzone) | **PUT** `/identity/api/networkzones/{code}` | [EARLY ACCESS] UpdateNetworkZone: Updates an existing network zone |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Identity.Api;
using Finbourne.Sdk.Identity.Client;
using Finbourne.Sdk.Identity.Extensions;
using Finbourne.Sdk.Services.Identity.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<NetworkZonesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NetworkZonesApi>();
```

---

<a id="createnetworkzone"></a>
## CreateNetworkZone

> NetworkZoneDefinitionResponse CreateNetworkZone(CreateNetworkZoneRequest createNetworkZoneRequest)

[EARLY ACCESS] CreateNetworkZone: Creates a network zone

By default, the network zone will have its hierarchy set to last on creation.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NetworkZonesApi>();
var createNetworkZoneRequest = new CreateNetworkZoneRequest(); // CreateNetworkZoneRequest
NetworkZoneDefinitionResponse result = apiInstance.CreateNetworkZone(createNetworkZoneRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createNetworkZoneRequest** | [CreateNetworkZoneRequest](CreateNetworkZoneRequest.md) | body | **required** | The details of the network zone to define |

### Return type

[NetworkZoneDefinitionResponse](NetworkZoneDefinitionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Create Network Zone |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateNetworkZoneWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<NetworkZoneDefinitionResponse> response = apiInstance.CreateNetworkZoneWithHttpInfo(createNetworkZoneRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletenetworkzone"></a>
## DeleteNetworkZone

> void DeleteNetworkZone(string code)

[EARLY ACCESS] DeleteNetworkZone: Deletes a network zone

Will return a success if network zone already deleted

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NetworkZonesApi>();
var code = "code_example";  // string
apiInstance.DeleteNetworkZone(code);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The unique identifier of the network zone to delete |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteNetworkZoneWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteNetworkZoneWithHttpInfo(code);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getnetworkzone"></a>
## GetNetworkZone

> NetworkZoneDefinitionResponse GetNetworkZone(string code)

[EARLY ACCESS] GetNetworkZone: Retrieve a Network Zone

Retrieves a Network Zone

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NetworkZonesApi>();
var code = "code_example";  // string
NetworkZoneDefinitionResponse result = apiInstance.GetNetworkZone(code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The unique identifier of the network zone |

### Return type

[NetworkZoneDefinitionResponse](NetworkZoneDefinitionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Get Network Zone |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetNetworkZoneWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<NetworkZoneDefinitionResponse> response = apiInstance.GetNetworkZoneWithHttpInfo(code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listnetworkzones"></a>
## ListNetworkZones

> List&lt;NetworkZoneDefinitionResponse&gt; ListNetworkZones()

[EARLY ACCESS] ListNetworkZones: Lists all network zones for a domain

Lists all network zones for a domain

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NetworkZonesApi>();
List<NetworkZoneDefinitionResponse> result = apiInstance.ListNetworkZones();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;NetworkZoneDefinitionResponse&gt;](NetworkZoneDefinitionResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List Network Zones |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListNetworkZonesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<NetworkZoneDefinitionResponse>> response = apiInstance.ListNetworkZonesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatenetworkzone"></a>
## UpdateNetworkZone

> NetworkZoneDefinitionResponse UpdateNetworkZone(string code, UpdateNetworkZoneRequest updateNetworkZoneRequest)

[EARLY ACCESS] UpdateNetworkZone: Updates an existing network zone

Updates an existing network zone

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<NetworkZonesApi>();
var code = "code_example";  // string
var updateNetworkZoneRequest = new UpdateNetworkZoneRequest(); // UpdateNetworkZoneRequest
NetworkZoneDefinitionResponse result = apiInstance.UpdateNetworkZone(code, updateNetworkZoneRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **code** | **string** | path | **required** | The unique identifier of the network zone |
| **updateNetworkZoneRequest** | [UpdateNetworkZoneRequest](UpdateNetworkZoneRequest.md) | body | **required** | The updated definition of the network zone |

### Return type

[NetworkZoneDefinitionResponse](NetworkZoneDefinitionResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Update Network Zone |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateNetworkZoneWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<NetworkZoneDefinitionResponse> response = apiInstance.UpdateNetworkZoneWithHttpInfo(code, updateNetworkZoneRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

