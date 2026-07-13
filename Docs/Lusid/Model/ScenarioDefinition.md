# Finbourne.Sdk.Lusid.Model.ScenarioDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Shifts** | [List&lt;ScenarioShiftDefinition&gt;](ScenarioShiftDefinition.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioDefinition(
    scope: "...",  // required
    code: "...",  // required
    displayName: "...",  // optional
    description: "...",  // optional
    shifts: new List<ScenarioShiftDefinition>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioDefinition>(json);
```

- [ScenarioShiftDefinition](ScenarioShiftDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

