# Finbourne.Sdk.Luminesce.Api.ApplicationMetadataApi


All URIs are relative to *http://localhost*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**GetServicesAsAccessControlledResources**](#getservicesasaccesscontrolledresources) | **GET** `/honeycomb/api/metadata/access/resources` | GetServicesAsAccessControlledResources: Get resources available for access control |

### Example

```csharp
using System.Collections.Generic;
using Finbourne.Sdk.Services.Luminesce.Api;
using Finbourne.Sdk.Luminesce.Client;
using Finbourne.Sdk.Luminesce.Extensions;
using Finbourne.Sdk.Services.Luminesce.Model;
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
// var apiInstance = ApiFactoryBuilder.Build(secretsFilename, opts: opts).Api<ApplicationMetadataApi>();

var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationMetadataApi>();
```

---

<a id="getservicesasaccesscontrolledresources"></a>
## GetServicesAsAccessControlledResources

> ResourceListOfAccessControlledResource GetServicesAsAccessControlledResources()

GetServicesAsAccessControlledResources: Get resources available for access control

 Get the comprehensive set of resources that are available for access control.  The following LuminesceSql is executed to return this information,  which is then packaged up as AccessControlledResource:  ```sql select     Name,     min(coalesce(Description, Name) || ' (' || Type || ')') as Description from     Sys.Registration where     Type in ('DirectProvider', 'DataProvider')     and     ShowAll = true group by 1 order by 1     ```  The following error codes are to be anticipated with standard Problem Detail reports: - 401 Unauthorized - 403 Forbidden 

### Example

```csharp
var apiInstance = ApiFactoryBuilder.Build(secretsFilename).Api<ApplicationMetadataApi>();
ResourceListOfAccessControlledResource result = apiInstance.GetServicesAsAccessControlledResources();
Console.WriteLine(JsonConvert.SerializeObject(result, Formatting.Indented));
```

### Parameters
This endpoint does not need any parameter.

### Return type

[ResourceListOfAccessControlledResource](ResourceListOfAccessControlledResource.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: `text/plain`, `application/json`, `text/json`

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<details>
<summary>Using the GetServicesAsAccessControlledResourcesWithHttpInfo variant</summary>

This returns an `ApiResponse` object which contains the response data, status code and headers.

```csharp
ApiResponse<ResourceListOfAccessControlledResource> response = apiInstance.GetServicesAsAccessControlledResourcesWithHttpInfo();
Console.WriteLine("Status Code: " + response.StatusCode);
Console.WriteLine("Response Headers: " + JsonConvert.SerializeObject(response.Headers, Formatting.Indented));
Console.WriteLine("Response Body: " + JsonConvert.SerializeObject(response.Data, Formatting.Indented));
```
</details>

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

