# Finbourne.Sdk.Lusid.Model.UpsertScenarioRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scenario** | [ScenarioDefinition](ScenarioDefinition.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertScenarioRequest(
    scenario: new ScenarioDefinition(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertScenarioRequest>(json);
```


## Related Models

- [ScenarioDefinition](ScenarioDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

