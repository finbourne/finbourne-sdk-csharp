# Finbourne.Sdk.Lusid.Api.TransferAgencyApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CalculateOrderDates**](#calculateorderdates) | **POST** `/api/api/transferagency/orderdates` | [EXPERIMENTAL] CalculateOrderDates: Calculate the key dates associated with transfer agency orders |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TransferAgencyApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
```

---

<a id="calculateorderdates"></a>
## CalculateOrderDates

> CalculateOrderDatesResponse CalculateOrderDates(Dictionary<string, CalculateOrderDatesRequest> requestBody)

[EXPERIMENTAL] CalculateOrderDates: Calculate the key dates associated with transfer agency orders

The response contains both the collection of successfully calculated dates and any failed calculations,  each in the form of a dictionary keyed by the request's keys.  For each failure, a reason is provided. It is important to check the failed set for unsuccessful results.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TransferAgencyApi>();
var requestBody = new Dictionary<string, CalculateOrderDatesRequest>(); // Dictionary<string, CalculateOrderDatesRequest>
CalculateOrderDatesResponse result = apiInstance.CalculateOrderDates(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, CalculateOrderDatesRequest&gt;](CalculateOrderDatesRequest.md) | body | **required** | The request containing the dates used for calculation |

### Return type

[CalculateOrderDatesResponse](CalculateOrderDatesResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Successfully calculated dates and any failed calculations. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CalculateOrderDatesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CalculateOrderDatesResponse> response = apiInstance.CalculateOrderDatesWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

