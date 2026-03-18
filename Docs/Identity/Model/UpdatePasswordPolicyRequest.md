# Finbourne.Sdk.Identity.Model.UpdatePasswordPolicyRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Conditions** | [UpdatePasswordPolicyRequestConditions](UpdatePasswordPolicyRequestConditions.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdatePasswordPolicyRequest(
    conditions: new UpdatePasswordPolicyRequestConditions(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePasswordPolicyRequest>(json);
```


## Related Models

- [UpdatePasswordPolicyRequestConditions](UpdatePasswordPolicyRequestConditions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

