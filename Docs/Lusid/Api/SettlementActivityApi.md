# Finbourne.Sdk.Lusid.Api.SettlementActivityApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**QuerySettlementActivity**](#querysettlementactivity) | **POST** `/api/api/settlementactivities/$query` | [EARLY ACCESS] QuerySettlementActivity: Query Settlement Activity |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<SettlementActivityApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SettlementActivityApi>();
```

---

<a id="querysettlementactivity"></a>
## QuerySettlementActivity

> ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery QuerySettlementActivity(SettlementActivityQuery settlementActivityQuery)

[EARLY ACCESS] QuerySettlementActivity: Query Settlement Activity

Queries settlement activity (Expected and Settled) for the specified portfolios and/or portfolio groups.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<SettlementActivityApi>();
var settlementActivityQuery = new SettlementActivityQuery(); // SettlementActivityQuery
ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery result = apiInstance.QuerySettlementActivity(settlementActivityQuery);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **settlementActivityQuery** | [SettlementActivityQuery](SettlementActivityQuery.md) | body | **required** | The query parameters controlling which settlement activity is returned. |

### Return type

[ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery](ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested settlement activity for the specified portfolios and portfolio groups |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the QuerySettlementActivityWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListWithPostBodiesOfSettlementActivityToSettlementActivityQuery> response = apiInstance.QuerySettlementActivityWithHttpInfo(settlementActivityQuery);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

