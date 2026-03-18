# Finbourne.Sdk.Identity.Model.ExternalTokenIssuerResponse

Response DTO exposed to client for an external token issuer.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Optional | The External Token Issuer Code |
| **Issuer** | **string** | Optional | Issuer of the External Token Issuer |
| **Audience** | **string** | Optional | Audience of the External Token Issuer |
| **Description** | **string** | Optional | The Description of the External Token Issuer |
| **ClaimMappings** | [ClaimMappings](ClaimMappings.md) | Optional | *No description available.* |
| **LogoutUrl** | **string** | Optional | The LogoutUrl of the External Token Issuer |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new ExternalTokenIssuerResponse(
    code: "...",  // optional — The External Token Issuer Code
    issuer: "...",  // optional — Issuer of the External Token Issuer
    audience: "...",  // optional — Audience of the External Token Issuer
    description: "...",  // optional — The Description of the External Token Issuer
    claimMappings: new ClaimMappings(...),  // optional
    logoutUrl: "..."  // optional — The LogoutUrl of the External Token Issuer
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalTokenIssuerResponse>(json);
```

- [ClaimMappings](ClaimMappings.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

