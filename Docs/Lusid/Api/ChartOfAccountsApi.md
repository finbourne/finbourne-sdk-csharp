# Finbourne.Sdk.Lusid.Api.ChartOfAccountsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateChartOfAccounts**](#createchartofaccounts) | **POST** `/api/api/chartofaccounts/{scope}` | [EXPERIMENTAL] CreateChartOfAccounts: Create a Chart of Accounts |
| [**CreateCleardownModule**](#createcleardownmodule) | **POST** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules` | [EXPERIMENTAL] CreateCleardownModule: Create a Cleardown Module |
| [**CreateGeneralLedgerProfile**](#creategeneralledgerprofile) | **POST** `/api/api/chartofaccounts/{scope}/{code}/generalledgerprofile` | [EXPERIMENTAL] CreateGeneralLedgerProfile: Create a General Ledger Profile. |
| [**CreatePostingModule**](#createpostingmodule) | **POST** `/api/api/chartofaccounts/{scope}/{code}/postingmodules` | [EXPERIMENTAL] CreatePostingModule: Create a Posting Module |
| [**DeleteAccounts**](#deleteaccounts) | **POST** `/api/api/chartofaccounts/{scope}/{code}/accounts/$delete` | [EXPERIMENTAL] DeleteAccounts: Soft or hard delete multiple accounts |
| [**DeleteChartOfAccounts**](#deletechartofaccounts) | **DELETE** `/api/api/chartofaccounts/{scope}/{code}` | [EXPERIMENTAL] DeleteChartOfAccounts: Delete a Chart of Accounts |
| [**DeleteCleardownModule**](#deletecleardownmodule) | **DELETE** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules/{cleardownModuleCode}` | [EXPERIMENTAL] DeleteCleardownModule: Delete a Cleardown Module. |
| [**DeleteGeneralLedgerProfile**](#deletegeneralledgerprofile) | **DELETE** `/api/api/chartofaccounts/{scope}/{code}/generalledgerprofile/{generalLedgerProfileCode}` | [EXPERIMENTAL] DeleteGeneralLedgerProfile: Delete a General Ledger Profile. |
| [**DeletePostingModule**](#deletepostingmodule) | **DELETE** `/api/api/chartofaccounts/{scope}/{code}/postingmodules/{postingModuleCode}` | [EXPERIMENTAL] DeletePostingModule: Delete a Posting Module. |
| [**GetAccount**](#getaccount) | **GET** `/api/api/chartofaccounts/{scope}/{code}/accounts/{accountCode}` | [EXPERIMENTAL] GetAccount: Get Account |
| [**GetAccountProperties**](#getaccountproperties) | **GET** `/api/api/chartofaccounts/{scope}/{code}/accounts/{accountCode}/properties` | [EXPERIMENTAL] GetAccountProperties: Get Account properties |
| [**GetChartOfAccounts**](#getchartofaccounts) | **GET** `/api/api/chartofaccounts/{scope}/{code}` | [EXPERIMENTAL] GetChartOfAccounts: Get ChartOfAccounts |
| [**GetChartOfAccountsProperties**](#getchartofaccountsproperties) | **GET** `/api/api/chartofaccounts/{scope}/{code}/properties` | [EXPERIMENTAL] GetChartOfAccountsProperties: Get chart of accounts properties |
| [**GetCleardownModule**](#getcleardownmodule) | **GET** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules/{cleardownModuleCode}` | [EXPERIMENTAL] GetCleardownModule: Get a Cleardown Module |
| [**GetGeneralLedgerProfile**](#getgeneralledgerprofile) | **GET** `/api/api/chartofaccounts/{scope}/{code}/generalledgerprofile/{generalLedgerProfileCode}` | [EXPERIMENTAL] GetGeneralLedgerProfile: Get a General Ledger Profile. |
| [**GetPostingModule**](#getpostingmodule) | **GET** `/api/api/chartofaccounts/{scope}/{code}/postingmodules/{postingModuleCode}` | [EXPERIMENTAL] GetPostingModule: Get a Posting Module |
| [**ListAccounts**](#listaccounts) | **GET** `/api/api/chartofaccounts/{scope}/{code}/accounts` | [EXPERIMENTAL] ListAccounts: List Accounts |
| [**ListChartsOfAccounts**](#listchartsofaccounts) | **GET** `/api/api/chartofaccounts` | [EXPERIMENTAL] ListChartsOfAccounts: List Charts of Accounts |
| [**ListCleardownModuleRules**](#listcleardownmodulerules) | **GET** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules/{cleardownModuleCode}/cleardownrules` | [EXPERIMENTAL] ListCleardownModuleRules: List Cleardown Module Rules |
| [**ListCleardownModules**](#listcleardownmodules) | **GET** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules` | [EXPERIMENTAL] ListCleardownModules: List Cleardown Modules |
| [**ListGeneralLedgerProfiles**](#listgeneralledgerprofiles) | **GET** `/api/api/chartofaccounts/{scope}/{code}/generalledgerprofile` | [EXPERIMENTAL] ListGeneralLedgerProfiles: List General Ledger Profiles. |
| [**ListPostingModuleRules**](#listpostingmodulerules) | **GET** `/api/api/chartofaccounts/{scope}/{code}/postingmodules/{postingModuleCode}/postingrules` | [EXPERIMENTAL] ListPostingModuleRules: List Posting Module Rules |
| [**ListPostingModules**](#listpostingmodules) | **GET** `/api/api/chartofaccounts/{scope}/{code}/postingmodules` | [EXPERIMENTAL] ListPostingModules: List Posting Modules |
| [**PatchChartOfAccounts**](#patchchartofaccounts) | **PATCH** `/api/api/chartofaccounts/{scope}/{code}` | [EXPERIMENTAL] PatchChartOfAccounts: Patch a Chart of Accounts. |
| [**PatchCleardownModule**](#patchcleardownmodule) | **PATCH** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules/{cleardownModuleCode}` | [EXPERIMENTAL] PatchCleardownModule: Patch a Cleardown Module |
| [**PatchPostingModule**](#patchpostingmodule) | **PATCH** `/api/api/chartofaccounts/{scope}/{code}/postingmodules/{postingModuleCode}` | [EXPERIMENTAL] PatchPostingModule: Patch a Posting Module |
| [**SetCleardownModuleDetails**](#setcleardownmoduledetails) | **PUT** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules/{cleardownModuleCode}` | [EXPERIMENTAL] SetCleardownModuleDetails: Set the details of a Cleardown Module |
| [**SetCleardownModuleRules**](#setcleardownmodulerules) | **PUT** `/api/api/chartofaccounts/{scope}/{code}/cleardownmodules/{cleardownModuleCode}/cleardownrules` | [EXPERIMENTAL] SetCleardownModuleRules: Set the rules of a Cleardown Module |
| [**SetGeneralLedgerProfileMappings**](#setgeneralledgerprofilemappings) | **PUT** `/api/api/chartofaccounts/{scope}/{code}/generalledgerprofile/{generalLedgerProfileCode}/mappings` | [EXPERIMENTAL] SetGeneralLedgerProfileMappings: Sets the General Ledger Profile Mappings. |
| [**SetPostingModuleDetails**](#setpostingmoduledetails) | **PUT** `/api/api/chartofaccounts/{scope}/{code}/postingmodules/{postingModuleCode}` | [EXPERIMENTAL] SetPostingModuleDetails: Set the details of a Posting Module |
| [**SetPostingModuleRules**](#setpostingmodulerules) | **PUT** `/api/api/chartofaccounts/{scope}/{code}/postingmodules/{postingModuleCode}/postingrules` | [EXPERIMENTAL] SetPostingModuleRules: Set the rules of a Posting Module |
| [**UpsertAccountProperties**](#upsertaccountproperties) | **POST** `/api/api/chartofaccounts/{scope}/{code}/accounts/{accountCode}/properties/$upsert` | [EXPERIMENTAL] UpsertAccountProperties: Upsert account properties |
| [**UpsertAccounts**](#upsertaccounts) | **POST** `/api/api/chartofaccounts/{scope}/{code}/accounts` | [EXPERIMENTAL] UpsertAccounts: Upsert Accounts |
| [**UpsertChartOfAccountsProperties**](#upsertchartofaccountsproperties) | **POST** `/api/api/chartofaccounts/{scope}/{code}/properties/$upsert` | [EXPERIMENTAL] UpsertChartOfAccountsProperties: Upsert Chart of Accounts properties |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ChartOfAccountsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
```

---

<a id="createchartofaccounts"></a>
## CreateChartOfAccounts

> ChartOfAccounts CreateChartOfAccounts(string scope, ChartOfAccountsRequest chartOfAccountsRequest)

[EXPERIMENTAL] CreateChartOfAccounts: Create a Chart of Accounts

Create the given Chart of Accounts.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var chartOfAccountsRequest = new ChartOfAccountsRequest(); // ChartOfAccountsRequest
ChartOfAccounts result = apiInstance.CreateChartOfAccounts(scope, chartOfAccountsRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **chartOfAccountsRequest** | [ChartOfAccountsRequest](ChartOfAccountsRequest.md) | body | **required** | The definition of the Chart of Accounts. |

### Return type

[ChartOfAccounts](ChartOfAccounts.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Chart of Accounts. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateChartOfAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ChartOfAccounts> response = apiInstance.CreateChartOfAccountsWithHttpInfo(scope, chartOfAccountsRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createcleardownmodule"></a>
## CreateCleardownModule

> CleardownModuleResponse CreateCleardownModule(string scope, string code, CleardownModuleRequest cleardownModuleRequest)

[EXPERIMENTAL] CreateCleardownModule: Create a Cleardown Module

Create the given Cleardown Module.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleRequest = new CleardownModuleRequest(); // CleardownModuleRequest
CleardownModuleResponse result = apiInstance.CreateCleardownModule(scope, code, cleardownModuleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleRequest** | [CleardownModuleRequest](CleardownModuleRequest.md) | body | **required** | The definition of the Cleardown Module. |

### Return type

[CleardownModuleResponse](CleardownModuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Cleardown Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateCleardownModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CleardownModuleResponse> response = apiInstance.CreateCleardownModuleWithHttpInfo(scope, code, cleardownModuleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="creategeneralledgerprofile"></a>
## CreateGeneralLedgerProfile

> GeneralLedgerProfileResponse CreateGeneralLedgerProfile(string scope, string code, GeneralLedgerProfileRequest generalLedgerProfileRequest)

[EXPERIMENTAL] CreateGeneralLedgerProfile: Create a General Ledger Profile.

Create the given General Ledger profile.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var generalLedgerProfileRequest = new GeneralLedgerProfileRequest(); // GeneralLedgerProfileRequest
GeneralLedgerProfileResponse result = apiInstance.CreateGeneralLedgerProfile(scope, code, generalLedgerProfileRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. |
| **generalLedgerProfileRequest** | [GeneralLedgerProfileRequest](GeneralLedgerProfileRequest.md) | body | **required** | The definition of the General Ledger Profile. |

### Return type

[GeneralLedgerProfileResponse](GeneralLedgerProfileResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created General Ledger Profile. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreateGeneralLedgerProfileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GeneralLedgerProfileResponse> response = apiInstance.CreateGeneralLedgerProfileWithHttpInfo(scope, code, generalLedgerProfileRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createpostingmodule"></a>
## CreatePostingModule

> PostingModuleResponse CreatePostingModule(string scope, string code, PostingModuleRequest postingModuleRequest)

[EXPERIMENTAL] CreatePostingModule: Create a Posting Module

Create the given Posting Module.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleRequest = new PostingModuleRequest(); // PostingModuleRequest
PostingModuleResponse result = apiInstance.CreatePostingModule(scope, code, postingModuleRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleRequest** | [PostingModuleRequest](PostingModuleRequest.md) | body | **required** | The definition of the Posting Module. |

### Return type

[PostingModuleResponse](PostingModuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created Posting Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePostingModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PostingModuleResponse> response = apiInstance.CreatePostingModuleWithHttpInfo(scope, code, postingModuleRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteaccounts"></a>
## DeleteAccounts

> DeleteAccountsResponse DeleteAccounts(string scope, string code, List<string> requestBody, string? deleteMode = null)

[EXPERIMENTAL] DeleteAccounts: Soft or hard delete multiple accounts

Delete one or more account from the Chart of Accounts. Soft deletion marks the account as inactive  While the Hard deletion is deleting the account.  The maximum number of accounts that this method can delete per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new List<string>(); // List<string>
var deleteMode = "Soft";  // string? (optional)
DeleteAccountsResponse result = apiInstance.DeleteAccounts(scope, code, requestBody, deleteMode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies              the Chart of Accounts. |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | The codes of the accounts to delete. |
| **deleteMode** | **string?** | query | optional | The delete mode to use (defaults to &#39;Soft&#39;). |

### Return type

[DeleteAccountsResponse](DeleteAccountsResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Accounts were deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeleteAccountsResponse> response = apiInstance.DeleteAccountsWithHttpInfo(scope, code, requestBody, deleteMode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletechartofaccounts"></a>
## DeleteChartOfAccounts

> DeletedEntityResponse DeleteChartOfAccounts(string scope, string code)

[EXPERIMENTAL] DeleteChartOfAccounts: Delete a Chart of Accounts

Delete the given Chart of Accounts.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeleteChartOfAccounts(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts to be deleted. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts to be deleted. Together with the scope this uniquely identifies the Chart of Accounts. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Chart of Accounts was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteChartOfAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteChartOfAccountsWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletecleardownmodule"></a>
## DeleteCleardownModule

> DeletedEntityResponse DeleteCleardownModule(string scope, string code, string cleardownModuleCode)

[EXPERIMENTAL] DeleteCleardownModule: Delete a Cleardown Module.

Delete the given Cleardown Module.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleCode = "cleardownModuleCode_example";  // string
DeletedEntityResponse result = apiInstance.DeleteCleardownModule(scope, code, cleardownModuleCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleCode** | **string** | path | **required** | The code of the Cleardown Module to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Cleardown Module was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteCleardownModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteCleardownModuleWithHttpInfo(scope, code, cleardownModuleCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletegeneralledgerprofile"></a>
## DeleteGeneralLedgerProfile

> DeletedEntityResponse DeleteGeneralLedgerProfile(string scope, string code, string generalLedgerProfileCode)

[EXPERIMENTAL] DeleteGeneralLedgerProfile: Delete a General Ledger Profile.

Delete the given General Ledger Profile.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var generalLedgerProfileCode = "generalLedgerProfileCode_example";  // string
DeletedEntityResponse result = apiInstance.DeleteGeneralLedgerProfile(scope, code, generalLedgerProfileCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts for the General Ledger Profile. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts for the General Ledger Profile. |
| **generalLedgerProfileCode** | **string** | path | **required** | The Code of the General Ledger Profile. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the General Ledger Profile was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteGeneralLedgerProfileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteGeneralLedgerProfileWithHttpInfo(scope, code, generalLedgerProfileCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletepostingmodule"></a>
## DeletePostingModule

> DeletedEntityResponse DeletePostingModule(string scope, string code, string postingModuleCode)

[EXPERIMENTAL] DeletePostingModule: Delete a Posting Module.

Delete the given Posting Module.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleCode = "postingModuleCode_example";  // string
DeletedEntityResponse result = apiInstance.DeletePostingModule(scope, code, postingModuleCode);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleCode** | **string** | path | **required** | The code of the Posting Module to be deleted. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the Posting Module was deleted. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePostingModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePostingModuleWithHttpInfo(scope, code, postingModuleCode);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaccount"></a>
## GetAccount

> Account GetAccount(string scope, string code, string accountCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetAccount: Get Account

Retrieve the definition of a particular Account which is part of a Chart of Accounts.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var accountCode = "accountCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Account result = apiInstance.GetAccount(scope, code, accountCode, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **accountCode** | **string** | path | **required** | The code of the Account. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Account properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Account definition. Defaults to returning the latest version of the Account definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Account&#39; domain to decorate onto the Account.              These must take the format {domain}/{scope}/{code}, for example &#39;Account/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[Account](Account.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Account definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAccountWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Account> response = apiInstance.GetAccountWithHttpInfo(scope, code, accountCode, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getaccountproperties"></a>
## GetAccountProperties

> AccountProperties GetAccountProperties(string scope, string code, string accountCode, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetAccountProperties: Get Account properties

Get all the properties of a single account.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var accountCode = "accountCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
AccountProperties result = apiInstance.GetAccountProperties(scope, code, accountCode, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts to update or insert the properties onto. Together with the scope this uniquely identifies the Chart of Accounts. |
| **accountCode** | **string** | path | **required** | The unique ID of the account to get properties for. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the Account&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Account&#39;s properties. Defaults to return the latest version of each property if not specified. |

### Return type

[AccountProperties](AccountProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified account |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetAccountPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AccountProperties> response = apiInstance.GetAccountPropertiesWithHttpInfo(scope, code, accountCode, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getchartofaccounts"></a>
## GetChartOfAccounts

> ChartOfAccounts GetChartOfAccounts(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetChartOfAccounts: Get ChartOfAccounts

Retrieve the definition of a particular Chart of Accounts.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
ChartOfAccounts result = apiInstance.GetChartOfAccounts(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the Chart of Accounts properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Chart of Accounts definition. Defaults to returning the latest version of the Chart of Accounts definition if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;ChartOfAccounts&#39; domain to decorate onto the Chart of Accounts.              These must take the format {domain}/{scope}/{code}, for example &#39;ChartOfAccounts/Manager/Id&#39;. If no properties are specified, then no properties will be returned. |

### Return type

[ChartOfAccounts](ChartOfAccounts.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Chart Of Accounts definition. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetChartOfAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ChartOfAccounts> response = apiInstance.GetChartOfAccountsWithHttpInfo(scope, code, effectiveAt, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getchartofaccountsproperties"></a>
## GetChartOfAccountsProperties

> ChartOfAccountsProperties GetChartOfAccountsProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetChartOfAccountsProperties: Get chart of accounts properties

Get all the properties of a single chart of accounts.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ChartOfAccountsProperties result = apiInstance.GetChartOfAccountsProperties(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the chart of accounts to list the properties for. |
| **code** | **string** | path | **required** | The code of the chart of accounts to list the properties for. Together with the scope this uniquely identifies the chart of accounts. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the chart of accounts&#39; properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the chart of accounts&#39; properties. Defaults to return the latest version of each property if not specified. |

### Return type

[ChartOfAccountsProperties](ChartOfAccountsProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified chartOfAccounts |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetChartOfAccountsPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ChartOfAccountsProperties> response = apiInstance.GetChartOfAccountsPropertiesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcleardownmodule"></a>
## GetCleardownModule

> CleardownModuleResponse GetCleardownModule(string scope, string code, string cleardownModuleCode, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetCleardownModule: Get a Cleardown Module

Retrieve the definition of a Cleardown Module complete with its rules.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleCode = "cleardownModuleCode_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
CleardownModuleResponse result = apiInstance.GetCleardownModule(scope, code, cleardownModuleCode, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleCode** | **string** | path | **required** | The code of the Cleardown Module. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Cleardown Module. Defaults to return the latest version of the Cleardown Module if not specified. |

### Return type

[CleardownModuleResponse](CleardownModuleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The full definition of the Cleardown Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCleardownModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CleardownModuleResponse> response = apiInstance.GetCleardownModuleWithHttpInfo(scope, code, cleardownModuleCode, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getgeneralledgerprofile"></a>
## GetGeneralLedgerProfile

> GeneralLedgerProfileResponse GetGeneralLedgerProfile(string scope, string code, string generalLedgerProfileCode, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetGeneralLedgerProfile: Get a General Ledger Profile.

Get the given General Ledger Profile.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var generalLedgerProfileCode = "generalLedgerProfileCode_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
GeneralLedgerProfileResponse result = apiInstance.GetGeneralLedgerProfile(scope, code, generalLedgerProfileCode, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts for the General Ledger Profile. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts for the General Ledger Profile. |
| **generalLedgerProfileCode** | **string** | path | **required** | The General Ledger Profile Code of the General Ledger Profile. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the General Ledger Profile. Defaults to return the latest version of the General Ledger Profile if not specified. |

### Return type

[GeneralLedgerProfileResponse](GeneralLedgerProfileResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested General Ledger Profile entry. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetGeneralLedgerProfileWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GeneralLedgerProfileResponse> response = apiInstance.GetGeneralLedgerProfileWithHttpInfo(scope, code, generalLedgerProfileCode, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpostingmodule"></a>
## GetPostingModule

> PostingModuleResponse GetPostingModule(string scope, string code, string postingModuleCode, DateTimeOffset? asAt = null)

[EXPERIMENTAL] GetPostingModule: Get a Posting Module

Retrieve the definition of a Posting Module complete with its rules.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleCode = "postingModuleCode_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PostingModuleResponse result = apiInstance.GetPostingModule(scope, code, postingModuleCode, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleCode** | **string** | path | **required** | The code of the Posting Module. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Posting Module. Defaults to return the latest version of the Posting Module if not specified. |

### Return type

[PostingModuleResponse](PostingModuleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The full definition of the Posting Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPostingModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PostingModuleResponse> response = apiInstance.GetPostingModuleWithHttpInfo(scope, code, postingModuleCode, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listaccounts"></a>
## ListAccounts

> PagedResourceListOfAccount ListAccounts(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListAccounts: List Accounts

List the accounts in a Chart of Accounts

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfAccount result = apiInstance.ListAccounts(scope, code, effectiveAt, asAt, page, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies              the Chart of Accounts. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties decorated on Accounts. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Accounts. Defaults to              returning the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing charts of accounts; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Account type, specify \&quot;code eq &#39;001&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;Account&#39; domain to decorate onto the Account.              These must have the format {domain}/{scope}/{code}, for example &#39;Account/system/Name&#39;. |

### Return type

[PagedResourceListOfAccount](PagedResourceListOfAccount.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Accounts in the given Chart of Accounts. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfAccount> response = apiInstance.ListAccountsWithHttpInfo(scope, code, effectiveAt, asAt, page, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listchartsofaccounts"></a>
## ListChartsOfAccounts

> PagedResourceListOfChartOfAccounts ListChartsOfAccounts(DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListChartsOfAccounts: List Charts of Accounts

List all the Charts of Accounts matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfChartOfAccounts result = apiInstance.ListChartsOfAccounts(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the TimeVariant properties for the Chart Of Accounts. Defaults to the current LUSID              system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the charts of accounts. Defaults to returning the latest version              of each Chart of Accounts if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing charts of accounts; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Chart of Accounts type, specify \&quot;id.Code eq &#39;001&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the &#39;ChartOfAccounts&#39; domain to decorate onto each Chart of Accounts.              These must take the format {domain}/{scope}/{code}, for example &#39;ChartOfAccounts/Manager/Id&#39;. |

### Return type

[PagedResourceListOfChartOfAccounts](PagedResourceListOfChartOfAccounts.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Charts of Accounts. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListChartsOfAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfChartOfAccounts> response = apiInstance.ListChartsOfAccountsWithHttpInfo(effectiveAt, asAt, page, limit, filter, sortBy, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcleardownmodulerules"></a>
## ListCleardownModuleRules

> PagedResourceListOfCleardownModuleRule ListCleardownModuleRules(string scope, string code, string cleardownModuleCode, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListCleardownModuleRules: List Cleardown Module Rules

List the Rules in a Cleardown Module

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleCode = "cleardownModuleCode_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfCleardownModuleRule result = apiInstance.ListCleardownModuleRules(scope, code, cleardownModuleCode, asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleCode** | **string** | path | **required** | The code of the cleardown module. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument. Defaults to              returning the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing cleardown module rules; this              value is returned from the previous call. If a pagination token is provided, the filter              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the rule id, specify \&quot;ruleId eq &#39;rule 1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |

### Return type

[PagedResourceListOfCleardownModuleRule](PagedResourceListOfCleardownModuleRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rules in the given Cleardown Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCleardownModuleRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCleardownModuleRule> response = apiInstance.ListCleardownModuleRulesWithHttpInfo(scope, code, cleardownModuleCode, asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listcleardownmodules"></a>
## ListCleardownModules

> PagedResourceListOfCleardownModuleResponse ListCleardownModules(string scope, string code, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListCleardownModules: List Cleardown Modules

List all the Cleardown Modules matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfCleardownModuleResponse result = apiInstance.ListCleardownModules(scope, code, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Cleardown Module. Defaults to returning the latest version              of each Cleardown Module if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Cleardown Modules; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Cleardown Module status, specify \&quot;status eq &#39;Active&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfCleardownModuleResponse](PagedResourceListOfCleardownModuleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Cleardown Modules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListCleardownModulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfCleardownModuleResponse> response = apiInstance.ListCleardownModulesWithHttpInfo(scope, code, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listgeneralledgerprofiles"></a>
## ListGeneralLedgerProfiles

> PagedResourceListOfGeneralLedgerProfileResponse ListGeneralLedgerProfiles(string scope, string code, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListGeneralLedgerProfiles: List General Ledger Profiles.

List all the General Ledger profiles matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfGeneralLedgerProfileResponse result = apiInstance.ListGeneralLedgerProfiles(scope, code, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts |
| **code** | **string** | path | **required** | The code of the Chart of Accounts |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the General Ledger Profiles. Defaults to returning the latest version of each General Ledger Profile if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing General Ledger Profiles; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the General Ledger profiles type, specify \&quot;type eq &#39;PeriodBoundary&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfGeneralLedgerProfileResponse](PagedResourceListOfGeneralLedgerProfileResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested General Ledger Profile entries. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListGeneralLedgerProfilesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfGeneralLedgerProfileResponse> response = apiInstance.ListGeneralLedgerProfilesWithHttpInfo(scope, code, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpostingmodulerules"></a>
## ListPostingModuleRules

> PagedResourceListOfPostingModuleRule ListPostingModuleRules(string scope, string code, string postingModuleCode, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null)

[EXPERIMENTAL] ListPostingModuleRules: List Posting Module Rules

List the Rules in a Posting Module

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleCode = "postingModuleCode_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
PagedResourceListOfPostingModuleRule result = apiInstance.ListPostingModuleRules(scope, code, postingModuleCode, asAt, page, limit, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleCode** | **string** | path | **required** | The code of the posting module. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the instrument. Defaults to              returning the latest version if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing posting module rules; this              value is returned from the previous call. If a pagination token is provided, the filter              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the rule id, specify \&quot;ruleId eq &#39;rule 1&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |

### Return type

[PagedResourceListOfPostingModuleRule](PagedResourceListOfPostingModuleRule.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The rules in the given Posting Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPostingModuleRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPostingModuleRule> response = apiInstance.ListPostingModuleRulesWithHttpInfo(scope, code, postingModuleCode, asAt, page, limit, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpostingmodules"></a>
## ListPostingModules

> PagedResourceListOfPostingModuleResponse ListPostingModules(string scope, string code, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null)

[EXPERIMENTAL] ListPostingModules: List Posting Modules

List all the Posting Modules matching particular criteria.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
PagedResourceListOfPostingModuleResponse result = apiInstance.ListPostingModules(scope, code, asAt, page, limit, filter, sortBy);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the Posting Module. Defaults to returning the latest version              of each Posting Module if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing Posting Modules; this              value is returned from the previous call. If a pagination token is provided, the filter, effectiveAt              and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the results to this number. Defaults to 100 if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the results.              For example, to filter on the Posting Module status, specify \&quot;status eq &#39;Active&#39;\&quot;. For more information about filtering              results, see https://support.lusid.com/knowledgebase/article/KA-01914. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |

### Return type

[PagedResourceListOfPostingModuleResponse](PagedResourceListOfPostingModuleResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested Posting Modules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPostingModulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPostingModuleResponse> response = apiInstance.ListPostingModulesWithHttpInfo(scope, code, asAt, page, limit, filter, sortBy);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchchartofaccounts"></a>
## PatchChartOfAccounts

> ChartOfAccounts PatchChartOfAccounts(string scope, string code, List<Operation> operation)

[EXPERIMENTAL] PatchChartOfAccounts: Patch a Chart of Accounts.

Update fields on a Chart of Accounts.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var operation = new List<Operation>(); // List<Operation>
ChartOfAccounts result = apiInstance.PatchChartOfAccounts(scope, code, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[ChartOfAccounts](ChartOfAccounts.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Chart of Accounts. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchChartOfAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ChartOfAccounts> response = apiInstance.PatchChartOfAccountsWithHttpInfo(scope, code, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchcleardownmodule"></a>
## PatchCleardownModule

> CleardownModuleResponse PatchCleardownModule(string scope, string code, string cleardownModuleCode, List<Operation> operation)

[EXPERIMENTAL] PatchCleardownModule: Patch a Cleardown Module

Update fields on a Cleardown Module.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description, Rules.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleCode = "cleardownModuleCode_example";  // string
var operation = new List<Operation>(); // List<Operation>
CleardownModuleResponse result = apiInstance.PatchCleardownModule(scope, code, cleardownModuleCode, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleCode** | **string** | path | **required** | The code of the Cleardown Module to be updated. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[CleardownModuleResponse](CleardownModuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Cleardown Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchCleardownModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CleardownModuleResponse> response = apiInstance.PatchCleardownModuleWithHttpInfo(scope, code, cleardownModuleCode, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchpostingmodule"></a>
## PatchPostingModule

> PostingModuleResponse PatchPostingModule(string scope, string code, string postingModuleCode, List<Operation> operation)

[EXPERIMENTAL] PatchPostingModule: Patch a Posting Module

Update fields on a Posting Module.  The behaviour is defined by the JSON Patch specification.    Currently supported fields are: DisplayName, Description, Rules.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleCode = "postingModuleCode_example";  // string
var operation = new List<Operation>(); // List<Operation>
PostingModuleResponse result = apiInstance.PatchPostingModule(scope, code, postingModuleCode, operation);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleCode** | **string** | path | **required** | The code of the Posting Module to be updated. |
| **operation** | [List&lt;Operation&gt;](Operation.md) | body | **required** | The json patch document. For more information see: https://datatracker.ietf.org/doc/html/rfc6902. |

### Return type

[PostingModuleResponse](PostingModuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Posting Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchPostingModuleWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PostingModuleResponse> response = apiInstance.PatchPostingModuleWithHttpInfo(scope, code, postingModuleCode, operation);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setcleardownmoduledetails"></a>
## SetCleardownModuleDetails

> CleardownModuleResponse SetCleardownModuleDetails(string scope, string code, string cleardownModuleCode, CleardownModuleDetails cleardownModuleDetails)

[EXPERIMENTAL] SetCleardownModuleDetails: Set the details of a Cleardown Module

Update the given Cleardown Module details.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleCode = "cleardownModuleCode_example";  // string
var cleardownModuleDetails = new CleardownModuleDetails(); // CleardownModuleDetails
CleardownModuleResponse result = apiInstance.SetCleardownModuleDetails(scope, code, cleardownModuleCode, cleardownModuleDetails);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleCode** | **string** | path | **required** | The code of the Cleardown Module to be updated. |
| **cleardownModuleDetails** | [CleardownModuleDetails](CleardownModuleDetails.md) | body | **required** | The new details for the Cleardown Module. |

### Return type

[CleardownModuleResponse](CleardownModuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Cleardown Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetCleardownModuleDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CleardownModuleResponse> response = apiInstance.SetCleardownModuleDetailsWithHttpInfo(scope, code, cleardownModuleCode, cleardownModuleDetails);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setcleardownmodulerules"></a>
## SetCleardownModuleRules

> CleardownModuleRulesUpdatedResponse SetCleardownModuleRules(string scope, string code, string cleardownModuleCode, List<CleardownModuleRule> cleardownModuleRule)

[EXPERIMENTAL] SetCleardownModuleRules: Set the rules of a Cleardown Module

Set the given Cleardown Modules rules, this will replace the existing set of rules for the cleardown module.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var cleardownModuleCode = "cleardownModuleCode_example";  // string
var cleardownModuleRule = new List<CleardownModuleRule>(); // List<CleardownModuleRule>
CleardownModuleRulesUpdatedResponse result = apiInstance.SetCleardownModuleRules(scope, code, cleardownModuleCode, cleardownModuleRule);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **cleardownModuleCode** | **string** | path | **required** | The code of the Cleardown Module to be updated. |
| **cleardownModuleRule** | [List&lt;CleardownModuleRule&gt;](CleardownModuleRule.md) | body | **required** | The new rule set for the Cleardown Module. |

### Return type

[CleardownModuleRulesUpdatedResponse](CleardownModuleRulesUpdatedResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Cleardown Module with updated rules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetCleardownModuleRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CleardownModuleRulesUpdatedResponse> response = apiInstance.SetCleardownModuleRulesWithHttpInfo(scope, code, cleardownModuleCode, cleardownModuleRule);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setgeneralledgerprofilemappings"></a>
## SetGeneralLedgerProfileMappings

> GeneralLedgerProfileResponse SetGeneralLedgerProfileMappings(string scope, string code, string generalLedgerProfileCode, List<GeneralLedgerProfileMapping> generalLedgerProfileMapping)

[EXPERIMENTAL] SetGeneralLedgerProfileMappings: Sets the General Ledger Profile Mappings.

Update the given General Ledger profile Mappings.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var generalLedgerProfileCode = "generalLedgerProfileCode_example";  // string
var generalLedgerProfileMapping = new List<GeneralLedgerProfileMapping>(); // List<GeneralLedgerProfileMapping>
GeneralLedgerProfileResponse result = apiInstance.SetGeneralLedgerProfileMappings(scope, code, generalLedgerProfileCode, generalLedgerProfileMapping);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. |
| **generalLedgerProfileCode** | **string** | path | **required** | The code of the General Ledger Profile |
| **generalLedgerProfileMapping** | [List&lt;GeneralLedgerProfileMapping&gt;](GeneralLedgerProfileMapping.md) | body | **required** | The updated General Ledger Profile Mappings, the previous mappings will be wholly replaced with this data. Mappings will be evaluated in the order they are provided. |

### Return type

[GeneralLedgerProfileResponse](GeneralLedgerProfileResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The General Ledger Profile that holds the updated mappings. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetGeneralLedgerProfileMappingsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<GeneralLedgerProfileResponse> response = apiInstance.SetGeneralLedgerProfileMappingsWithHttpInfo(scope, code, generalLedgerProfileCode, generalLedgerProfileMapping);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setpostingmoduledetails"></a>
## SetPostingModuleDetails

> PostingModuleResponse SetPostingModuleDetails(string scope, string code, string postingModuleCode, PostingModuleDetails postingModuleDetails)

[EXPERIMENTAL] SetPostingModuleDetails: Set the details of a Posting Module

Update the given Posting Module details.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleCode = "postingModuleCode_example";  // string
var postingModuleDetails = new PostingModuleDetails(); // PostingModuleDetails
PostingModuleResponse result = apiInstance.SetPostingModuleDetails(scope, code, postingModuleCode, postingModuleDetails);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleCode** | **string** | path | **required** | The code of the Posting Module to be updated. |
| **postingModuleDetails** | [PostingModuleDetails](PostingModuleDetails.md) | body | **required** | The new details for the Posting Module. |

### Return type

[PostingModuleResponse](PostingModuleResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated Posting Module. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPostingModuleDetailsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PostingModuleResponse> response = apiInstance.SetPostingModuleDetailsWithHttpInfo(scope, code, postingModuleCode, postingModuleDetails);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setpostingmodulerules"></a>
## SetPostingModuleRules

> PostingModuleRulesUpdatedResponse SetPostingModuleRules(string scope, string code, string postingModuleCode, List<PostingModuleRule> postingModuleRule)

[EXPERIMENTAL] SetPostingModuleRules: Set the rules of a Posting Module

Set the given Posting Modules rules, this will replace the existing set of rules for the posting module.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var postingModuleCode = "postingModuleCode_example";  // string
var postingModuleRule = new List<PostingModuleRule>(); // List<PostingModuleRule>
PostingModuleRulesUpdatedResponse result = apiInstance.SetPostingModuleRules(scope, code, postingModuleCode, postingModuleRule);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies the Chart of Accounts. |
| **postingModuleCode** | **string** | path | **required** | The code of the Posting Module to be updated. |
| **postingModuleRule** | [List&lt;PostingModuleRule&gt;](PostingModuleRule.md) | body | **required** | The new rule set for the Posting Module. |

### Return type

[PostingModuleRulesUpdatedResponse](PostingModuleRulesUpdatedResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The Posting Module with updated rules. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPostingModuleRulesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PostingModuleRulesUpdatedResponse> response = apiInstance.SetPostingModuleRulesWithHttpInfo(scope, code, postingModuleCode, postingModuleRule);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertaccountproperties"></a>
## UpsertAccountProperties

> AccountProperties UpsertAccountProperties(string scope, string code, string accountCode, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertAccountProperties: Upsert account properties

Update or insert one or more properties onto a single account. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'Account'.                Upserting a property that exists for an account, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var accountCode = "accountCode_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
AccountProperties result = apiInstance.UpsertAccountProperties(scope, code, accountCode, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts to update or insert the properties onto. Together with the scope this uniquely identifies the Chart of Accounts. |
| **accountCode** | **string** | path | **required** | The unique ID of the account to create or update properties for. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the chart of account. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;Account/Manager/Id\&quot;. |

### Return type

[AccountProperties](AccountProperties.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted properties. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertAccountPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AccountProperties> response = apiInstance.UpsertAccountPropertiesWithHttpInfo(scope, code, accountCode, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertaccounts"></a>
## UpsertAccounts

> AccountsUpsertResponse UpsertAccounts(string scope, string code, List<Account> account)

[EXPERIMENTAL] UpsertAccounts: Upsert Accounts

Create or update accounts in the Chart of Accounts. An account will be updated  if it already exists and created if it does not.  The maximum number of accounts that this method can upsert per request is 2,000.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var account = new List<Account>(); // List<Account>
AccountsUpsertResponse result = apiInstance.UpsertAccounts(scope, code, account);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts. Together with the scope this uniquely identifies              the Chart of Accounts. |
| **account** | [List&lt;Account&gt;](Account.md) | body | **required** | A list of accounts to be created or updated. |

### Return type

[AccountsUpsertResponse](AccountsUpsertResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The newly upserted Accounts. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertAccountsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<AccountsUpsertResponse> response = apiInstance.UpsertAccountsWithHttpInfo(scope, code, account);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertchartofaccountsproperties"></a>
## UpsertChartOfAccountsProperties

> ChartOfAccountsProperties UpsertChartOfAccountsProperties(string scope, string code, Dictionary<string, Property>? requestBody = null)

[EXPERIMENTAL] UpsertChartOfAccountsProperties: Upsert Chart of Accounts properties

Update or insert one or more properties onto a single Chart of Accounts. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'ChartOfAccounts'.                Upserting a property that exists for a Chart of Accounts, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ChartOfAccountsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
ChartOfAccountsProperties result = apiInstance.UpsertChartOfAccountsProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Chart of Accounts to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the Chart of Accounts to update or insert the properties onto. Together with the scope this uniquely identifies the Chart of Accounts. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the chart of account. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;ChartOfAccounts/Manager/Id\&quot;. |

### Return type

[ChartOfAccountsProperties](ChartOfAccountsProperties.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted properties. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertChartOfAccountsPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ChartOfAccountsProperties> response = apiInstance.UpsertChartOfAccountsPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

