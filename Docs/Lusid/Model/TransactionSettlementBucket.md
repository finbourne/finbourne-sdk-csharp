# Finbourne.Sdk.Lusid.Model.TransactionSettlementBucket

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementCategory** | **string** | Required | A category representing the set of movement types that this instruction applies to. |
| **LusidInstrumentId** | **string** | Required | The LusidInstrumentId of the instrument being settled. |
| **InstrumentScope** | **string** | Required | The Scope of the instrument being settled. |
| **ContractualSettlementDate** | **DateTimeOffset?** | Optional | The contractual settlement date. Used to match the instruction to the correct settlement bucket. |
| **ContractedUnits** | **decimal** | Optional | The contracted units. |
| **SettledUnits** | **decimal** | Optional | The settled units. |
| **UnsettledUnits** | **decimal** | Optional | The unsettled units. |
| **OverdueUnits** | **decimal** | Optional | The overdue units. |
| **ConfiguredSettlement** | **string** | Optional | The method of settlement for the settlement bucket, as defined in the portfolio&#39;s SettlementConfiguration |
| **Status** | **string** | Required | The Status of the settlement bucket - &#39;Settled&#39;, &#39;Part Settled&#39; or &#39;Unsettled&#39;. |
| **SettlementInstructions** | [List&lt;TransactionSettlementInstruction&gt;](TransactionSettlementInstruction.md) | Optional | The settlement instructions received for this settlement bucket. |
| **Movements** | [List&lt;TransactionSettlementMovement&gt;](TransactionSettlementMovement.md) | Optional | The movements for the settlement bucket. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSettlementBucket(
    settlementCategory: "...",  // required — A category representing the set of movement types that this instruction applies to.
    lusidInstrumentId: "...",  // required — The LusidInstrumentId of the instrument being settled.
    instrumentScope: "...",  // required — The Scope of the instrument being settled.
    contractualSettlementDate: DateTimeOffset.Now,  // optional — The contractual settlement date. Used to match the instruction to the correct settlement bucket.
    contractedUnits: 0.0d,  // optional — The contracted units.
    settledUnits: 0.0d,  // optional — The settled units.
    unsettledUnits: 0.0d,  // optional — The unsettled units.
    overdueUnits: 0.0d,  // optional — The overdue units.
    configuredSettlement: "...",  // optional — The method of settlement for the settlement bucket, as defined in the portfolio&#39;s SettlementConfiguration
    status: "...",  // required — The Status of the settlement bucket - &#39;Settled&#39;, &#39;Part Settled&#39; or &#39;Unsettled&#39;.
    settlementInstructions: new List<TransactionSettlementInstruction>(),  // optional — The settlement instructions received for this settlement bucket.
    movements: new List<TransactionSettlementMovement>()  // optional — The movements for the settlement bucket.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSettlementBucket>(json);
```

- [TransactionSettlementInstruction](TransactionSettlementInstruction.md) — used in `SettlementInstructions`
- [TransactionSettlementMovement](TransactionSettlementMovement.md) — used in `Movements`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

