# Finbourne.Sdk.Identity.Model.UpdatePasswordPolicyRequestConditions

Password policy conditions for a password policy
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Complexity** | [UpdatePasswordPolicyRequestComplexity](UpdatePasswordPolicyRequestComplexity.md) | Required | *No description available.* |
| **Age** | [UpdatePasswordPolicyRequestAge](UpdatePasswordPolicyRequestAge.md) | Required | *No description available.* |
| **Lockout** | [UpdatePasswordPolicyRequestLockout](UpdatePasswordPolicyRequestLockout.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdatePasswordPolicyRequestConditions(
    complexity: new UpdatePasswordPolicyRequestComplexity(...),  // required
    age: new UpdatePasswordPolicyRequestAge(...),  // required
    lockout: new UpdatePasswordPolicyRequestLockout(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePasswordPolicyRequestConditions>(json);
```


## Related Models

- [UpdatePasswordPolicyRequestComplexity](UpdatePasswordPolicyRequestComplexity.md)
- [UpdatePasswordPolicyRequestAge](UpdatePasswordPolicyRequestAge.md)
- [UpdatePasswordPolicyRequestLockout](UpdatePasswordPolicyRequestLockout.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

