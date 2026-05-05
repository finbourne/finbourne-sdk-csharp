# Finbourne.Sdk.Identity.Api.CellManagementApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**AcceptCellAttachment**](#acceptcellattachment) | **POST** `/identity/api/cellmanagement/acceptattachment` | [EARLY ACCESS] AcceptCellAttachment: Accept (or retry) a cell attachment |
| [**DetachParentCell**](#detachparentcell) | **PUT** `/identity/api/cellmanagement/detach` | [EARLY ACCESS] DetachParentCell: Detach this cell from its parent |
| [**GetCellParentStatus**](#getcellparentstatus) | **GET** `/identity/api/cellmanagement/parentcell` | [EARLY ACCESS] GetCellParentStatus: Get cell parent status |
| [**RefuseCellAttachment**](#refusecellattachment) | **POST** `/identity/api/cellmanagement/refuseattachment` | [EARLY ACCESS] RefuseCellAttachment: Refuse a Proposed cell attachment |
| [**RemovePrimaryDomain**](#removeprimarydomain) | **DELETE** `/identity/api/cellmanagement/primarydomain` | [EARLY ACCESS] RemovePrimaryDomain: Remove primary domain |
| [**SetAttachingKey**](#setattachingkey) | **PUT** `/identity/api/cellmanagement/attachingkey` | [EARLY ACCESS] SetAttachingKey: Store the Attaching Key pasted from the parent admin portal |
| [**SetParentCell**](#setparentcell) | **PUT** `/identity/api/cellmanagement/parentcell` | [EARLY ACCESS] SetParentCell: Set parent cell |
| [**SetPrimaryDomain**](#setprimarydomain) | **PUT** `/identity/api/cellmanagement/primarydomain` | [EARLY ACCESS] SetPrimaryDomain: Set primary domain |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Identity.Api;
using Finbourne.Sdk.Identity.Client;
using Finbourne.Sdk.Identity.Extensions;
using Finbourne.Sdk.Services.Identity.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<CellManagementApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
```

---

<a id="acceptcellattachment"></a>
## AcceptCellAttachment

> CellParentStatusResponse AcceptCellAttachment()

[EARLY ACCESS] AcceptCellAttachment: Accept (or retry) a cell attachment

Confirms a Proposed attachment, or retries one that previously failed: transitions the cell to Attaching and runs the shared registration service to provision the parent-cell service user, mint a PAT, and push it to the parent admin domain. Accepted starting states are `Proposed` (the normal first confirm — anti-circumvention is enforced by requiring a prior `SetAttachingKey`) and `Failed` (recovery from a previous failed attempt). The registration service is idempotent and resumes from the persisted `RegistrationStep` checkpoint, so this is safe to call any number of times after a failure. To abandon a failed attempt instead of retrying, call `Detach`. Only the designated primary domain may call this. Requires JWT authentication.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
CellParentStatusResponse result = apiInstance.AcceptCellAttachment();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the AcceptCellAttachmentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.AcceptCellAttachmentWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="detachparentcell"></a>
## DetachParentCell

> CellParentStatusResponse DetachParentCell(DetachParentCellRequest detachParentCellRequest)

[EARLY ACCESS] DetachParentCell: Detach this cell from its parent

Double-invoke pattern. First call with `Confirm=false` transitions the cell into Detaching; second call with `Confirm=true` executes: deactivates the parent-cell service user, deletes the Attaching Key from ParameterStore, and best-effort notifies the parent admin domain. Accepts `Attached`, `Attaching`, `Failed`, and `Detaching` as valid starting states (call `AcceptAttachment` instead if you'd rather retry a Failed cell than abandon it). Only the designated primary domain may call this. Requires JWT authentication.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
var detachParentCellRequest = new DetachParentCellRequest(); // DetachParentCellRequest
CellParentStatusResponse result = apiInstance.DetachParentCell(detachParentCellRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **detachParentCellRequest** | [DetachParentCellRequest](DetachParentCellRequest.md) | body | **required** |  |

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DetachParentCellWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.DetachParentCellWithHttpInfo(detachParentCellRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getcellparentstatus"></a>
## GetCellParentStatus

> CellParentStatusResponse GetCellParentStatus()

[EARLY ACCESS] GetCellParentStatus: Get cell parent status

Returns the current cell parent relationship status including primary domain, admin domain name, and attachment status.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
CellParentStatusResponse result = apiInstance.GetCellParentStatus();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The cell parent status |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetCellParentStatusWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.GetCellParentStatusWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="refusecellattachment"></a>
## RefuseCellAttachment

> CellParentStatusResponse RefuseCellAttachment()

[EARLY ACCESS] RefuseCellAttachment: Refuse a Proposed cell attachment

Rejects a Proposed attachment, deletes the Attaching Key from ParameterStore, and returns the cell to Standalone. Only the designated primary domain may call this. Requires JWT authentication.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
CellParentStatusResponse result = apiInstance.RefuseCellAttachment();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RefuseCellAttachmentWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.RefuseCellAttachmentWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="removeprimarydomain"></a>
## RemovePrimaryDomain

> CellParentStatusResponse RemovePrimaryDomain()

[EARLY ACCESS] RemovePrimaryDomain: Remove primary domain

Removes the primary domain designation for this cell. Only the current primary domain or FINBOURNE staff can perform this. Requires JWT authentication (PAT tokens are rejected).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
CellParentStatusResponse result = apiInstance.RemovePrimaryDomain();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the RemovePrimaryDomainWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.RemovePrimaryDomainWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setattachingkey"></a>
## SetAttachingKey

> CellParentStatusResponse SetAttachingKey(SetAttachingKeyRequest setAttachingKeyRequest)

[EARLY ACCESS] SetAttachingKey: Store the Attaching Key pasted from the parent admin portal

Persists the Attaching Key PAT to the cell's ParameterStore / Azure Key Vault and records a Proposed attachment against the provided parent admin domain. Only the designated primary domain may call this. Requires JWT authentication (PAT tokens are rejected).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
var setAttachingKeyRequest = new SetAttachingKeyRequest(); // SetAttachingKeyRequest
CellParentStatusResponse result = apiInstance.SetAttachingKey(setAttachingKeyRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **setAttachingKeyRequest** | [SetAttachingKeyRequest](SetAttachingKeyRequest.md) | body | **required** |  |

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetAttachingKeyWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.SetAttachingKeyWithHttpInfo(setAttachingKeyRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setparentcell"></a>
## SetParentCell

> CellParentStatusResponse SetParentCell(SetParentCellRequest setParentCellRequest)

[EARLY ACCESS] SetParentCell: Set parent cell

Sets the parent cell for this cell. Uses a double-invoke pattern: first call (confirm=false) sets status to Proposed, second call (confirm=true) transitions to Attaching. Only the designated primary domain can call this. Requires JWT authentication (PAT tokens are rejected).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
var setParentCellRequest = new SetParentCellRequest(); // SetParentCellRequest
CellParentStatusResponse result = apiInstance.SetParentCell(setParentCellRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **setParentCellRequest** | [SetParentCellRequest](SetParentCellRequest.md) | body | **required** |  |

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetParentCellWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.SetParentCellWithHttpInfo(setParentCellRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="setprimarydomain"></a>
## SetPrimaryDomain

> CellParentStatusResponse SetPrimaryDomain()

[EARLY ACCESS] SetPrimaryDomain: Set primary domain

Designates the calling domain as the primary domain for this cell. Requires JWT authentication (PAT tokens are rejected).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<CellManagementApi>();
CellParentStatusResponse result = apiInstance.SetPrimaryDomain();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[CellParentStatusResponse](CellParentStatusResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated cell parent status |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the SetPrimaryDomainWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<CellParentStatusResponse> response = apiInstance.SetPrimaryDomainWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

