# Finbourne.Sdk.Identity.Model.CreateExternalTokenIssuerRequest

Client input for creating an external token issuer.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | *No description available.* |
| **Issuer** | **string** | Required | *No description available.* |
| **Audience** | **string** | Required | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **ClaimMappings** | [ClaimMappings](ClaimMappings.md) | Optional | *No description available.* |
| **LogoutUrl** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new CreateExternalTokenIssuerRequest(
    code: "...",  // required
    issuer: "...",  // required
    audience: "...",  // required
    description: "...",  // optional
    claimMappings: new ClaimMappings(...),  // optional
    logoutUrl: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateExternalTokenIssuerRequest>(json);
```

- [ClaimMappings](ClaimMappings.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

