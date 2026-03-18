# Finbourne.Sdk.Lusid.Model.TransactionSettlementStatus

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | The unique identifier for the transaction. |
| **SettlementBuckets** | [List&lt;TransactionSettlementBucket&gt;](TransactionSettlementBucket.md) | Optional | The transaction&#39;s external movements (ie: with SettlementMode&#x3D;External) are grouped into buckets with each bucket uniquely defined by the combination of SettlementCategory, LusidInstrumentId, InstrumentScope and ContractualSettlementDate. |
| **InvalidInstructions** | [List&lt;TransactionSettlementInstruction&gt;](TransactionSettlementInstruction.md) | Optional | Invalid settlement instructions where the referenced transaction exists but the settlement bucket implied by the settlement instruction does not exist. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSettlementStatus(
    transactionId: "...",  // required — The unique identifier for the transaction.
    settlementBuckets: new List<TransactionSettlementBucket>(),  // optional — The transaction&#39;s external movements (ie: with SettlementMode&#x3D;External) are grouped into buckets with each bucket uniquely defined by the combination of SettlementCategory, LusidInstrumentId, InstrumentScope and ContractualSettlementDate.
    invalidInstructions: new List<TransactionSettlementInstruction>(),  // optional — Invalid settlement instructions where the referenced transaction exists but the settlement bucket implied by the settlement instruction does not exist.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSettlementStatus>(json);
```

- [TransactionSettlementBucket](TransactionSettlementBucket.md) — used in `SettlementBuckets`
- [TransactionSettlementInstruction](TransactionSettlementInstruction.md) — used in `InvalidInstructions`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

