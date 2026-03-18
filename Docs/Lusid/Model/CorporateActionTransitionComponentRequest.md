# Finbourne.Sdk.Lusid.Model.CorporateActionTransitionComponentRequest

A single transition component request, when grouped with other transition component requests a corporate action  transition request is formed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | Unique instrument identifiers |
| **UnitsFactor** | **decimal** | Required | The factor to scale units by |
| **CostFactor** | **decimal** | Required | The factor to scale cost by |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CorporateActionTransitionComponentRequest(
    instrumentIdentifiers: ,  // required — Unique instrument identifiers
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
var instance = JsonConvert.DeserializeObject<CorporateActionTransitionComponentRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

