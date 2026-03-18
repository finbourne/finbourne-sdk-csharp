# Finbourne.Sdk.Horizon.Api.IntegrationsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateInstance**](#createinstance) | **POST** `/horizon/api/integrations/instances` | [EXPERIMENTAL] CreateInstance: Create a single integration instance. |
| [**DeleteInstance**](#deleteinstance) | **DELETE** `/horizon/api/integrations/instances/{instanceId}` | [EXPERIMENTAL] DeleteInstance: Delete a single integration instance. |
| [**ExecuteInstance**](#executeinstance) | **POST** `/horizon/api/integrations/instances/{instanceId}/execute` | [EXPERIMENTAL] ExecuteInstance: Execute an integration instance. |
| [**ExecuteInstanceWithParams**](#executeinstancewithparams) | **POST** `/horizon/api/integrations/instances/{instanceId}/executewithparams` | [EXPERIMENTAL] ExecuteInstanceWithParams: Execute an integration instance with runtime parameters |
| [**GetExecutionIdsForInstance**](#getexecutionidsforinstance) | **GET** `/horizon/api/integrations/instances/{instanceId}/executions` | [EXPERIMENTAL] GetExecutionIdsForInstance: Get integration instance execution ids. |
| [**GetInstance**](#getinstance) | **GET** `/horizon/api/integrations/instances/{instanceId}` | [EXPERIMENTAL] GetInstance: Get a specified Instance for a given integration. |
| [**GetInstanceOptionalPropertyMapping**](#getinstanceoptionalpropertymapping) | **GET** `/horizon/api/integrations/instances/configuration/{integration}/{instanceId}` | [EXPERIMENTAL] GetInstanceOptionalPropertyMapping: Get the Optional Property Mapping for an Integration Instance |
| [**GetIntegrationConfiguration**](#getintegrationconfiguration) | **GET** `/horizon/api/integrations/configuration/{integration}` | [EXPERIMENTAL] GetIntegrationConfiguration: Get the Field and Property Mapping configuration for a given integration |
| [**GetIntegrationConfigurationFields**](#getintegrationconfigurationfields) | **GET** `/horizon/api/integrations/configuration/{integration}/fields` | [EXPERIMENTAL] GetIntegrationConfigurationFields: Get the Field Mapping configuration for a given integration |
| [**GetIntegrationConfigurationProperties**](#getintegrationconfigurationproperties) | **GET** `/horizon/api/integrations/configuration/{integration}/properties` | [EXPERIMENTAL] GetIntegrationConfigurationProperties: Get the Property Mapping configuration for a given integration |
| [**GetSchema**](#getschema) | **GET** `/horizon/api/integrations/schema/{integration}` | [EXPERIMENTAL] GetSchema: Get the JSON schema for the details section of an integration instance. |
| [**ListInstances**](#listinstances) | **GET** `/horizon/api/integrations/instances` | [EXPERIMENTAL] ListInstances: List instances across all integrations. |
| [**ListIntegrations**](#listintegrations) | **GET** `/horizon/api/integrations` | [EXPERIMENTAL] ListIntegrations: List available integrations. |
| [**SetInstanceOptionalPropertyMapping**](#setinstanceoptionalpropertymapping) | **PUT** `/horizon/api/integrations/instances/configuration/{integration}/{instanceId}` | [EXPERIMENTAL] SetInstanceOptionalPropertyMapping: Set the Optional Property Mapping for an Integration Instance |
| [**UpdateInstance**](#updateinstance) | **PUT** `/horizon/api/integrations/instances/{instanceId}` | [EXPERIMENTAL] UpdateInstance: Update a single integration instance. |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Horizon.Api;
using Finbourne.Sdk.Horizon.Client;
using Finbourne.Sdk.Horizon.Extensions;
using Finbourne.Sdk.Services.Horizon.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<IntegrationsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
```

---

<a id="createinstance"></a>
## CreateInstance

> InstanceIdentifier CreateInstance(CreateInstanceRequest? createInstanceRequest = null)

[EXPERIMENTAL] CreateInstance: Create a single integration instance.

Creates a new instance of an integration, returning its identifier. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var createInstanceRequest = new CreateInstanceRequest?(); // CreateInstanceRequest? (optional)
InstanceIdentifier result = apiInstance.CreateInstance(createInstanceRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createInstanceRequest** | [CreateInstanceRequest?](CreateInstanceRequest?.md) | body | optional | The new integration instance. |

### Return type

[InstanceIdentifier](InstanceIdentifier.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Identifier of the created instance. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The integration type does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<InstanceIdentifier> response = apiInstance.CreateInstanceWithHttpInfo(createInstanceRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteinstance"></a>
## DeleteInstance

> void DeleteInstance(string instanceId)

[EXPERIMENTAL] DeleteInstance: Delete a single integration instance.

Deletes an existing instance of an integration, returning its identifier. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
apiInstance.DeleteInstance(instanceId);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Instance identifier e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |

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
| **404** | The instance does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.DeleteInstanceWithHttpInfo(instanceId);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="executeinstance"></a>
## ExecuteInstance

> ExecuteInstanceResponse ExecuteInstance(string instanceId)

[EXPERIMENTAL] ExecuteInstance: Execute an integration instance.

Starts execution of an instance, returning its execution identifier. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
ExecuteInstanceResponse result = apiInstance.ExecuteInstance(instanceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Instance identifier e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |

### Return type

[ExecuteInstanceResponse](ExecuteInstanceResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The execution id |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The integration instance does not exist |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ExecuteInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ExecuteInstanceResponse> response = apiInstance.ExecuteInstanceWithHttpInfo(instanceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="executeinstancewithparams"></a>
## ExecuteInstanceWithParams

> ExecuteInstanceResponse ExecuteInstanceWithParams(string instanceId, Dictionary<string, string> requestBody)

[EXPERIMENTAL] ExecuteInstanceWithParams: Execute an integration instance with runtime parameters

Starts execution of an instance, returning its execution identifier. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
var requestBody = new Dictionary<string, string>(); // Dictionary<string, string>
ExecuteInstanceResponse result = apiInstance.ExecuteInstanceWithParams(instanceId, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Instance identifier e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |
| **requestBody** | [Dictionary&lt;string, string&gt;](string.md) | body | **required** | Dictionary(string,string) of runtime parameters passed to the integration instance |

### Return type

[ExecuteInstanceResponse](ExecuteInstanceResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The execution id |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The integration instance does not exist |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ExecuteInstanceWithParamsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ExecuteInstanceResponse> response = apiInstance.ExecuteInstanceWithParamsWithHttpInfo(instanceId, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getexecutionidsforinstance"></a>
## GetExecutionIdsForInstance

> List&lt;string&gt; GetExecutionIdsForInstance(string instanceId, int? limit = null)

[EXPERIMENTAL] GetExecutionIdsForInstance: Get integration instance execution ids.

Get the most recent execution ids for an integration instance. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
var limit = 56;  // int? (optional)
List<string> result = apiInstance.GetExecutionIdsForInstance(instanceId, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Instance identifier e.g. \&quot;30dc93c6-a127-46bf-aea8-e466d720b72d\&quot;. |
| **limit** | **int?** | query | optional | Maximum number of returned execution ids |

### Return type

**List<string>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The execution ids sorted by start date (descending) |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The integration instance does not exist |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetExecutionIdsForInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<string>> response = apiInstance.GetExecutionIdsForInstanceWithHttpInfo(instanceId, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstance"></a>
## GetInstance

> IntegrationInstanceResponse GetInstance(string instanceId)

[EXPERIMENTAL] GetInstance: Get a specified Instance for a given integration.

The user must be authenticated to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
IntegrationInstanceResponse result = apiInstance.GetInstance(instanceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** |  |

### Return type

[IntegrationInstanceResponse](IntegrationInstanceResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested instance does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IntegrationInstanceResponse> response = apiInstance.GetInstanceWithHttpInfo(instanceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getinstanceoptionalpropertymapping"></a>
## GetInstanceOptionalPropertyMapping

> Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt; GetInstanceOptionalPropertyMapping(string integration, string instanceId)

[EXPERIMENTAL] GetInstanceOptionalPropertyMapping: Get the Optional Property Mapping for an Integration Instance

Will return the full list of optional properties configured for this integration instance and any naming overrides

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var integration = "integration_example";  // string
var instanceId = "instanceId_example";  // string
Dictionary<string, LusidPropertyDefinitionOverridesByType> result = apiInstance.GetInstanceOptionalPropertyMapping(integration, instanceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **integration** | **string** | path | **required** | The type of the integration e.g. \&quot;copp-clark\&quot;. |
| **instanceId** | **string** | path | **required** | Identifier of the instance |

### Return type

[Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt;](LusidPropertyDefinitionOverridesByType.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **404** | The requested instance(s) do not exist. |  -  |
| **400** | The details of the input related failure |  -  |
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetInstanceOptionalPropertyMappingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, LusidPropertyDefinitionOverridesByType>> response = apiInstance.GetInstanceOptionalPropertyMappingWithHttpInfo(integration, instanceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getintegrationconfiguration"></a>
## GetIntegrationConfiguration

> IntegrationPropertyConfiguration GetIntegrationConfiguration(string integration)

[EXPERIMENTAL] GetIntegrationConfiguration: Get the Field and Property Mapping configuration for a given integration

The user must be authenticated, entitled to call this method, but the user's domain does not need to be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var integration = "integration_example";  // string
IntegrationPropertyConfiguration result = apiInstance.GetIntegrationConfiguration(integration);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **integration** | **string** | path | **required** |  |

### Return type

[IntegrationPropertyConfiguration](IntegrationPropertyConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested integration does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetIntegrationConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<IntegrationPropertyConfiguration> response = apiInstance.GetIntegrationConfigurationWithHttpInfo(integration);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getintegrationconfigurationfields"></a>
## GetIntegrationConfigurationFields

> PagedResourceListOfIFieldMapping GetIntegrationConfigurationFields(string integration, string? filter = null, List<string>? sortBy = null, int? limit = null, string? pageToken = null)

[EXPERIMENTAL] GetIntegrationConfigurationFields: Get the Field Mapping configuration for a given integration

The user must be authenticated, entitled to call this method, but the user's domain does not need to be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var integration = "integration_example";  // string
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 100;  // int? (optional)
var pageToken = "\"\"";  // string? (optional)
PagedResourceListOfIFieldMapping result = apiInstance.GetIntegrationConfigurationFields(integration, filter, sortBy, limit, pageToken);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **integration** | **string** | path | **required** |  |
| **filter** | **string?** | query | optional |  |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional |  |
| **limit** | **int?** | query | optional |  Default: `100` |
| **pageToken** | **string?** | query | optional |  Default: `&quot;&quot;` |

### Return type

[PagedResourceListOfIFieldMapping](PagedResourceListOfIFieldMapping.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested integration does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetIntegrationConfigurationFieldsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfIFieldMapping> response = apiInstance.GetIntegrationConfigurationFieldsWithHttpInfo(integration, filter, sortBy, limit, pageToken);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getintegrationconfigurationproperties"></a>
## GetIntegrationConfigurationProperties

> PagedResourceListOfIPropertyMapping GetIntegrationConfigurationProperties(string integration, string? filter = null, List<string>? sortBy = null, int? limit = null, string? pageToken = null)

[EXPERIMENTAL] GetIntegrationConfigurationProperties: Get the Property Mapping configuration for a given integration

The user must be authenticated, entitled to call this method, but the user's domain does not need to be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var integration = "integration_example";  // string
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 100;  // int? (optional)
var pageToken = "\"\"";  // string? (optional)
PagedResourceListOfIPropertyMapping result = apiInstance.GetIntegrationConfigurationProperties(integration, filter, sortBy, limit, pageToken);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **integration** | **string** | path | **required** |  |
| **filter** | **string?** | query | optional |  |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional |  |
| **limit** | **int?** | query | optional |  Default: `100` |
| **pageToken** | **string?** | query | optional |  Default: `&quot;&quot;` |

### Return type

[PagedResourceListOfIPropertyMapping](PagedResourceListOfIPropertyMapping.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The requested integration does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetIntegrationConfigurationPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfIPropertyMapping> response = apiInstance.GetIntegrationConfigurationPropertiesWithHttpInfo(integration, filter, sortBy, limit, pageToken);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getschema"></a>
## GetSchema

> JSchema GetSchema(string integration)

[EXPERIMENTAL] GetSchema: Get the JSON schema for the details section of an integration instance.

The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var integration = "integration_example";  // string
JSchema result = apiInstance.GetSchema(integration);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **integration** | **string** | path | **required** | The type of the integration e.g. \&quot;copp-clark\&quot;. |

### Return type

[JSchema](JSchema.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The system defined JSON schema for the details of a specified integration. |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The integration type does not exist or is not enabled. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetSchemaWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<JSchema> response = apiInstance.GetSchemaWithHttpInfo(integration);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listinstances"></a>
## ListInstances

> List&lt;IntegrationInstance&gt; ListInstances()

[EXPERIMENTAL] ListInstances: List instances across all integrations.

The user must be authenticated to call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
List<IntegrationInstance> result = apiInstance.ListInstances();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;IntegrationInstance&gt;](IntegrationInstance.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **404** | The requested instance(s) do not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListInstancesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<IntegrationInstance>> response = apiInstance.ListInstancesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listintegrations"></a>
## ListIntegrations

> List&lt;IntegrationDescription&gt; ListIntegrations()

[EXPERIMENTAL] ListIntegrations: List available integrations.

List all available integrations. ```\"licensed\"``` indicates your domain is licensed to use this integration. To request a licence contact your [FINBOURNE sales representative](https://www.finbourne.com/contact/). Any authenticated user can call this method.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
List<IntegrationDescription> result = apiInstance.ListIntegrations();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[List&lt;IntegrationDescription&gt;](IntegrationDescription.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListIntegrationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<IntegrationDescription>> response = apiInstance.ListIntegrationsWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setinstanceoptionalpropertymapping"></a>
## SetInstanceOptionalPropertyMapping

> Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt; SetInstanceOptionalPropertyMapping(string instanceId, string integration, Dictionary<string, LusidPropertyDefinitionOverridesByType>? requestBody = null)

[EXPERIMENTAL] SetInstanceOptionalPropertyMapping: Set the Optional Property Mapping for an Integration Instance

The full list of properties must be supplied, the removal of a property from this list will remove it from the integration instance

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
var integration = "integration_example";  // string
var requestBody = new Dictionary<string, LusidPropertyDefinitionOverridesByType>?(); // Dictionary<string, LusidPropertyDefinitionOverridesByType>? (optional)
Dictionary<string, LusidPropertyDefinitionOverridesByType> result = apiInstance.SetInstanceOptionalPropertyMapping(instanceId, integration, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Identifier of the instance |
| **integration** | **string** | path | **required** | The type of the integration e.g. \&quot;copp-clark\&quot;. |
| **requestBody** | [Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt;?](LusidPropertyDefinitionOverridesByType.md) | body | optional | Properties to be included and any overrides |

### Return type

[Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt;](LusidPropertyDefinitionOverridesByType.md)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **404** | The requested instance(s) do not exist. |  -  |
| **400** | The details of the input related failure |  -  |
| **200** | OK |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetInstanceOptionalPropertyMappingWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, LusidPropertyDefinitionOverridesByType>> response = apiInstance.SetInstanceOptionalPropertyMappingWithHttpInfo(instanceId, integration, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateinstance"></a>
## UpdateInstance

> void UpdateInstance(string instanceId, UpdateInstanceRequest? updateInstanceRequest = null)

[EXPERIMENTAL] UpdateInstance: Update a single integration instance.

Updates an existing instance of an integration, returning its identifier. The user must be authenticated, entitled to call this method, and the user's domain must be licensed for the integration.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<IntegrationsApi>();
var instanceId = "instanceId_example";  // string
var updateInstanceRequest = new UpdateInstanceRequest?(); // UpdateInstanceRequest? (optional)
apiInstance.UpdateInstance(instanceId, updateInstanceRequest);
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **instanceId** | **string** | path | **required** | Instance identifier e.g. \&quot;b64135e7-98a0-41af-a845-d86167d54cc7\&quot;. |
| **updateInstanceRequest** | [UpdateInstanceRequest?](UpdateInstanceRequest?.md) | body | optional | The new integration instance. |

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: `application/json`
 - **Accept**: `application/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | No Content |  -  |
| **400** | The details of the input related failure |  -  |
| **404** | The instance does not exist. |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateInstanceWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
apiInstance.UpdateInstanceWithHttpInfo(instanceId, updateInstanceRequest);
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

