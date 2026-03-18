# Finbourne.Sdk.Lusid.Api.PortfolioGroupsApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AddPortfolioToGroup**](#addportfoliotogroup) | **POST** `/api/api/portfoliogroups/{scope}/{code}/portfolios` | [EARLY ACCESS] AddPortfolioToGroup: Add portfolio to group |
| [**AddSubGroupToGroup**](#addsubgrouptogroup) | **POST** `/api/api/portfoliogroups/{scope}/{code}/subgroups` | [EARLY ACCESS] AddSubGroupToGroup: Add sub group to group |
| [**BuildTransactionsForPortfolioGroup**](#buildtransactionsforportfoliogroup) | **POST** `/api/api/portfoliogroups/{scope}/{code}/transactions/$build` | BuildTransactionsForPortfolioGroup: Build transactions for transaction portfolios in a portfolio group |
| [**CreatePortfolioGroup**](#createportfoliogroup) | **POST** `/api/api/portfoliogroups/{scope}` | CreatePortfolioGroup: Create portfolio group |
| [**DeleteGroupProperties**](#deletegroupproperties) | **POST** `/api/api/portfoliogroups/{scope}/{code}/properties/$delete` | [EARLY ACCESS] DeleteGroupProperties: Delete group properties |
| [**DeleteKeyFromPortfolioGroupAccessMetadata**](#deletekeyfromportfoliogroupaccessmetadata) | **DELETE** `/api/api/portfoliogroups/{scope}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] DeleteKeyFromPortfolioGroupAccessMetadata: Delete a Portfolio Group Access Metadata entry |
| [**DeletePortfolioFromGroup**](#deleteportfoliofromgroup) | **DELETE** `/api/api/portfoliogroups/{scope}/{code}/portfolios/{portfolioScope}/{portfolioCode}` | [EARLY ACCESS] DeletePortfolioFromGroup: Delete portfolio from group |
| [**DeletePortfolioGroup**](#deleteportfoliogroup) | **DELETE** `/api/api/portfoliogroups/{scope}/{code}` | [EARLY ACCESS] DeletePortfolioGroup: Delete portfolio group |
| [**DeleteSubGroupFromGroup**](#deletesubgroupfromgroup) | **DELETE** `/api/api/portfoliogroups/{scope}/{code}/subgroups/{subgroupScope}/{subgroupCode}` | [EARLY ACCESS] DeleteSubGroupFromGroup: Delete sub group from group |
| [**GetA2BDataForPortfolioGroup**](#geta2bdataforportfoliogroup) | **GET** `/api/api/portfoliogroups/{scope}/{code}/a2b` | [EARLY ACCESS] GetA2BDataForPortfolioGroup: Get A2B data for a Portfolio Group |
| [**GetGroupProperties**](#getgroupproperties) | **GET** `/api/api/portfoliogroups/{scope}/{code}/properties` | [EARLY ACCESS] GetGroupProperties: Get group properties |
| [**GetHoldingsForPortfolioGroup**](#getholdingsforportfoliogroup) | **GET** `/api/api/portfoliogroups/{scope}/{code}/holdings` | GetHoldingsForPortfolioGroup: Get holdings for transaction portfolios in portfolio group |
| [**GetPortfolioGroup**](#getportfoliogroup) | **GET** `/api/api/portfoliogroups/{scope}/{code}` | GetPortfolioGroup: Get portfolio group |
| [**GetPortfolioGroupAccessMetadataByKey**](#getportfoliogroupaccessmetadatabykey) | **GET** `/api/api/portfoliogroups/{scope}/{code}/metadata/{metadataKey}` | [EARLY ACCESS] GetPortfolioGroupAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Portfolio Group |
| [**GetPortfolioGroupCommands**](#getportfoliogroupcommands) | **GET** `/api/api/portfoliogroups/{scope}/{code}/commands` | GetPortfolioGroupCommands: Get portfolio group commands |
| [**GetPortfolioGroupExpansion**](#getportfoliogroupexpansion) | **GET** `/api/api/portfoliogroups/{scope}/{code}/expansion` | [EARLY ACCESS] GetPortfolioGroupExpansion: Get portfolio group expansion |
| [**GetPortfolioGroupMetadata**](#getportfoliogroupmetadata) | **GET** `/api/api/portfoliogroups/{scope}/{code}/metadata` | [EARLY ACCESS] GetPortfolioGroupMetadata: Get Access Metadata rules for Portfolio Group |
| [**GetPortfolioGroupPropertyTimeSeries**](#getportfoliogrouppropertytimeseries) | **GET** `/api/api/portfoliogroups/{scope}/{code}/properties/time-series` | [EARLY ACCESS] GetPortfolioGroupPropertyTimeSeries: Get the time series of a portfolio group property |
| [**GetPortfolioGroupRelations**](#getportfoliogrouprelations) | **GET** `/api/api/portfoliogroups/{scope}/{code}/relations` | [EXPERIMENTAL] GetPortfolioGroupRelations: Get Relations for Portfolio Group |
| [**GetPortfolioGroupRelationships**](#getportfoliogrouprelationships) | **GET** `/api/api/portfoliogroups/{scope}/{code}/relationships` | [EARLY ACCESS] GetPortfolioGroupRelationships: Get Relationships for Portfolio Group |
| [**GetTransactionsForPortfolioGroup**](#gettransactionsforportfoliogroup) | **GET** `/api/api/portfoliogroups/{scope}/{code}/transactions` | GetTransactionsForPortfolioGroup: Get transactions for transaction portfolios in a portfolio group |
| [**ListPortfolioGroups**](#listportfoliogroups) | **GET** `/api/api/portfoliogroups/{scope}` | ListPortfolioGroups: List portfolio groups |
| [**PatchPortfolioGroupAccessMetadata**](#patchportfoliogroupaccessmetadata) | **PATCH** `/api/api/portfoliogroups/{scope}/{code}/metadata` | [EARLY ACCESS] PatchPortfolioGroupAccessMetadata: Patch Access Metadata rules for a Portfolio Group. |
| [**UpdatePortfolioGroup**](#updateportfoliogroup) | **PUT** `/api/api/portfoliogroups/{scope}/{code}` | [EARLY ACCESS] UpdatePortfolioGroup: Update portfolio group |
| [**UpsertGroupProperties**](#upsertgroupproperties) | **POST** `/api/api/portfoliogroups/{scope}/{code}/properties/$upsert` | [EARLY ACCESS] UpsertGroupProperties: Upsert group properties |
| [**UpsertPortfolioGroupAccessMetadata**](#upsertportfoliogroupaccessmetadata) | **PUT** `/api/api/portfoliogroups/{scope}/{code}/metadata/{metadataKey}` | UpsertPortfolioGroupAccessMetadata: Upsert a Portfolio Group Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID. |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PortfolioGroupsApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
```

---

<a id="addportfoliotogroup"></a>
## AddPortfolioToGroup

> PortfolioGroup AddPortfolioToGroup(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, ResourceId? resourceId = null)

[EARLY ACCESS] AddPortfolioToGroup: Add portfolio to group

Add a single portfolio to a portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var resourceId = new ResourceId?(); // ResourceId? (optional)
PortfolioGroup result = apiInstance.AddPortfolioToGroup(scope, code, effectiveAt, resourceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to add a portfolio to. |
| **code** | **string** | path | **required** | The code of the portfolio group to add a portfolio to. Together with the scope this uniquely identifies the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the portfolio will be added to the group. |
| **resourceId** | [ResourceId?](ResourceId?.md) | body | optional | The resource identifier of the portfolio to add to the portfolio group. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The portfolio group containing the newly added portfolio |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddPortfolioToGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.AddPortfolioToGroupWithHttpInfo(scope, code, effectiveAt, resourceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="addsubgrouptogroup"></a>
## AddSubGroupToGroup

> PortfolioGroup AddSubGroupToGroup(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, ResourceId? resourceId = null)

[EARLY ACCESS] AddSubGroupToGroup: Add sub group to group

Add a portfolio group to a portfolio group as a sub group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var resourceId = new ResourceId?(); // ResourceId? (optional)
PortfolioGroup result = apiInstance.AddSubGroupToGroup(scope, code, effectiveAt, resourceId);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to add a portfolio group to. |
| **code** | **string** | path | **required** | The code of the portfolio group to add a portfolio group to. Together with the scope this uniquely identifies the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the sub group will be added to the group. |
| **resourceId** | [ResourceId?](ResourceId?.md) | body | optional | The resource identifier of the portfolio group to add to the portfolio group as a sub group. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The portfolio group containing the newly added portfolio group as a sub group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AddSubGroupToGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.AddSubGroupToGroupWithHttpInfo(scope, code, effectiveAt, resourceId);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="buildtransactionsforportfoliogroup"></a>
## BuildTransactionsForPortfolioGroup

> VersionedResourceListOfOutputTransaction BuildTransactionsForPortfolioGroup(string scope, string code, TransactionQueryParameters transactionQueryParameters, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, int? limit = null, string? page = null, string? dataModelScope = null, string? dataModelCode = null, string? membershipType = null)

BuildTransactionsForPortfolioGroup: Build transactions for transaction portfolios in a portfolio group

Build transactions for transaction portfolios in a portfolio group over a given interval of effective time.                When the specified portfolio in a portfolio group is a derived transaction portfolio, the returned set of transactions is the  union set of all transactions of the parent (and any grandparents etc.) and the specified derived transaction portfolio itself.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var transactionQueryParameters = new TransactionQueryParameters(); // TransactionQueryParameters
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var membershipType = "membershipType_example";  // string? (optional)
VersionedResourceListOfOutputTransaction result = apiInstance.BuildTransactionsForPortfolioGroup(scope, code, transactionQueryParameters, asAt, filter, propertyKeys, limit, page, dataModelScope, dataModelCode, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group. |
| **code** | **string** | path | **required** | The code of the portfolio group. Together with the scope this uniquely identifies               the portfolio group. |
| **transactionQueryParameters** | [TransactionQueryParameters](TransactionQueryParameters.md) | body | **required** | The query queryParameters which control how the output transactions are built. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to build the transactions. Defaults to return the latest               version of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to filter on the Transaction Type, use \&quot;type eq &#39;Buy&#39;\&quot;               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; or \&quot;Transaction\&quot; domain to decorate onto               the transactions. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or               \&quot;Transaction/strategy/quantsignal\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to BuildTransactions. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[VersionedResourceListOfOutputTransaction](VersionedResourceListOfOutputTransaction.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested transactions from transaction portfolios in the specified portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the BuildTransactionsForPortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfOutputTransaction> response = apiInstance.BuildTransactionsForPortfolioGroupWithHttpInfo(scope, code, transactionQueryParameters, asAt, filter, propertyKeys, limit, page, dataModelScope, dataModelCode, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="createportfoliogroup"></a>
## CreatePortfolioGroup

> PortfolioGroup CreatePortfolioGroup(string scope, CreatePortfolioGroupRequest? createPortfolioGroupRequest = null)

CreatePortfolioGroup: Create portfolio group

Create a portfolio group in a specific scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var createPortfolioGroupRequest = new CreatePortfolioGroupRequest?(); // CreatePortfolioGroupRequest? (optional)
PortfolioGroup result = apiInstance.CreatePortfolioGroup(scope, createPortfolioGroupRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope that the portfolio group will be created in. |
| **createPortfolioGroupRequest** | [CreatePortfolioGroupRequest?](CreatePortfolioGroupRequest?.md) | body | optional | The definition and details of the portfolio group. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The newly created portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the CreatePortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.CreatePortfolioGroupWithHttpInfo(scope, createPortfolioGroupRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletegroupproperties"></a>
## DeleteGroupProperties

> DeletedEntityResponse DeleteGroupProperties(string scope, string code, List<string> requestBody, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeleteGroupProperties: Delete group properties

Delete one or more properties from a single portfolio group. If the properties are time variant then an effective date time from which the properties  will be deleted must be specified. If the properties are perpetual then it is invalid to specify an effective date time for deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new List<string>(); // List<string>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
DeletedEntityResponse result = apiInstance.DeleteGroupProperties(scope, code, requestBody, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group to delete properties from. |
| **code** | **string** | path | **required** | The code of the group to delete properties from. Together with the scope this uniquely identifies the group. |
| **requestBody** | [List&lt;string&gt;](string.md) | body | **required** | The property keys of the properties to delete. These take the format              {domain}/{scope}/{code} e.g. \&quot;PortfolioGroup/Manager/Id\&quot;. Each property must be from the \&quot;PortfolioGroup\&quot; domain. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to delete time-variant properties from.              The property must exist at the specified &#39;effectiveAt&#39; datetime. If the &#39;effectiveAt&#39; is not provided or is              before the time-variant property exists then a failure is returned. Do not specify this parameter if any of              the properties to delete are perpetual. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the properties were deleted from the specified group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteGroupPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteGroupPropertiesWithHttpInfo(scope, code, requestBody, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletekeyfromportfoliogroupaccessmetadata"></a>
## DeleteKeyFromPortfolioGroupAccessMetadata

> DeletedEntityResponse DeleteKeyFromPortfolioGroupAccessMetadata(string scope, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] DeleteKeyFromPortfolioGroupAccessMetadata: Delete a Portfolio Group Access Metadata entry

Deletes the Portfolio Group Access Metadata entry that exactly matches the provided identifier parts.    It is important to always check to verify success (or failure).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
DeletedEntityResponse result = apiInstance.DeleteKeyFromPortfolioGroupAccessMetadata(scope, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Group |
| **code** | **string** | path | **required** | The Portfolio Group code |
| **metadataKey** | **string** | path | **required** | Key of the Access Metadata entry to delete |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date to delete at, if this is not supplied, it will delete all data found |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the delete is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The has been deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteKeyFromPortfolioGroupAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeleteKeyFromPortfolioGroupAccessMetadataWithHttpInfo(scope, code, metadataKey, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteportfoliofromgroup"></a>
## DeletePortfolioFromGroup

> PortfolioGroup DeletePortfolioFromGroup(string scope, string code, string portfolioScope, string portfolioCode, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeletePortfolioFromGroup: Delete portfolio from group

Remove a single portfolio from a portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var portfolioScope = "portfolioScope_example";  // string
var portfolioCode = "portfolioCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
PortfolioGroup result = apiInstance.DeletePortfolioFromGroup(scope, code, portfolioScope, portfolioCode, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to remove the portfolio from. |
| **code** | **string** | path | **required** | The code of the portfolio group to remove the portfolio from. Together with the scope this uniquely identifies the portfolio group. |
| **portfolioScope** | **string** | path | **required** | The scope of the portfolio being removed from the portfolio group. |
| **portfolioCode** | **string** | path | **required** | The code of the portfolio being removed from the portfolio group. Together with the scope this uniquely identifies the portfolio to remove. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the portfolio will be removed from the portfolio group. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The portfolio group with the portfolio removed from the group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePortfolioFromGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.DeletePortfolioFromGroupWithHttpInfo(scope, code, portfolioScope, portfolioCode, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deleteportfoliogroup"></a>
## DeletePortfolioGroup

> DeletedEntityResponse DeletePortfolioGroup(string scope, string code)

[EARLY ACCESS] DeletePortfolioGroup: Delete portfolio group

Delete a single portfolio group. A portfolio group can be deleted while it still contains portfolios or sub groups.  In this case any portfolios or sub groups contained in this group will not be deleted, however they will no longer be grouped together by this portfolio group.  The deletion will be valid from the portfolio group's creation datetime, ie. the portfolio group will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeletePortfolioGroup(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to delete. |
| **code** | **string** | path | **required** | The code of the portfolio group to delete. Together with the scope this uniquely identifies the portfolio group to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The datetime that the portfolio group was deleted |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePortfolioGroupWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="deletesubgroupfromgroup"></a>
## DeleteSubGroupFromGroup

> PortfolioGroup DeleteSubGroupFromGroup(string scope, string code, string subgroupScope, string subgroupCode, DateTimeOrCutLabel? effectiveAt = null)

[EARLY ACCESS] DeleteSubGroupFromGroup: Delete sub group from group

Remove a single portfolio group (sub group) from a portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var subgroupScope = "subgroupScope_example";  // string
var subgroupCode = "subgroupCode_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
PortfolioGroup result = apiInstance.DeleteSubGroupFromGroup(scope, code, subgroupScope, subgroupCode, effectiveAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to remove the sub group from. |
| **code** | **string** | path | **required** | The code of the portfolio group to remove the sub group from. Together with the scope this uniquely identifies the portfolio group. |
| **subgroupScope** | **string** | path | **required** | The scope of the sub group to remove from the portfolio group. |
| **subgroupCode** | **string** | path | **required** | The code of the sub group to remove from the portfolio group. Together with the scope this uniquely identifies the sub group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label from which the sub group will be removed from the portfolio group. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The portfolio group with the sub group removed from the group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeleteSubGroupFromGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.DeleteSubGroupFromGroupWithHttpInfo(scope, code, subgroupScope, subgroupCode, effectiveAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="geta2bdataforportfoliogroup"></a>
## GetA2BDataForPortfolioGroup

> VersionedResourceListOfA2BDataRecord GetA2BDataForPortfolioGroup(string scope, string code, DateTimeOrCutLabel fromEffectiveAt, DateTimeOrCutLabel toEffectiveAt, DateTimeOffset? asAt = null, string? recipeIdScope = null, string? recipeIdCode = null, List<string>? propertyKeys = null, string? filter = null)

[EARLY ACCESS] GetA2BDataForPortfolioGroup: Get A2B data for a Portfolio Group

Get an A2B report for all Transaction Portfolios within the given portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromEffectiveAt = "fromEffectiveAt_example";  // DateTimeOrCutLabel
var toEffectiveAt = "toEffectiveAt_example";  // DateTimeOrCutLabel
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var recipeIdScope = "recipeIdScope_example";  // string? (optional)
var recipeIdCode = "recipeIdCode_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var filter = "filter_example";  // string? (optional)
VersionedResourceListOfA2BDataRecord result = apiInstance.GetA2BDataForPortfolioGroup(scope, code, fromEffectiveAt, toEffectiveAt, asAt, recipeIdScope, recipeIdCode, propertyKeys, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group to retrieve the A2B report for. |
| **code** | **string** | path | **required** | The code of the group to retrieve the A2B report for. Together with the scope this              uniquely identifies the portfolio group. |
| **fromEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The lower bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no lower bound if this is not specified. |
| **toEffectiveAt** | **DateTimeOrCutLabel** | query | **required** | The upper bound effective datetime or cut label (inclusive) from which to retrieve the data.              There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio. Defaults to return the latest version              of each transaction if not specified. |
| **recipeIdScope** | **string?** | query | optional | The scope of the given recipeId |
| **recipeIdCode** | **string?** | query | optional | The code of the given recipeId |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot; domain to decorate onto              the results. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot;. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[VersionedResourceListOfA2BDataRecord](VersionedResourceListOfA2BDataRecord.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested group A2B data |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetA2BDataForPortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfA2BDataRecord> response = apiInstance.GetA2BDataForPortfolioGroupWithHttpInfo(scope, code, fromEffectiveAt, toEffectiveAt, asAt, recipeIdScope, recipeIdCode, propertyKeys, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getgroupproperties"></a>
## GetGroupProperties

> PortfolioGroupProperties GetGroupProperties(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetGroupProperties: Get group properties

List all the properties of a single portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
PortfolioGroupProperties result = apiInstance.GetGroupProperties(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group to list the properties for. |
| **code** | **string** | path | **required** | The code of the group to list the properties for. Together with the scope this uniquely identifies the group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective date time or cut label at which to list the group&#39;s properties. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt date time at which to list the group&#39;s properties. Defaults to return the latest version of each property if not specified. |

### Return type

[PortfolioGroupProperties](PortfolioGroupProperties.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The properties of the specified group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetGroupPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroupProperties> response = apiInstance.GetGroupPropertiesWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getholdingsforportfoliogroup"></a>
## GetHoldingsForPortfolioGroup

> VersionedResourceListOfPortfolioHolding GetHoldingsForPortfolioGroup(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, bool? byTaxlots = null, int? includeSettlementEventsAfterDays = null)

GetHoldingsForPortfolioGroup: Get holdings for transaction portfolios in portfolio group

Get the holdings of transaction portfolios in specified portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var byTaxlots = true;  // bool? (optional)
var includeSettlementEventsAfterDays = 56;  // int? (optional)
VersionedResourceListOfPortfolioHolding result = apiInstance.GetHoldingsForPortfolioGroup(scope, code, effectiveAt, asAt, filter, propertyKeys, byTaxlots, includeSettlementEventsAfterDays);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group. |
| **code** | **string** | path | **required** | The code of the portfolio group. Together with the scope this uniquely identifies              the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the holdings of transaction              portfolios in the portfolio group. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the holdings of transaction portfolios in the portfolio group. Defaults              to return the latest version of the holdings if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot;, \&quot;Holding\&quot; or \&quot;Portfolio\&quot; domain to decorate onto              the holdings. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or \&quot;Holding/system/Cost\&quot;. |
| **byTaxlots** | **bool?** | query | optional | Whether or not to expand the holdings to return the underlying tax-lots. Defaults to              False. |
| **includeSettlementEventsAfterDays** | **int?** | query | optional | Number of days ahead to bring back settlements from, in relation to the specified effectiveAt |

### Return type

[VersionedResourceListOfPortfolioHolding](VersionedResourceListOfPortfolioHolding.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The holdings of transaction portfolios in a specific version of portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetHoldingsForPortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfPortfolioHolding> response = apiInstance.GetHoldingsForPortfolioGroupWithHttpInfo(scope, code, effectiveAt, asAt, filter, propertyKeys, byTaxlots, includeSettlementEventsAfterDays);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogroup"></a>
## GetPortfolioGroup

> PortfolioGroup GetPortfolioGroup(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? relatedEntityPropertyKeys = null, List<string>? relationshipDefinitionIds = null)

GetPortfolioGroup: Get portfolio group

Retrieve the definition of a single portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var relatedEntityPropertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
PortfolioGroup result = apiInstance.GetPortfolioGroup(scope, code, effectiveAt, asAt, relatedEntityPropertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to retrieve the definition for. |
| **code** | **string** | path | **required** | The code of the portfolio group to retrieve the definition for. Together with the scope              this uniquely identifies the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve the portfolio group definition. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the portfolio group definition. Defaults to return              the latest version of the portfolio group definition if not specified. |
| **relatedEntityPropertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from any domain that supports relationships              to decorate onto related entities. These must take the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the portfolio group in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested portfolio group definition |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.GetPortfolioGroupWithHttpInfo(scope, code, effectiveAt, asAt, relatedEntityPropertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogroupaccessmetadatabykey"></a>
## GetPortfolioGroupAccessMetadataByKey

> List&lt;AccessMetadataValue&gt; GetPortfolioGroupAccessMetadataByKey(string scope, string code, string metadataKey, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetPortfolioGroupAccessMetadataByKey: Get an entry identified by a metadataKey in the Access Metadata of a Portfolio Group

Get a specific Portfolio Group access metadata by specifying the corresponding identifier parts                No matching will be performed through this endpoint. To retrieve a rule, it is necessary to specify, exactly, the identifier of the rule

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
List<AccessMetadataValue> result = apiInstance.GetPortfolioGroupAccessMetadataByKey(scope, code, metadataKey, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Group |
| **code** | **string** | path | **required** | The Portfolio Group code |
| **metadataKey** | **string** | path | **required** | Key of the metadata entry to retrieve |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the access metadata |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the access metadata |

### Return type

[List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully retrieved Portfolio group access metadata filtered by metadataKey or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupAccessMetadataByKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<List<AccessMetadataValue>> response = apiInstance.GetPortfolioGroupAccessMetadataByKeyWithHttpInfo(scope, code, metadataKey, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogroupcommands"></a>
## GetPortfolioGroupCommands

> ResourceListOfProcessedCommand GetPortfolioGroupCommands(string scope, string code, DateTimeOffset? fromAsAt = null, DateTimeOffset? toAsAt = null, string? filter = null)

GetPortfolioGroupCommands: Get portfolio group commands

Gets all the commands that modified a single portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromAsAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var toAsAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
ResourceListOfProcessedCommand result = apiInstance.GetPortfolioGroupCommands(scope, code, fromAsAt, toAsAt, filter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to retrieve the commands for. |
| **code** | **string** | path | **required** | The code of the portfolio group to retrieve the commands for. Together with the scope this uniquely identifies the portfolio group. |
| **fromAsAt** | **DateTimeOffset?** | query | optional | The lower bound asAt datetime (inclusive) from which to retrieve commands. There is no lower bound if this is not specified. |
| **toAsAt** | **DateTimeOffset?** | query | optional | The upper bound asAt datetime (inclusive) from which to retrieve commands. There is no upper bound if this is not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to filter on the User ID, use \&quot;userId.id eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |

### Return type

[ResourceListOfProcessedCommand](ResourceListOfProcessedCommand.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The commands that modified the specified portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupCommandsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfProcessedCommand> response = apiInstance.GetPortfolioGroupCommandsWithHttpInfo(scope, code, fromAsAt, toAsAt, filter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogroupexpansion"></a>
## GetPortfolioGroupExpansion

> ExpandedGroup GetPortfolioGroupExpansion(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, List<string>? propertyFilter = null)

[EARLY ACCESS] GetPortfolioGroupExpansion: Get portfolio group expansion

List all the portfolios in a group, including all portfolios within sub groups in the group. Each portfolio will be decorated with all of its properties unless a property filter is specified.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyFilter = new List<string>?(); // List<string>? (optional)
ExpandedGroup result = apiInstance.GetPortfolioGroupExpansion(scope, code, effectiveAt, asAt, propertyFilter);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to expand. |
| **code** | **string** | path | **required** | The code of the portfolio group to expand. Together with the scope this uniquely identifies the portfolio              group to expand. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to expand the portfolio group. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to expand the portfolio group. Defaults to return the latest version of each portfolio in the group if not specified. |
| **propertyFilter** | [List&lt;string&gt;?](string.md) | query | optional | The restricted list of property keys from the \&quot;Portfolio\&quot; domain which will be decorated onto each portfolio. These take the format {domain}/{scope}/{code} e.g. \&quot;Portfolio/Manager/Id\&quot;. |

### Return type

[ExpandedGroup](ExpandedGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The expanded portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupExpansionWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ExpandedGroup> response = apiInstance.GetPortfolioGroupExpansionWithHttpInfo(scope, code, effectiveAt, asAt, propertyFilter);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogroupmetadata"></a>
## GetPortfolioGroupMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; GetPortfolioGroupMetadata(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null)

[EARLY ACCESS] GetPortfolioGroupMetadata: Get Access Metadata rules for Portfolio Group

Pass the scope and Portfolio Group code parameters to retrieve the associated Access Metadata

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.GetPortfolioGroupMetadata(scope, code, effectiveAt, asAt);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Group |
| **code** | **string** | path | **required** | The Portfolio Group code |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effectiveAt datetime at which to retrieve the Access Metadata |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the Access Metadata |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The access metadata for the portfolio group or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.GetPortfolioGroupMetadataWithHttpInfo(scope, code, effectiveAt, asAt);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogrouppropertytimeseries"></a>
## GetPortfolioGroupPropertyTimeSeries

> ResourceListOfPropertyInterval GetPortfolioGroupPropertyTimeSeries(string scope, string code, string propertyKey, string? portfolioGroupEffectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, string? page = null, int? limit = null)

[EARLY ACCESS] GetPortfolioGroupPropertyTimeSeries: Get the time series of a portfolio group property

List the complete time series of a portfolio group property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var propertyKey = "propertyKey_example";  // string
var portfolioGroupEffectiveAt = "portfolioGroupEffectiveAt_example";  // string? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
ResourceListOfPropertyInterval result = apiInstance.GetPortfolioGroupPropertyTimeSeries(scope, code, propertyKey, portfolioGroupEffectiveAt, asAt, filter, page, limit);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group. |
| **code** | **string** | path | **required** | The code of the group. Together with the scope this uniquely identifies              the portfolio group. |
| **propertyKey** | **string** | query | **required** | The property key of the property that will have its history shown. These must be in the format {domain}/{scope}/{code} e.g. \&quot;PortfolioGroup/Manager/Id\&quot;.              Each property must be from the \&quot;PortfolioGroup\&quot; domain. |
| **portfolioGroupEffectiveAt** | **string?** | query | optional | The effective datetime used to resolve the portfolio group. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the portfolio group&#39;s property history. Defaults to return the current datetime if not supplied. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing properties from a previous call to get property time series.              This value is returned from the previous call. If a pagination token is provided the filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |

### Return type

[ResourceListOfPropertyInterval](ResourceListOfPropertyInterval.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The time series of the property |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupPropertyTimeSeriesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPropertyInterval> response = apiInstance.GetPortfolioGroupPropertyTimeSeriesWithHttpInfo(scope, code, propertyKey, portfolioGroupEffectiveAt, asAt, filter, page, limit);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogrouprelations"></a>
## GetPortfolioGroupRelations

> ResourceListOfRelation GetPortfolioGroupRelations(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EXPERIMENTAL] GetPortfolioGroupRelations: Get Relations for Portfolio Group

Get relations for the specified Portfolio Group

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelation result = apiInstance.GetPortfolioGroupRelations(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group. |
| **code** | **string** | path | **required** | The code of the portfolio group. Together with the scope this uniquely identifies              the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve relations. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relations. Defaults to return the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the relations. Users should provide null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifiers types (as property keys) used for referencing Persons or Legal Entities. These take the format              {domain}/{scope}/{code} e.g. \&quot;Person/CompanyDetails/Role\&quot;. They must be from the \&quot;Person\&quot; or \&quot;LegalEntity\&quot; domain.              Only identifier types stated will be used to look up relevant entities in relations. If not applicable, provide an empty array. |

### Return type

[ResourceListOfRelation](ResourceListOfRelation.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relations for the specific portfolio group. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupRelationsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelation> response = apiInstance.GetPortfolioGroupRelationsWithHttpInfo(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getportfoliogrouprelationships"></a>
## GetPortfolioGroupRelationships

> ResourceListOfRelationship GetPortfolioGroupRelationships(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? identifierTypes = null)

[EARLY ACCESS] GetPortfolioGroupRelationships: Get Relationships for Portfolio Group

Get relationships for the specified Portfolio Group

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var identifierTypes = new List<string>?(); // List<string>? (optional)
ResourceListOfRelationship result = apiInstance.GetPortfolioGroupRelationships(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group. |
| **code** | **string** | path | **required** | The code of the portfolio group. Together with the scope this uniquely identifies              the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to retrieve relationship. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve relationships. Defaults to return the latest LUSID AsAt time if not specified. |
| **filter** | **string?** | query | optional | Expression to filter relationships. Users should provide null or empty string for this field until further notice. |
| **identifierTypes** | [List&lt;string&gt;?](string.md) | query | optional | Identifier types (as property keys) used for referencing Persons or Legal Entities.              These can be specified from the &#39;Person&#39; or &#39;LegalEntity&#39; domains and have the format {domain}/{scope}/{code}, for example              &#39;Person/CompanyDetails/Role&#39;. An Empty array may be used to return all related Entities. |

### Return type

[ResourceListOfRelationship](ResourceListOfRelationship.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The relationships for the specific portfolio group. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPortfolioGroupRelationshipsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfRelationship> response = apiInstance.GetPortfolioGroupRelationshipsWithHttpInfo(scope, code, effectiveAt, asAt, filter, identifierTypes);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="gettransactionsforportfoliogroup"></a>
## GetTransactionsForPortfolioGroup

> VersionedResourceListOfTransaction GetTransactionsForPortfolioGroup(string scope, string code, DateTimeOrCutLabel? fromTransactionDate = null, DateTimeOrCutLabel? toTransactionDate = null, DateTimeOffset? asAt = null, string? filter = null, List<string>? propertyKeys = null, int? limit = null, string? page = null, bool? showCancelledTransactions = null, List<string>? sortBy = null, string? dataModelScope = null, string? dataModelCode = null, string? membershipType = null)

GetTransactionsForPortfolioGroup: Get transactions for transaction portfolios in a portfolio group

Get transactions for transaction portfolios in a portfolio group over a given interval of effective time.                When the specified portfolio in a portfolio group is a derived transaction portfolio, the returned set of transactions is the  union set of all transactions of the parent (and any grandparents etc.) and the specified derived transaction portfolio itself.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var fromTransactionDate = "fromTransactionDate_example";  // DateTimeOrCutLabel? (optional)
var toTransactionDate = "toTransactionDate_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var page = "page_example";  // string? (optional)
var showCancelledTransactions = true;  // bool? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var dataModelScope = "dataModelScope_example";  // string? (optional)
var dataModelCode = "dataModelCode_example";  // string? (optional)
var membershipType = "membershipType_example";  // string? (optional)
VersionedResourceListOfTransaction result = apiInstance.GetTransactionsForPortfolioGroup(scope, code, fromTransactionDate, toTransactionDate, asAt, filter, propertyKeys, limit, page, showCancelledTransactions, sortBy, dataModelScope, dataModelCode, membershipType);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group. |
| **code** | **string** | path | **required** | The code of the portfolio group. Together with the scope this uniquely identifies               the portfolio group. |
| **fromTransactionDate** | **DateTimeOrCutLabel?** | query | optional | The lower bound effective datetime or cut label (inclusive) from which to retrieve the transactions.               There is no lower bound if this is not specified. |
| **toTransactionDate** | **DateTimeOrCutLabel?** | query | optional | The upper bound effective datetime or cut label (inclusive) from which to retrieve transactions.               There is no upper bound if this is not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the transactions. Defaults to return the latest version               of each transaction if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.               For example, to filter on the Transaction Type, use \&quot;type eq &#39;Buy&#39;\&quot;               Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Instrument\&quot;, \&quot;Transaction\&quot;, \&quot;LegalEntity\&quot; or \&quot;CustodianAccount\&quot; domain to decorate onto               the transactions. These take the format {domain}/{scope}/{code} e.g. \&quot;Instrument/system/Name\&quot; or               \&quot;Transaction/strategy/quantsignal\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to 100 if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing transactions from a previous call to GetTransactions. |
| **showCancelledTransactions** | **bool?** | query | optional | Option to specify whether or not to include cancelled transactions,               including previous versions of transactions which have since been amended.               Defaults to False if not specified. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **dataModelScope** | **string?** | query | optional | The optional scope of a Custom Data Model to use |
| **dataModelCode** | **string?** | query | optional | The optional code of a Custom Data Model to use |
| **membershipType** | **string?** | query | optional | The membership types of the specified Custom Data Model to return. Allowable values are Member, Candidate and All. Defaults to Member. |

### Return type

[VersionedResourceListOfTransaction](VersionedResourceListOfTransaction.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested transactions from transaction portfolios in the specified portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetTransactionsForPortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<VersionedResourceListOfTransaction> response = apiInstance.GetTransactionsForPortfolioGroupWithHttpInfo(scope, code, fromTransactionDate, toTransactionDate, asAt, filter, propertyKeys, limit, page, showCancelledTransactions, sortBy, dataModelScope, dataModelCode, membershipType);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listportfoliogroups"></a>
## ListPortfolioGroups

> PagedResourceListOfPortfolioGroup ListPortfolioGroups(string scope, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? asAt = null, string? page = null, int? limit = null, string? filter = null, List<string>? sortBy = null, List<string>? relatedEntityPropertyKeys = null, List<string>? relationshipDefinitionIds = null)

ListPortfolioGroups: List portfolio groups

List all the portfolio groups in a single scope.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var relatedEntityPropertyKeys = new List<string>?(); // List<string>? (optional)
var relationshipDefinitionIds = new List<string>?(); // List<string>? (optional)
PagedResourceListOfPortfolioGroup result = apiInstance.ListPortfolioGroups(scope, effectiveAt, asAt, page, limit, filter, sortBy, relatedEntityPropertyKeys, relationshipDefinitionIds);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to list the portfolio groups in. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to list the portfolio groups. Defaults to the current LUSID system datetime if not specified. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to list the portfolio groups. Defaults to return the latest version of each portfolio group if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing portfolio groups from a previous call to list portfolio groups. This  value is returned from the previous call. If a pagination token is provided the filter, effectiveAt, sortBy  and asAt fields must not have changed since the original request. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. Defaults to no limit if not specified. |
| **filter** | **string?** | query | optional | Expression to filter the result set.              For example, to filter on the Display Name, use \&quot;displayName eq &#39;string&#39;\&quot;              Read more about filtering results from LUSID here https://support.lusid.com/filtering-results-from-lusid. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot; |
| **relatedEntityPropertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from any domain that supports relationships              to decorate onto related entities. These must take the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. |
| **relationshipDefinitionIds** | [List&lt;string&gt;?](string.md) | query | optional | A list of relationship definitions that are used to decorate related entities              onto the portfolio groups in the response. These must take the form {relationshipDefinitionScope}/{relationshipDefinitionCode}. |

### Return type

[PagedResourceListOfPortfolioGroup](PagedResourceListOfPortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The portfolio groups in the specified scope |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPortfolioGroupsWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPortfolioGroup> response = apiInstance.ListPortfolioGroupsWithHttpInfo(scope, effectiveAt, asAt, page, limit, filter, sortBy, relatedEntityPropertyKeys, relationshipDefinitionIds);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="patchportfoliogroupaccessmetadata"></a>
## PatchPortfolioGroupAccessMetadata

> Dictionary&lt;string, List&lt;AccessMetadataValue&gt;&gt; PatchPortfolioGroupAccessMetadata(string scope, string code, List<AccessMetadataOperation> accessMetadataOperation, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

[EARLY ACCESS] PatchPortfolioGroupAccessMetadata: Patch Access Metadata rules for a Portfolio Group.

Patch Portfolio Group Access Metadata Rules in a single scope.  The behaviour is defined by the JSON Patch specification.                Currently only 'add' is a supported operation on the patch document.    Currently only valid metadata keys are supported paths on the patch document.                The response will return any affected Portfolio Group Access Metadata rules or a failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var accessMetadataOperation = new List<AccessMetadataOperation>(); // List<AccessMetadataOperation>
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
Dictionary<string, List<AccessMetadataValue>> result = apiInstance.PatchPortfolioGroupAccessMetadata(scope, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Group |
| **code** | **string** | path | **required** | The Portfolio Group code |
| **accessMetadataOperation** | [List&lt;AccessMetadataOperation&gt;](AccessMetadataOperation.md) | body | **required** | The Json patch document |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The date this rule will be effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

**Dictionary<string, List<AccessMetadataValue>>**

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully patched items. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the PatchPortfolioGroupAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Dictionary<string, List<AccessMetadataValue>>> response = apiInstance.PatchPortfolioGroupAccessMetadataWithHttpInfo(scope, code, accessMetadataOperation, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="updateportfoliogroup"></a>
## UpdatePortfolioGroup

> PortfolioGroup UpdatePortfolioGroup(string scope, string code, DateTimeOrCutLabel? effectiveAt = null, UpdatePortfolioGroupRequest? updatePortfolioGroupRequest = null)

[EARLY ACCESS] UpdatePortfolioGroup: Update portfolio group

Update the definition of a single portfolio group. Not all elements within a portfolio group definition are modifiable  due to the potential implications for data already stored against the portfolio group.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var updatePortfolioGroupRequest = new UpdatePortfolioGroupRequest?(); // UpdatePortfolioGroupRequest? (optional)
PortfolioGroup result = apiInstance.UpdatePortfolioGroup(scope, code, effectiveAt, updatePortfolioGroupRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the portfolio group to update the definition for. |
| **code** | **string** | path | **required** | The code of the portfolio group to update the definition for. Together with the scope this uniquely identifies the portfolio group. |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The effective datetime or cut label at which to update the definition. |
| **updatePortfolioGroupRequest** | [UpdatePortfolioGroupRequest?](UpdatePortfolioGroupRequest?.md) | body | optional | The updated portfolio group definition. |

### Return type

[PortfolioGroup](PortfolioGroup.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated definition of the portfolio group |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpdatePortfolioGroupWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroup> response = apiInstance.UpdatePortfolioGroupWithHttpInfo(scope, code, effectiveAt, updatePortfolioGroupRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertgroupproperties"></a>
## UpsertGroupProperties

> PortfolioGroupProperties UpsertGroupProperties(string scope, string code, Dictionary<string, Property>? requestBody = null)

[EARLY ACCESS] UpsertGroupProperties: Upsert group properties

Update or insert one or more properties onto a single group. A property will be updated if it  already exists and inserted if it does not. All properties must be of the domain 'PortfolioGroup'.                Upserting a property that exists for a group, with a null value, will delete the instance of the property for that group.                Properties have an <i>effectiveFrom</i> datetime for which the property is valid, and an <i>effectiveUntil</i>  datetime until which the property is valid. Not supplying an <i>effectiveUntil</i> datetime results in the property being  valid indefinitely, or until the next <i>effectiveFrom</i> datetime of the property.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var requestBody = new Dictionary<string, Property>?(); // Dictionary<string, Property>? (optional)
PortfolioGroupProperties result = apiInstance.UpsertGroupProperties(scope, code, requestBody);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the group to update or insert the properties onto. |
| **code** | **string** | path | **required** | The code of the group to update or insert the properties onto. Together with the scope this uniquely identifies the group. |
| **requestBody** | [Dictionary&lt;string, Property&gt;?](Property.md) | body | optional | The properties to be updated or inserted onto the group. Each property in               the request must be keyed by its unique property key. This has the format {domain}/{scope}/{code} e.g. \&quot;PortfolioGroup/Manager/Id\&quot;. |

### Return type

[PortfolioGroupProperties](PortfolioGroupProperties.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated or inserted properties |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertGroupPropertiesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PortfolioGroupProperties> response = apiInstance.UpsertGroupPropertiesWithHttpInfo(scope, code, requestBody);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertportfoliogroupaccessmetadata"></a>
## UpsertPortfolioGroupAccessMetadata

> ResourceListOfAccessMetadataValueOf UpsertPortfolioGroupAccessMetadata(string scope, string code, string metadataKey, UpsertPortfolioGroupAccessMetadataRequest upsertPortfolioGroupAccessMetadataRequest, DateTimeOrCutLabel? effectiveAt = null, DateTimeOffset? effectiveUntil = null)

UpsertPortfolioGroupAccessMetadata: Upsert a Portfolio Group Access Metadata entry associated with a specific metadataKey. This creates or updates the data in LUSID.

Update or insert one Portfolio Group Access Metadata Entry in a single scope. An item will be updated if it already exists  and inserted if it does not.                The response will return the successfully updated or inserted Portfolio Group Access Metadata rule or failure message if unsuccessful.                It is important to always check to verify success (or failure).                Multiple rules for a metadataKey can exist with different effective at dates, when resources are accessed the rule that is active for the current time will be fetched.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PortfolioGroupsApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var metadataKey = "metadataKey_example";  // string
var upsertPortfolioGroupAccessMetadataRequest = new UpsertPortfolioGroupAccessMetadataRequest(); // UpsertPortfolioGroupAccessMetadataRequest
var effectiveAt = "effectiveAt_example";  // DateTimeOrCutLabel? (optional)
var effectiveUntil = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
ResourceListOfAccessMetadataValueOf result = apiInstance.UpsertPortfolioGroupAccessMetadata(scope, code, metadataKey, upsertPortfolioGroupAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope of the Portfolio Group |
| **code** | **string** | path | **required** | The Portfolio Group code |
| **metadataKey** | **string** | path | **required** | Key of the access metadata entry to upsert |
| **upsertPortfolioGroupAccessMetadataRequest** | [UpsertPortfolioGroupAccessMetadataRequest](UpsertPortfolioGroupAccessMetadataRequest.md) | body | **required** | The Portfolio Group Access Metadata rule to upsert |
| **effectiveAt** | **DateTimeOrCutLabel?** | query | optional | The date this rule will be effective from |
| **effectiveUntil** | **DateTimeOffset?** | query | optional | The effective date until which the Access Metadata is valid. If not supplied this will be valid indefinitely, or until the next &#39;effectiveAt&#39; date of the Access Metadata |

### Return type

[ResourceListOfAccessMetadataValueOf](ResourceListOfAccessMetadataValueOf.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The successfully updated or inserted item or any failure. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPortfolioGroupAccessMetadataWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAccessMetadataValueOf> response = apiInstance.UpsertPortfolioGroupAccessMetadataWithHttpInfo(scope, code, metadataKey, upsertPortfolioGroupAccessMetadataRequest, effectiveAt, effectiveUntil);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

