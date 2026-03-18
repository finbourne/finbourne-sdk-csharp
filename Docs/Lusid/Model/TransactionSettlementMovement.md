# Finbourne.Sdk.Lusid.Model.TransactionSettlementMovement

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The movement name (optional) |
| **Type** | **string** | Optional | Movement types determine the impact of the movement on the holdings. The available values are: Settlement, Traded, StockMovement, FutureCash,  Commitment, Receivable, CashSettlement, CashForward, CashCommitment, CashReceivable, Accrual, CashAccrual, ForwardFx, CashFxForward, Carry, CarryAsPnl, VariationMargin, Capital, Fee, Deferred, CashDeferred. |
| **Units** | **decimal** | Optional | The number of units for the movement. |
| **Direction** | **int** | Optional |  A multiplier to apply to Transaction amounts; the values are -1 to indicate to reverse the signs and 1 to indicate to use the signed values from the Transaction directly. For a typical Transaction with unsigned values, 1 means increase, -1 means decrease |
| **SettlementMode** | **string** | Optional | The mode of settlement for the movement which can either be Internal or External. An Internal movement will settle automatically on the contractual settlement date using TransactionConfiguration. An External movement will be determined by portfolio configuration and settlement instruction. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSettlementMovement(
    name: "...",  // optional — The movement name (optional)
    type: "...",  // optional — Movement types determine the impact of the movement on the holdings. The available values are: Settlement, Traded, StockMovement, FutureCash,  Commitment, Receivable, CashSettlement, CashForward, CashCommitment, CashReceivable, Accrual, CashAccrual, ForwardFx, CashFxForward, Carry, CarryAsPnl, VariationMargin, Capital, Fee, Deferred, CashDeferred.
    units: 0.0d,  // optional — The number of units for the movement.
    direction: 0,  // optional —  A multiplier to apply to Transaction amounts; the values are -1 to indicate to reverse the signs and 1 to indicate to use the signed values from the Transaction directly. For a typical Transaction with unsigned values, 1 means increase, -1 means decrease
    settlementMode: "..."  // optional — The mode of settlement for the movement which can either be Internal or External. An Internal movement will settle automatically on the contractual settlement date using TransactionConfiguration. An External movement will be determined by portfolio configuration and settlement instruction.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSettlementMovement>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

