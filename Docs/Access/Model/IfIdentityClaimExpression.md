# Finbourne.Sdk.Access.Model.IfIdentityClaimExpression

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ClaimType** | **string** | Required | *No description available.* |
| **ClaimValueType** | **string** | Optional | *No description available.* |
| **ClaimIssuer** | **string** | Optional | *No description available.* |
| **ClaimOriginalIssuer** | **string** | Optional | *No description available.* |
| **Operator** | **TextOperator** | Required | *No description available.* |
| **Value** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new IfIdentityClaimExpression(
    claimType: "...",  // required
    claimValueType: "...",  // optional
    claimIssuer: "...",  // optional
    claimOriginalIssuer: "...",  // optional
    varOperator: ,  // required
    value: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IfIdentityClaimExpression>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

