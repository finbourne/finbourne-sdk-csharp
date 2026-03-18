# Finbourne.Sdk.Identity.Model.UpdateExternalTokenIssuerRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Issuer** | **string** | Optional | *No description available.* |
| **Audience** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **ClaimMappings** | [ClaimMappings](ClaimMappings.md) | Optional | *No description available.* |
| **LogoutUrl** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdateExternalTokenIssuerRequest(
    issuer: "...",  // optional
    audience: "...",  // optional
    description: "...",  // optional
    claimMappings: new ClaimMappings(...),  // optional
    logoutUrl: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateExternalTokenIssuerRequest>(json);
```

- [ClaimMappings](ClaimMappings.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

