# Finbourne.Sdk.Identity.Model.PasswordPolicyResponseLockout

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaxAttempts** | **int** | Required | The maximum number of unsuccessful attempts before the user is locked out of their account |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new PasswordPolicyResponseLockout(
    maxAttempts: 0  // required — The maximum number of unsuccessful attempts before the user is locked out of their account
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PasswordPolicyResponseLockout>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

