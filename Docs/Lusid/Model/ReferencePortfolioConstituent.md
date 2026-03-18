# Finbourne.Sdk.Lusid.Model.ReferencePortfolioConstituent

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | Unique instrument identifiers |
| **InstrumentUid** | **string** | Required | LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers |
| **Currency** | **string** | Required | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties associated with the constituent |
| **Weight** | **decimal** | Required | *No description available.* |
| **FloatingWeight** | **decimal?** | Optional | *No description available.* |
| **InstrumentScope** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReferencePortfolioConstituent(
    instrumentIdentifiers: ,  // optional — Unique instrument identifiers
    instrumentUid: "...",  // required — LUSID&#39;s internal unique instrument identifier, resolved from the instrument identifiers
    currency: "...",  // required
    properties: new PerpetualProperty(...),  // optional — Properties associated with the constituent
    weight: 0.0d,  // required
    floatingWeight: 0.0d,  // optional
    instrumentScope: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReferencePortfolioConstituent>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

