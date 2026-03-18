# Finbourne.Sdk.Identity.Model.PasswordPolicyResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Conditions** | [PasswordPolicyResponseConditions](PasswordPolicyResponseConditions.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new PasswordPolicyResponse(
    conditions: new PasswordPolicyResponseConditions(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PasswordPolicyResponse>(json);
```


## Related Models

- [PasswordPolicyResponseConditions](PasswordPolicyResponseConditions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

