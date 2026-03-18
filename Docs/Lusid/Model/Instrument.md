# Finbourne.Sdk.Lusid.Model.Instrument

A list of instruments.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Scope** | **string** | Optional | The scope in which the instrument lies. |
| **LusidInstrumentId** | **string** | Required | The unique LUSID Instrument Identifier (LUID) of the instrument. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Name** | **string** | Required | The name of the instrument. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | The set of identifiers that can be used to identify the instrument. |
| **Properties** | [List&lt;Property&gt;](Property.md) | Optional | The requested instrument properties. These will be from the &#39;Instrument&#39; domain. |
| **LookthroughPortfolio** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentDefinition** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **State** | **string** | Required | The state of of the instrument at the asAt datetime of this version of the instrument definition. The available values are: Active, Inactive, Deleted |
| **AssetClass** | **string** | Optional | The nominal asset class of the instrument, e.g. InterestRates, FX, Inflation, Equities, Credit, Commodities, etc. The available values are: InterestRates, FX, Inflation, Equities, Credit, Commodities, Money, Unknown |
| **DomCcy** | **string** | Optional | The domestic currency, meaning the currency in which the instrument would typically be expected to pay cashflows, e.g. a share in AAPL being USD. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Optional | A set of relationships associated to the instrument. |
| **SettlementCycle** | [SettlementCycle](SettlementCycle.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Instrument(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    scope: "...",  // optional — The scope in which the instrument lies.
    lusidInstrumentId: "...",  // required — The unique LUSID Instrument Identifier (LUID) of the instrument.
    varVersion: new ModelVersion(...),  // required
    stagedModifications: new StagedModificationsInfo(...),  // optional
    name: "...",  // required — The name of the instrument.
    identifiers: ,  // required — The set of identifiers that can be used to identify the instrument.
    properties: new List<Property>(),  // optional — The requested instrument properties. These will be from the &#39;Instrument&#39; domain.
    lookthroughPortfolio: new ResourceId(...),  // optional
    instrumentDefinition: new LusidInstrument(...),  // optional
    state: "...",  // required — The state of of the instrument at the asAt datetime of this version of the instrument definition. The available values are: Active, Inactive, Deleted
    assetClass: "...",  // optional — The nominal asset class of the instrument, e.g. InterestRates, FX, Inflation, Equities, Credit, Commodities, etc. The available values are: InterestRates, FX, Inflation, Equities, Credit, Commodities, Money, Unknown
    domCcy: "...",  // optional — The domestic currency, meaning the currency in which the instrument would typically be expected to pay cashflows, e.g. a share in AAPL being USD.
    relationships: new List<Relationship>(),  // optional — A set of relationships associated to the instrument.
    settlementCycle: new SettlementCycle(...),  // optional
    dataModelMembership: new DataModelMembership(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Instrument>(json);
```

- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Property](Property.md) — used in `Properties`
- [ResourceId](ResourceId.md)
- [LusidInstrument](LusidInstrument.md)
- [Relationship](Relationship.md) — used in `Relationships`
- [SettlementCycle](SettlementCycle.md)
- [DataModelMembership](DataModelMembership.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

