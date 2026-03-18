# Finbourne.Sdk.Identity.Model.UpdatePasswordPolicyRequestAge

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaxAgeDays** | **int** | Required | The maximum age (in days) a password can be before expiring and needing to be changed. 0 indicates no limit |
| **HistoryCount** | **int** | Required | The number of unique passwords that need to be used before a previous password is permitted again. 0 indicates none |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new UpdatePasswordPolicyRequestAge(
    maxAgeDays: 0,  // required — The maximum age (in days) a password can be before expiring and needing to be changed. 0 indicates no limit
    historyCount: 0  // required — The number of unique passwords that need to be used before a previous password is permitted again. 0 indicates none
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdatePasswordPolicyRequestAge>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

