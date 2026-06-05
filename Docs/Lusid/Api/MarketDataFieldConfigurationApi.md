# Finbourne.Sdk.Lusid.Api.MarketDataFieldConfigurationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetMarketDataFieldConfiguration**](#getmarketdatafieldconfiguration) | **GET** `/api/api/marketdata/fieldconfiguration/{marketDataCategory}` | [EARLY ACCESS] GetMarketDataFieldConfiguration: Get a Market Data Field Configuration |
| [**UpdateMarketDataFieldConfiguration**](#updatemarketdatafieldconfiguration) | **POST** `/api/api/marketdata/fieldconfiguration/{marketDataCategory}/$update` | [EARLY ACCESS] UpdateMarketDataFieldConfiguration: Update a Market Data Field Configuration |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<MarketDataFieldConfigurationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MarketDataFieldConfigurationApi>();
```

---

<a id="getmarketdatafieldconfiguration"></a>
## GetMarketDataFieldConfiguration

> MarketDataFieldConfiguration GetMarketDataFieldConfiguration(string marketDataCategory, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetMarketDataFieldConfiguration: Get a Market Data Field Configuration

Retrieve the market data field configuration for a given market data category.  If the configuration does not yet exist, an empty configuration will be returned.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MarketDataFieldConfigurationApi>();
var marketDataCategory = "marketDataCategory_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
MarketDataFieldConfiguration result = apiInstance.GetMarketDataFieldConfiguration(marketDataCategory, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **marketDataCategory** | **string** | path | **required** | The market data category. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the configuration. Defaults to return the latest version if not specified. |

### Return type

[MarketDataFieldConfiguration](MarketDataFieldConfiguration.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested market data field configuration. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetMarketDataFieldConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarketDataFieldConfiguration> response = apiInstance.GetMarketDataFieldConfigurationWithHttpInfo(marketDataCategory, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updatemarketdatafieldconfiguration"></a>
## UpdateMarketDataFieldConfiguration

> MarketDataFieldConfiguration UpdateMarketDataFieldConfiguration(string marketDataCategory, UpdateMarketDataFieldConfigurationRequest updateMarketDataFieldConfigurationRequest)

[EARLY ACCESS] UpdateMarketDataFieldConfiguration: Update a Market Data Field Configuration

Update the metadata field schema for a market data field configuration.  Allows adding, updating, and removing metadata field definitions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<MarketDataFieldConfigurationApi>();
var marketDataCategory = "marketDataCategory_example";  // string
var updateMarketDataFieldConfigurationRequest = new UpdateMarketDataFieldConfigurationRequest(); // UpdateMarketDataFieldConfigurationRequest
MarketDataFieldConfiguration result = apiInstance.UpdateMarketDataFieldConfiguration(marketDataCategory, updateMarketDataFieldConfigurationRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **marketDataCategory** | **string** | path | **required** | The market data category. |
| **updateMarketDataFieldConfigurationRequest** | [UpdateMarketDataFieldConfigurationRequest](UpdateMarketDataFieldConfigurationRequest.md) | body | **required** | The metadata fields to add, update, or remove. |

### Return type

[MarketDataFieldConfiguration](MarketDataFieldConfiguration.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated market data field configuration. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdateMarketDataFieldConfigurationWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<MarketDataFieldConfiguration> response = apiInstance.UpdateMarketDataFieldConfigurationWithHttpInfo(marketDataCategory, updateMarketDataFieldConfigurationRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

