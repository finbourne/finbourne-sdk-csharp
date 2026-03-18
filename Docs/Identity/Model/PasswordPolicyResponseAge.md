# Finbourne.Sdk.Identity.Model.PasswordPolicyResponseAge

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaxAgeDays** | **int** | Required | The maximum age (in days) a password can be before expiring and needing to be changed |
| **HistoryCount** | **int** | Required | The number of unique passwords that need to be used before a previous password is permitted again |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new PasswordPolicyResponseAge(
    maxAgeDays: 0,  // required — The maximum age (in days) a password can be before expiring and needing to be changed
    historyCount: 0  // required — The number of unique passwords that need to be used before a previous password is permitted again
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PasswordPolicyResponseAge>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

