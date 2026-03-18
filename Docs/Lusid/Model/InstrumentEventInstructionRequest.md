# Finbourne.Sdk.Lusid.Model.InstrumentEventInstructionRequest

The request to create an instruction for an instrument event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentEventInstructionId** | **string** | Required | The unique identifier for this instruction |
| **InstrumentEventId** | **string** | Required | The identifier of the instrument event being instructed |
| **InstructionType** | **string** | Required | The type of instruction (Ignore, ElectForPortfolio, ElectForHolding, ElectForLoanFacilityHolding) |
| **ElectionKey** | **string** | Optional | For elected instructions, the key to be chosen |
| **HoldingId** | **long?** | Optional | For holding instructions, the id of the holding for which the instruction will apply |
| **EntitlementDateInstructed** | **DateTimeOffset?** | Optional | The instructed entitlement date for the event (where none is set on the event itself) |
| **QuantityInstructed** | [QuantityInstructed](QuantityInstructed.md) | Optional | *No description available.* |
| **TaxLotId** | **string** | Optional | For loan facility holding instructions, the tax lot id of the holding for which the instruction will apply |
| **IgnoreCostImpact** | **bool** | Optional | For loan facility holding instructions, set this flag to &#39;true&#39; if you want the event to not impact cost. If you want to use this option, do not add multiple instructions to the same tax lot or you will get undefined behaviour. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventInstructionRequest(
    instrumentEventInstructionId: "...",  // required — The unique identifier for this instruction
    instrumentEventId: "...",  // required — The identifier of the instrument event being instructed
    instructionType: "...",  // required — The type of instruction (Ignore, ElectForPortfolio, ElectForHolding, ElectForLoanFacilityHolding)
    electionKey: "...",  // optional — For elected instructions, the key to be chosen
    holdingId: 0L,  // optional — For holding instructions, the id of the holding for which the instruction will apply
    entitlementDateInstructed: DateTimeOffset.Now,  // optional — The instructed entitlement date for the event (where none is set on the event itself)
    quantityInstructed: new QuantityInstructed(...),  // optional
    taxLotId: "...",  // optional — For loan facility holding instructions, the tax lot id of the holding for which the instruction will apply
    ignoreCostImpact: true  // optional — For loan facility holding instructions, set this flag to &#39;true&#39; if you want the event to not impact cost. If you want to use this option, do not add multiple instructions to the same tax lot or you will get undefined behaviour.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventInstructionRequest>(json);
```

- [QuantityInstructed](QuantityInstructed.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

