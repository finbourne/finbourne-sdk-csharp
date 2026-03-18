# Finbourne.Sdk.Access.Model.IfExpression

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IfRequestHeaderExpression** | [IfRequestHeaderExpression](IfRequestHeaderExpression.md) | Optional | *No description available.* |
| **IfIdentityClaimExpression** | [IfIdentityClaimExpression](IfIdentityClaimExpression.md) | Optional | *No description available.* |
| **IfIdentityScopeExpression** | [IfIdentityScopeExpression](IfIdentityScopeExpression.md) | Optional | *No description available.* |
| **IfViaApiExpression** | [IfViaApiExpression](IfViaApiExpression.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new IfExpression(
    ifRequestHeaderExpression: new IfRequestHeaderExpression(...),  // optional
    ifIdentityClaimExpression: new IfIdentityClaimExpression(...),  // optional
    ifIdentityScopeExpression: new IfIdentityScopeExpression(...),  // optional
    ifViaApiExpression: new IfViaApiExpression(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IfExpression>(json);
```


## Related Models

- [IfRequestHeaderExpression](IfRequestHeaderExpression.md)
- [IfIdentityClaimExpression](IfIdentityClaimExpression.md)
- [IfIdentityScopeExpression](IfIdentityScopeExpression.md)
- [IfViaApiExpression](IfViaApiExpression.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

