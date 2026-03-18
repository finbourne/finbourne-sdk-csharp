# Finbourne.Sdk.Identity.Model.CreateApplicationRequest

A request to create an application for authenticating the source of token requests
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The Display Name of the application |
| **ClientId** | **string** | Required | The OpenID Connect ClientId of the application |
| **Type** | **string** | Required | The Type of the application. This must be either Native or Web |
| **RedirectUris** | **List&lt;string&gt;** | Optional | A web application&#39;s acceptable list of post-login redirect URIs |
| **PostLogoutRedirectUris** | **List&lt;string&gt;** | Optional | A web application&#39;s acceptable list of post-logout redirect URIs |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CreateApplicationRequest(
    displayName: "...",  // required — The Display Name of the application
    clientId: "...",  // required — The OpenID Connect ClientId of the application
    type: "...",  // required — The Type of the application. This must be either Native or Web
    redirectUris: ,  // optional — A web application&#39;s acceptable list of post-login redirect URIs
    postLogoutRedirectUris:   // optional — A web application&#39;s acceptable list of post-logout redirect URIs
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateApplicationRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

