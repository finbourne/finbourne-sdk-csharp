# Finbourne.Sdk.Lusid.Api.PackagesApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**DeletePackage**](#deletepackage) | **DELETE** `/api/api/packages/{scope}/{code}` | [EXPERIMENTAL] DeletePackage: Delete package |
| [**GetPackage**](#getpackage) | **GET** `/api/api/packages/{scope}/{code}` | [EXPERIMENTAL] GetPackage: Get Package |
| [**ListPackages**](#listpackages) | **GET** `/api/api/packages` | [EXPERIMENTAL] ListPackages: List Packages |
| [**UpsertPackages**](#upsertpackages) | **POST** `/api/api/packages` | [EXPERIMENTAL] UpsertPackages: Upsert Package |

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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<PackagesApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PackagesApi>();
```

---

<a id="deletepackage"></a>
## DeletePackage

> DeletedEntityResponse DeletePackage(string scope, string code)

[EXPERIMENTAL] DeletePackage: Delete package

Delete an package. Deletion will be valid from the package's creation datetime.  This means that the package will no longer exist at any effective datetime from the asAt datetime of deletion.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PackagesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
DeletedEntityResponse result = apiInstance.DeletePackage(scope, code);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The package scope. |
| **code** | **string** | path | **required** | The package&#39;s code. This, together with the scope uniquely identifies the package to delete. |

### Return type

[DeletedEntityResponse](DeletedEntityResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The response from deleting an package. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the DeletePackageWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<DeletedEntityResponse> response = apiInstance.DeletePackageWithHttpInfo(scope, code);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="getpackage"></a>
## GetPackage

> Package GetPackage(string scope, string code, DateTimeOffset? asAt = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] GetPackage: Get Package

Fetch a Package that matches the specified identifier

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PackagesApi>();
var scope = "scope_example";  // string
var code = "code_example";  // string
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
Package result = apiInstance.GetPackage(scope, code, asAt, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **scope** | **string** | path | **required** | The scope to which the package belongs. |
| **code** | **string** | path | **required** | The package&#39;s unique identifier. |
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the package. Defaults to return the latest version of the package if not specified. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Package\&quot; domain to decorate onto the package.              These take the format {domain}/{scope}/{code} e.g. \&quot;Package/system/Name\&quot;. |

### Return type

[Package](Package.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The package matching the given identifier. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the GetPackageWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<Package> response = apiInstance.GetPackageWithHttpInfo(scope, code, asAt, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="listpackages"></a>
## ListPackages

> PagedResourceListOfPackage ListPackages(DateTimeOffset? asAt = null, string? page = null, List<string>? sortBy = null, int? limit = null, string? filter = null, List<string>? propertyKeys = null)

[EXPERIMENTAL] ListPackages: List Packages

Fetch the last pre-AsAt date version of each package in scope (does not fetch the entire history).

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PackagesApi>();
var asAt = DateTimeOffset.Parse("2013-10-20T19:20:30+01:00");  // DateTimeOffset? (optional)
var page = "page_example";  // string? (optional)
var sortBy = new List<string>?(); // List<string>? (optional)
var limit = 56;  // int? (optional)
var filter = "filter_example";  // string? (optional)
var propertyKeys = new List<string>?(); // List<string>? (optional)
PagedResourceListOfPackage result = apiInstance.ListPackages(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **asAt** | **DateTimeOffset?** | query | optional | The asAt datetime at which to retrieve the package. Defaults to return the latest version of the package if not specified. |
| **page** | **string?** | query | optional | The pagination token to use to continue listing packages from a previous call to list packages.              This value is returned from the previous call. If a pagination token is provided the sortBy, filter, effectiveAt, and asAt fields              must not have changed since the original request. |
| **sortBy** | [List&lt;string&gt;?](string.md) | query | optional | A list of field names or properties to sort by, each suffixed by \&quot; ASC\&quot; or \&quot; DESC\&quot;. |
| **limit** | **int?** | query | optional | When paginating, limit the number of returned results to this many. |
| **filter** | **string?** | query | optional | Expression to filter the result set. Read more about filtering results from LUSID here:              https://support.lusid.com/filtering-results-from-lusid. |
| **propertyKeys** | [List&lt;string&gt;?](string.md) | query | optional | A list of property keys from the \&quot;Package\&quot; domain to decorate onto each package.                  These take the format {domain}/{scope}/{code} e.g. \&quot;Package/system/Name\&quot;.                  All properties, except derived properties, are returned by default, without specifying here. |

### Return type

[PagedResourceListOfPackage](PagedResourceListOfPackage.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Packages in scope. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the ListPackagesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<PagedResourceListOfPackage> response = apiInstance.ListPackagesWithHttpInfo(asAt, page, sortBy, limit, filter, propertyKeys);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

---

<a id="upsertpackages"></a>
## UpsertPackages

> ResourceListOfPackage UpsertPackages(PackageSetRequest? packageSetRequest = null)

[EXPERIMENTAL] UpsertPackages: Upsert Package

Upsert; update existing packages with given ids, or create new packages otherwise.

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<PackagesApi>();
var packageSetRequest = new PackageSetRequest?(); // PackageSetRequest? (optional)
ResourceListOfPackage result = apiInstance.UpsertPackages(packageSetRequest);
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters

| Name | Type | In | Required | Description |
|------|------|----|----------|-------------|
| **packageSetRequest** | [PackageSetRequest?](PackageSetRequest?.md) | body | optional | The collection of package requests. |

### Return type

[ResourceListOfPackage](ResourceListOfPackage.md)

### HTTP request headers

 - **Content-Type**: `application/json-patch+json`, `application/json`, `text/json`, `application/*+json`
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | A collection of packages. |  -  |
| **400** | The details of the input related failure |  -  |
| **0** | Error response |  -  |

<details>
<summary>Using the UpsertPackagesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfPackage> response = apiInstance.UpsertPackagesWithHttpInfo(packageSetRequest);
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

