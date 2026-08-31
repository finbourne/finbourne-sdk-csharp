# Finbourne.Sdk.Lusid.Model.ScenarioDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | *No description available.* |
| **Code** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **ShortCode** | **string** | Optional | A short, memorable identifier for the scenario, for use in reporting. Optional on upsert:  when omitted, reads return a value inferred from the display name (falling back to the  code) rather than null; the inferred value is computed fresh on every read and is never  persisted. When supplied, the value is stored and returned verbatim. Independent of  scenarioType. |
| **ScenarioType** | **string** | Required | Classifies the scenario. Required on upsert; supported string (enumeration) values are:  [Historical, Regulatory, Hypothetical]. Independent of shortCode. Available values: Historical, Regulatory, Hypothetical. |
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
    shortCode: "...",  // optional — A short, memorable identifier for the scenario, for use in reporting. Optional on upsert:  when omitted, reads return a value inferred from the display name (falling back to the  code) rather than null; the inferred value is computed fresh on every read and is never  persisted. When supplied, the value is stored and returned verbatim. Independent of  scenarioType.
    scenarioType: "...",  // required — Classifies the scenario. Required on upsert; supported string (enumeration) values are:  [Historical, Regulatory, Hypothetical]. Independent of shortCode. Available values: Historical, Regulatory, Hypothetical.
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

