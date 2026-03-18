# Finbourne.Sdk.Lusid.Model.Investor

Representation of an Investor on the LUSID API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorType** | **string** | Optional | The type of the Investor |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | The identifiers of the Investor |
| **EntityUniqueId** | **string** | Optional | The unique Investor entity identifier |
| **Person** | [Person](Person.md) | Optional | *No description available.* |
| **LegalEntity** | [LegalEntity](LegalEntity.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Investor(
    investorType: "...",  // optional — The type of the Investor
    identifiers: ,  // optional — The identifiers of the Investor
    entityUniqueId: "...",  // optional — The unique Investor entity identifier
    person: new Person(...),  // optional
    legalEntity: new LegalEntity(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Investor>(json);
```

- [Person](Person.md)
- [LegalEntity](LegalEntity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

