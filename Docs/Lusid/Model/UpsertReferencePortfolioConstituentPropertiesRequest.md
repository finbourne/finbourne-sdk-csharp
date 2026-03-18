# Finbourne.Sdk.Lusid.Model.UpsertReferencePortfolioConstituentPropertiesRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | A set of instrument identifiers that can resolve the constituent to a unique instrument. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Required | The updated collection of properties of the constituent. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertReferencePortfolioConstituentPropertiesRequest(
    identifiers: ,  // required — A set of instrument identifiers that can resolve the constituent to a unique instrument.
    properties: new PerpetualProperty(...)  // required — The updated collection of properties of the constituent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertReferencePortfolioConstituentPropertiesRequest>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

