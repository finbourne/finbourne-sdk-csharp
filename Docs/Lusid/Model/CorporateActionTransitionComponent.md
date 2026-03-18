# Finbourne.Sdk.Lusid.Model.CorporateActionTransitionComponent

A single transition component, when grouped with other components a corporate action transition is formed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentScope** | **string** | Required | The scope in which the instrument lies. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | Unique instrument identifiers |
| **InstrumentUid** | **string** | Required | LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers |
| **UnitsFactor** | **decimal** | Required | The factor to scale units by |
| **CostFactor** | **decimal** | Required | The factor to scale cost by |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CorporateActionTransitionComponent(
    instrumentScope: "...",  // required — The scope in which the instrument lies.
    instrumentIdentifiers: ,  // required — Unique instrument identifiers
    instrumentUid: "...",  // required — LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers
    unitsFactor: 0.0d,  // required — The factor to scale units by
    costFactor: 0.0d  // required — The factor to scale cost by
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CorporateActionTransitionComponent>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

