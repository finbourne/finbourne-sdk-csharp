# Finbourne.Sdk.Identity.Model.LogOutcome

Represents a LogOutcome resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Result** | **string** | Optional | *No description available.* |
| **Reason** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogOutcome(
    result: "...",  // optional
    reason: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogOutcome>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

