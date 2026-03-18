# Finbourne.Sdk.Lusid.Model.SettlementInstructionWithTransaction

A Settlement Instruction with its Matched Transaction (if any)
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SettlementInstruction** | [TransactionSettlementInstruction](TransactionSettlementInstruction.md) | Optional | *No description available.* |
| **MatchedTransaction** | [OutputTransaction](OutputTransaction.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementInstructionWithTransaction(
    settlementInstruction: new TransactionSettlementInstruction(...),  // optional
    matchedTransaction: new OutputTransaction(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementInstructionWithTransaction>(json);
```


## Related Models

- [TransactionSettlementInstruction](TransactionSettlementInstruction.md)
- [OutputTransaction](OutputTransaction.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

