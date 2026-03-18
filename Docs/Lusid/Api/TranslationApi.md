# Finbourne.Sdk.Lusid.Api.TranslationApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**TranslateInstrumentDefinitions**](#translateinstrumentdefinitions) | **POST** `/api/api/translation/instrumentdefinitions` | [EXPERIMENTAL] TranslateInstrumentDefinitions: Translate instruments |
| [**TranslateTradeTickets**](#translatetradetickets) | **POST** `/api/api/translation/tradetickets` | [EXPERIMENTAL] TranslateTradeTickets: Translate trade ticket |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<TranslationApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TranslationApi>();
```

---

<a id="translateinstrumentdefinitions"></a>
## TranslateInstrumentDefinitions

> TranslateInstrumentDefinitionsResponse TranslateInstrumentDefinitions(TranslateInstrumentDefinitionsRequest translateInstrumentDefinitionsRequest)

[EXPERIMENTAL] TranslateInstrumentDefinitions: Translate instruments

Translates one or more instruments into the given target dialect.                In the request each instrument definition should be keyed by a unique correlation id. This id is ephemeral  and is not stored by LUSID. It serves only as a way to easily identify each instrument in the response.                Any instrument that is not already in the LUSID dialect should be given as an ExoticInstrument.                The response will return both the collection of successfully translated instruments in the target dialect,  as well as those that failed.  For the failures a reason will be provided explaining why the instrument could not be updated or inserted.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TranslationApi>();
var translateInstrumentDefinitionsRequest = new TranslateInstrumentDefinitionsRequest(); // TranslateInstrumentDefinitionsRequest
TranslateInstrumentDefinitionsResponse result = apiInstance.TranslateInstrumentDefinitions(translateInstrumentDefinitionsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **translateInstrumentDefinitionsRequest** | [TranslateInstrumentDefinitionsRequest](TranslateInstrumentDefinitionsRequest.md) | body | **required** | The definitions of the instruments to translate along with the target dialect. |

### Return type

[TranslateInstrumentDefinitionsResponse](TranslateInstrumentDefinitionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully translated instruments along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the TranslateInstrumentDefinitionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TranslateInstrumentDefinitionsResponse> response = apiInstance.TranslateInstrumentDefinitionsWithHttpInfo(translateInstrumentDefinitionsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="translatetradetickets"></a>
## TranslateTradeTickets

> TranslateTradeTicketsResponse TranslateTradeTickets(TranslateTradeTicketRequest translateTradeTicketRequest)

[EXPERIMENTAL] TranslateTradeTickets: Translate trade ticket

Translates one or more trade tickets into the given target dialect.                In the request each trade ticket definition should be keyed by a unique correlation id. This id is ephemeral  and is not stored by LUSID. It serves only as a way to easily identify each trade ticket in the response.                The response will return both the collection of successfully translated trade tickets in the target dialect,  as well as those that failed.  For the failures a reason will be provided explaining why the trade ticket could not be updated or inserted.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<TranslationApi>();
var translateTradeTicketRequest = new TranslateTradeTicketRequest(); // TranslateTradeTicketRequest
TranslateTradeTicketsResponse result = apiInstance.TranslateTradeTickets(translateTradeTicketRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **translateTradeTicketRequest** | [TranslateTradeTicketRequest](TranslateTradeTicketRequest.md) | body | **required** | The definitions of the trade ticket to translate along with the target dialect. |

### Return type

[TranslateTradeTicketsResponse](TranslateTradeTicketsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully translated trade ticket along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the TranslateTradeTicketsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<TranslateTradeTicketsResponse> response = apiInstance.TranslateTradeTicketsWithHttpInfo(translateTradeTicketRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

