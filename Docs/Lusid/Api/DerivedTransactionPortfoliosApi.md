# Finbourne.Sdk.Lusid.Api.DerivedTransactionPortfoliosApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateDerivedPortfolio**](#createderivedportfolio) | **POST** `/api/api/derivedtransactionportfolios/{scope}` | CreateDerivedPortfolio: Create derived portfolio |
| [**DeleteDerivedPortfolioDetails**](#deletederivedportfoliodetails) | **DELETE** `/api/api/derivedtransactionportfolios/{scope}/{code}/details` | [EARLY ACCESS] DeleteDerivedPortfolioDetails: Delete derived portfolio details |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<DerivedTransactionPortfoliosApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DerivedTransactionPortfoliosApi>();
```

---

<a id="createderivedportfolio"></a>
## CreateDerivedPortfolio

> Portfolio CreateDerivedPortfolio(string scope, CreateDerivedTransactionPortfolioRequest? createDerivedTransactionPortfolioRequest = null)

CreateDerivedPortfolio: Create derived portfolio

Create a derived transaction portfolio from a parent transaction portfolio (which may itself be derived).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DerivedTransactionPortfoliosApi>();
var scope = "scope_example";  // string
var createDerivedTransactionPortfolioRequest = new CreateDerivedTransactionPortfolioRequest?(); // CreateDerivedTransactionPortfolioRequest? (optional)
Portfolio result = apiInstance.CreateDerivedPortfolio(scope, createDerivedTransactionPortfolioRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope in which to create the derived transaction portfolio. |
| **createDerivedTransactionPortfolioRequest** | [CreateDerivedTransactionPortfolioRequest?](CreateDerivedTransactionPortfolioRequest?.md) | body | optional | The definition of the derived transaction portfolio. |

### Return type

[Portfolio](Portfolio.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created derived portfolio, with populated id |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateDerivedPortfolioWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Portfolio> response = apiInstance.CreateDerivedPortfolioWithHttpInfo(scope, createDerivedTransactionPortfolioRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletederivedportfoliodetails"></a>
## DeleteDerivedPortfolioDetails

> DeletedEntityResponse DeleteDerivedPortfolioDetails(string scope, string code, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeleteDerivedPortfolioDetails: Delete derived portfolio details

Delete all the portfolio details for a derived transaction portfolio.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<DerivedTransactionPortfoliosApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteDerivedPortfolioDetails(scope, code, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the derived transaction portfolio. |
| **code** | **string** | path | **required** | The code of the derived transaction portfolio. Together with the scope this uniquely identifies              the derived transaction portfolio. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date of the change. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteDerivedPortfolioDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteDerivedPortfolioDetailsWithHttpInfo(scope, code, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

