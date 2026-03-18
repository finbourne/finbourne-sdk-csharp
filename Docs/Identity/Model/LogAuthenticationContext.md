# Finbourne.Sdk.Identity.Model.LogAuthenticationContext

Represents a LogAuthenticationContext resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AuthenticationProvider** | **string** | Optional | *No description available.* |
| **CredentialProvider** | **List&lt;string&gt;** | Optional | *No description available.* |
| **CredentialType** | **List&lt;string&gt;** | Optional | *No description available.* |
| **Issuer** | [LogIssuer](LogIssuer.md) | Optional | *No description available.* |
| **Interface** | **string** | Optional | *No description available.* |
| **AuthenticationStep** | **int?** | Optional | *No description available.* |
| **ExternalSessionId** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogAuthenticationContext(
    authenticationProvider: "...",  // optional
    credentialProvider: ,  // optional
    credentialType: ,  // optional
    issuer: new LogIssuer(...),  // optional
    varInterface: "...",  // optional
    authenticationStep: 0,  // optional
    externalSessionId: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogAuthenticationContext>(json);
```

- [LogIssuer](LogIssuer.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

