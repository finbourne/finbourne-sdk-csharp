# Finbourne.Sdk.Lusid.Api.TransfersApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateTransfer**](#createtransfer) | **POST** `/api/api/transfers` | [EXPERIMENTAL] CreateTransfer: Create a transfer. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransfersApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
```

---

<a id="createtransfer"></a>
## CreateTransfer

> CreateTransferResponse CreateTransfer(CreateTransferRequest createTransferRequest)

[EXPERIMENTAL] CreateTransfer: Create a transfer.

Move a position between two portfolios, exchange one instrument for another within a portfolio, or do  both at once.                The outgoing and incoming transaction legs and the Transfer entity recording them are written as a single  atomic operation: if any part of the request is rejected, nothing is written.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransfersApi>();
var createTransferRequest = new CreateTransferRequest(); // CreateTransferRequest
CreateTransferResponse result = apiInstance.CreateTransfer(createTransferRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **createTransferRequest** | [CreateTransferRequest](../Model/CreateTransferRequest.md) | body | **required** | The transfer to create. |

### Return type

[CreateTransferResponse](../Model/CreateTransferResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The transfer that was created. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateTransferWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CreateTransferResponse> response = apiInstance.CreateTransferWithHttpInfo(createTransferRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

