# Finbourne.Sdk.Lusid.Api.SimplePositionPortfoliosApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateSimplePositionPortfolio**](#createsimplepositionportfolio) | **POST** `/api/api/simpleposition/{scope}` | [EARLY ACCESS] CreateSimplePositionPortfolio: Create simple position portfolio |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SimplePositionPortfoliosApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SimplePositionPortfoliosApi>();
```

---

<a id="createsimplepositionportfolio"></a>
## CreateSimplePositionPortfolio

> Portfolio CreateSimplePositionPortfolio(string scope, CreateSimplePositionPortfolioRequest createSimplePositionPortfolioRequest)

[EARLY ACCESS] CreateSimplePositionPortfolio: Create simple position portfolio

Create a simple position portfolio in a particular scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SimplePositionPortfoliosApi>();
var scope = "scope_example";  // string
var createSimplePositionPortfolioRequest = new CreateSimplePositionPortfolioRequest(); // CreateSimplePositionPortfolioRequest
Portfolio result = apiInstance.CreateSimplePositionPortfolio(scope, createSimplePositionPortfolioRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create the simple position portfolio. |
| **createSimplePositionPortfolioRequest** | [CreateSimplePositionPortfolioRequest](CreateSimplePositionPortfolioRequest.md) | body | **required** | The definition of the simple position portfolio. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created simple position portfolio, with populated id |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateSimplePositionPortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.CreateSimplePositionPortfolioWithHttpInfo(scope, createSimplePositionPortfolioRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

