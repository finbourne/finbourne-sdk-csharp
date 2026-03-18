# Finbourne.Sdk.Lusid.Model.InstrumentDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the instrument. |
| **Identifiers** | [Dictionary&lt;string, InstrumentIdValue&gt;](InstrumentIdValue.md) | Required | A set of identifiers that can be used to identify the instrument. At least one of these must be configured to be a unique identifier. |
| **Properties** | [List&lt;Property&gt;](Property.md) | Optional | Set of unique instrument properties and associated values to store with the instrument. Each property must be from the &#39;Instrument&#39; domain. |
| **LookThroughPortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Definition** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **SettlementCycle** | [SettlementCycle](SettlementCycle.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentDefinition(
    name: "...",  // required — The name of the instrument.
    identifiers: new InstrumentIdValue(...),  // required — A set of identifiers that can be used to identify the instrument. At least one of these must be configured to be a unique identifier.
    properties: new List<Property>(),  // optional — Set of unique instrument properties and associated values to store with the instrument. Each property must be from the &#39;Instrument&#39; domain.
    lookThroughPortfolioId: new ResourceId(...),  // optional
    definition: new LusidInstrument(...),  // optional
    settlementCycle: new SettlementCycle(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentDefinition>(json);
```

- [InstrumentIdValue](InstrumentIdValue.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [LusidInstrument](LusidInstrument.md)
- [SettlementCycle](SettlementCycle.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

