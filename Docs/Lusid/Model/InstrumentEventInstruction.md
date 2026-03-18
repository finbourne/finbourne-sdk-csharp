# Finbourne.Sdk.Lusid.Model.InstrumentEventInstruction

An instruction for an instrument event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventInstructionId** | **string** | Optional | The unique identifier for this instruction |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentEventId** | **string** | Optional | The identifier of the instrument event being instructed |
| **InstructionType** | **string** | Optional | The type of instruction (Ignore, ElectForPortfolio, ElectForHolding, ElectForLoanFacilityHolding) |
| **ElectionKey** | **string** | Optional | For elected instructions, the key to be chosen |
| **HoldingId** | **long?** | Optional | For holding instructions, the id of the holding for which the instruction will apply |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The uri for this version of this instruction |
| **EntitlementDateInstructed** | **DateTimeOffset?** | Optional | The instructed entitlement date for the event (where none is set on the event itself) |
| **QuantityInstructed** | [QuantityInstructed](QuantityInstructed.md) | Optional | *No description available.* |
| **TaxLotId** | **string** | Optional | For loan facility holding instructions, the tax lot id of the holding for which the instruction will apply |
| **IgnoreCostImpact** | **bool** | Optional | For loan facility holding instructions, set this flag to &#39;true&#39; if you want the event to not impact cost. If you want to use this option, do not add multiple instructions to the same tax lot or you will get undefined behaviour. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventInstruction(
    instrumentEventInstructionId: "...",  // optional — The unique identifier for this instruction
    portfolioId: new ResourceId(...),  // optional
    instrumentEventId: "...",  // optional — The identifier of the instrument event being instructed
    instructionType: "...",  // optional — The type of instruction (Ignore, ElectForPortfolio, ElectForHolding, ElectForLoanFacilityHolding)
    electionKey: "...",  // optional — For elected instructions, the key to be chosen
    holdingId: 0L,  // optional — For holding instructions, the id of the holding for which the instruction will apply
    varVersion: new ModelVersion(...),  // optional
    href: "...",  // optional — The uri for this version of this instruction
    entitlementDateInstructed: DateTimeOffset.Now,  // optional — The instructed entitlement date for the event (where none is set on the event itself)
    quantityInstructed: new QuantityInstructed(...),  // optional
    taxLotId: "...",  // optional — For loan facility holding instructions, the tax lot id of the holding for which the instruction will apply
    ignoreCostImpact: true,  // optional — For loan facility holding instructions, set this flag to &#39;true&#39; if you want the event to not impact cost. If you want to use this option, do not add multiple instructions to the same tax lot or you will get undefined behaviour.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventInstruction>(json);
```

- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [QuantityInstructed](QuantityInstructed.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

