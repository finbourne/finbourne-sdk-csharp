# Finbourne.Sdk.Lusid.Model.OutputTransition

A 'transition' within a corporate action, representing an output transition.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | Unique instrument identifiers |
| **UnitsFactor** | **decimal** | Required | The factor to scale units by |
| **CostFactor** | **decimal** | Required | The factor to scale cost by |
| **LusidInstrumentId** | **string** | Optional | LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers *(read-only)* |
| **InstrumentScope** | **string** | Optional | The scope in which the instrument lies. *(read-only)* |
| **Rounding** | [RoundingConfiguration](RoundingConfiguration.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OutputTransition(
    instrumentIdentifiers: ,  // required — Unique instrument identifiers
    unitsFactor: 0.0d,  // required — The factor to scale units by
    costFactor: 0.0d,  // required — The factor to scale cost by
    lusidInstrumentId: "...",  // optional — LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers
    instrumentScope: "...",  // optional — The scope in which the instrument lies.
    rounding: new RoundingConfiguration(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OutputTransition>(json);
```

- [RoundingConfiguration](RoundingConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

