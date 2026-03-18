# Finbourne.Sdk.Lusid.Model.TransactionSettlementInstruction

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementInstructionId** | **string** | Required | The instruction identifier. Unique within the portfolio. |
| **InstructionType** | **string** | Required | The type of instruction which can be Complete or CancelAutomatic. Complete means that the instruction is intended to completely settle a settlement bucket. CancelAutomatic means that it is intended to cancel Automatic settlement. |
| **ActualSettlementDate** | **DateTimeOffset** | Required | The date that settlement takes place. |
| **Units** | **decimal** | Required | The number of units for the instruction. |
| **TransactionId** | **string** | Required | The ID for the transaction being instructed. |
| **SettlementCategory** | **string** | Required | A category representing the set of movement types that this instruction applies to. |
| **LusidInstrumentId** | **string** | Required | The LusidInstrumentId of the instrument being settled. |
| **ContractualSettlementDate** | **DateTimeOffset?** | Optional | The contractual settlement date. Used to match the instruction to the correct settlement bucket. |
| **SubHoldingKeyOverrides** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Allows one or more sub-holding keys to be overridden for any movement being settled by an instruction. Providing a key and value will set the sub-holding key to the specified value; Providing a key only will nullify the sub-holding key. Not referenced sub-holding keys will not be impacted.  |
| **CustodianAccountOverride** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | A set of instrument identifiers that can resolve the settlement instruction to a unique instrument. |
| **Status** | **string** | Optional | The status of the settlement instruction - &#39;Invalid&#39;, &#39;Rejected&#39; &#39;Applied&#39; or &#39;Orphan&#39;. |
| **InstructionToPortfolioRate** | **decimal?** | Optional | The exchange rate between the Settlement Instruction and Portfolio. |
| **SettlementInLieu** | [SettlementInLieu](SettlementInLieu.md) | Optional | *No description available.* |
| **IsActive** | **bool** | Optional | Indicates whether the settlement instruction is active. When false, the instruction has no impact on settlement positions, but remains visible. Defaults to true. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The properties which have been requested to be decorated onto the settlement instruction. These will be from the &#39;SettlementInstruction&#39;, &#39;Portfolio&#39;, or &#39;Instrument&#39; domains. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSettlementInstruction(
    settlementInstructionId: "...",  // required — The instruction identifier. Unique within the portfolio.
    instructionType: "...",  // required — The type of instruction which can be Complete or CancelAutomatic. Complete means that the instruction is intended to completely settle a settlement bucket. CancelAutomatic means that it is intended to cancel Automatic settlement.
    actualSettlementDate: DateTimeOffset.Now,  // required — The date that settlement takes place.
    units: 0.0d,  // required — The number of units for the instruction.
    transactionId: "...",  // required — The ID for the transaction being instructed.
    settlementCategory: "...",  // required — A category representing the set of movement types that this instruction applies to.
    lusidInstrumentId: "...",  // required — The LusidInstrumentId of the instrument being settled.
    contractualSettlementDate: DateTimeOffset.Now,  // optional — The contractual settlement date. Used to match the instruction to the correct settlement bucket.
    subHoldingKeyOverrides: new PerpetualProperty(...),  // optional — Allows one or more sub-holding keys to be overridden for any movement being settled by an instruction. Providing a key and value will set the sub-holding key to the specified value; Providing a key only will nullify the sub-holding key. Not referenced sub-holding keys will not be impacted. 
    custodianAccountOverride: new ResourceId(...),  // optional
    instrumentIdentifiers: ,  // required — A set of instrument identifiers that can resolve the settlement instruction to a unique instrument.
    status: "...",  // optional — The status of the settlement instruction - &#39;Invalid&#39;, &#39;Rejected&#39; &#39;Applied&#39; or &#39;Orphan&#39;.
    instructionToPortfolioRate: 0.0d,  // optional — The exchange rate between the Settlement Instruction and Portfolio.
    settlementInLieu: new SettlementInLieu(...),  // optional
    isActive: true,  // optional — Indicates whether the settlement instruction is active. When false, the instruction has no impact on settlement positions, but remains visible. Defaults to true.
    properties: new PerpetualProperty(...),  // optional — The properties which have been requested to be decorated onto the settlement instruction. These will be from the &#39;SettlementInstruction&#39;, &#39;Portfolio&#39;, or &#39;Instrument&#39; domains.
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSettlementInstruction>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeyOverrides`
- [ResourceId](ResourceId.md)
- [SettlementInLieu](SettlementInLieu.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

