# Finbourne.Sdk.Identity.Model.PasswordPolicyResponseConditions

Password policy conditions for a password policy
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Complexity** | [PasswordPolicyResponseComplexity](PasswordPolicyResponseComplexity.md) | Required | *No description available.* |
| **Age** | [PasswordPolicyResponseAge](PasswordPolicyResponseAge.md) | Required | *No description available.* |
| **Lockout** | [PasswordPolicyResponseLockout](PasswordPolicyResponseLockout.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new PasswordPolicyResponseConditions(
    complexity: new PasswordPolicyResponseComplexity(...),  // required
    age: new PasswordPolicyResponseAge(...),  // required
    lockout: new PasswordPolicyResponseLockout(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PasswordPolicyResponseConditions>(json);
```


## Related Models

- [PasswordPolicyResponseComplexity](PasswordPolicyResponseComplexity.md)
- [PasswordPolicyResponseAge](PasswordPolicyResponseAge.md)
- [PasswordPolicyResponseLockout](PasswordPolicyResponseLockout.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

