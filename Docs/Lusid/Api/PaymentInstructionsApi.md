# Finbourne.Sdk.Lusid.Api.PaymentInstructionsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeletePaymentInstruction**](#deletepaymentinstruction) | **DELETE** `/api/api/paymentinstructions/{scope}/{code}` | [EXPERIMENTAL] DeletePaymentInstruction: Delete Payment Instruction |
| [**GetPaymentInstruction**](#getpaymentinstruction) | **GET** `/api/api/paymentinstructions/{scope}/{code}` | [EXPERIMENTAL] GetPaymentInstruction: Get Payment Instruction |
| [**GetPaymentInstructionsByPaymentRecordIds**](#getpaymentinstructionsbypaymentrecordids) | **POST** `/api/api/paymentinstructions/$getByPaymentRecordIds` | [EXPERIMENTAL] GetPaymentInstructionsByPaymentRecordIds: Get Payment Instructions by Payment Record Ids |
| [**UpsertPaymentInstructions**](#upsertpaymentinstructions) | **POST** `/api/api/paymentinstructions` | [EXPERIMENTAL] UpsertPaymentInstructions: Upsert Payment Instructions |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PaymentInstructionsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PaymentInstructionsApi>();
```

---

<a id="deletepaymentinstruction"></a>
## DeletePaymentInstruction

> DeletedEntityResponse DeletePaymentInstruction(string scope, string code)

[EXPERIMENTAL] DeletePaymentInstruction: Delete Payment Instruction

Delete a Payment Instruction. Deletion will be valid from the payment instruction's creation datetime.  This means that the payment instruction will no longer exist at any effective datetime from the asAt datetime  of deletion. Any payment records the instruction owns are released and become available to another instruction.  A payment instruction that has been released, instructed, sent, cancelled or failed cannot be deleted.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PaymentInstructionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeletePaymentInstruction(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the payment instruction. |
| **code** | **string** | path | **required** | The code of the payment instruction. |

### Return type

[DeletedEntityResponse](../Model/DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting the payment instruction |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePaymentInstructionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePaymentInstructionWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpaymentinstruction"></a>
## GetPaymentInstruction

> PaymentInstruction GetPaymentInstruction(string scope, string code, List<string>? propertyKeys = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetPaymentInstruction: Get Payment Instruction

Retrieve a single Payment Instruction.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PaymentInstructionsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var propertyKeys = new List<string>?(); // List<string>? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PaymentInstruction result = apiInstance.GetPaymentInstruction(scope, code, propertyKeys, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the payment instruction. |
| **code** | **string** | path | **required** | The code of the payment instruction. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the \&quot;PaymentInstruction\&quot; domain to decorate onto the              payment instruction. These take the format {domain}/{scope}/{code} e.g. \&quot;PaymentInstruction/myScope/myProperty\&quot;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the payment instruction.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the payment instruction. Defaults to return the latest              version of the payment instruction if not specified. |

### Return type

[PaymentInstruction](../Model/PaymentInstruction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested payment instruction |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPaymentInstructionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PaymentInstruction> response = apiInstance.GetPaymentInstructionWithHttpInfo(scope, code, propertyKeys, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpaymentinstructionsbypaymentrecordids"></a>
## GetPaymentInstructionsByPaymentRecordIds

> GetPaymentInstructionsResponse GetPaymentInstructionsByPaymentRecordIds(List<string> requestBody, List<string>? propertyKeys = null, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetPaymentInstructionsByPaymentRecordIds: Get Payment Instructions by Payment Record Ids

Retrieve the Payment Instructions that reference the given Payment Records. Payment record ids are unique  across the system scope, so no scope or identifier type is required. The response contains the payment  instructions that could be found, keyed by the payment record id used to retrieve them, along with the  nature of any failures.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PaymentInstructionsApi>();
var requestBody = new List<string>(); // List<string>
var propertyKeys = new List<string>?(); // List<string>? (optional)
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GetPaymentInstructionsResponse result = apiInstance.GetPaymentInstructionsByPaymentRecordIds(requestBody, propertyKeys, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [List&lt;string&gt;](../Model/string.md) | body | **required** | A collection of payment record ids to retrieve payment instructions for.              Duplicate ids are ignored. |
| **propertyKeys** | [List&lt;string&gt;?](../Model/string.md) | query | optional | A list of property keys from the \&quot;PaymentInstruction\&quot; domain to decorate onto each              payment instruction. These take the format {domain}/{scope}/{code} e.g. \&quot;PaymentInstruction/myScope/myProperty\&quot;. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the payment instructions.              Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the payment instructions. Defaults to return the latest              version of each payment instruction if not specified. |

### Return type

[GetPaymentInstructionsResponse](../Model/GetPaymentInstructionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The payment instructions that could be found for the supplied payment record ids, along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPaymentInstructionsByPaymentRecordIdsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GetPaymentInstructionsResponse> response = apiInstance.GetPaymentInstructionsByPaymentRecordIdsWithHttpInfo(requestBody, propertyKeys, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertpaymentinstructions"></a>
## UpsertPaymentInstructions

> PaymentInstructionsResponse UpsertPaymentInstructions(Dictionary<string, PaymentInstructionRequest> requestBody)

[EXPERIMENTAL] UpsertPaymentInstructions: Upsert Payment Instructions

Create or update a collection of Payment Instructions.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PaymentInstructionsApi>();
var requestBody = new Dictionary<string, PaymentInstructionRequest>(); // Dictionary<string, PaymentInstructionRequest>
PaymentInstructionsResponse result = apiInstance.UpsertPaymentInstructions(requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **requestBody** | [Dictionary&lt;string, PaymentInstructionRequest&gt;](../Model/PaymentInstructionRequest.md) | body | **required** | A collection of requests to create or update Payment Instructions. |

### Return type

[PaymentInstructionsResponse](../Model/PaymentInstructionsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The successfully created or updated payment instructions along with any failures |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPaymentInstructionsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PaymentInstructionsResponse> response = apiInstance.UpsertPaymentInstructionsWithHttpInfo(requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

