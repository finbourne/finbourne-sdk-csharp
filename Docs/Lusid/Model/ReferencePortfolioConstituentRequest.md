# Finbourne.Sdk.Lusid.Model.ReferencePortfolioConstituentRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | Unique instrument identifiers |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |
| **Weight** | **decimal** | Required | *No description available.* |
| **Currency** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReferencePortfolioConstituentRequest(
    instrumentIdentifiers: ,  // required — Unique instrument identifiers
    properties: new PerpetualProperty(...),  // optional
    weight: 0.0d,  // required
    currency: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReferencePortfolioConstituentRequest>(json);
```

- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

