# Finbourne.Sdk.Identity.Model.UpdatePasswordPolicyRequestLockout

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaxAttempts** | **int** | Required | The maximum number of unsuccessful attempts before the user is locked out of their account. 0 indicates no limit |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdatePasswordPolicyRequestLockout(
    maxAttempts: 0  // required — The maximum number of unsuccessful attempts before the user is locked out of their account. 0 indicates no limit
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePasswordPolicyRequestLockout>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

