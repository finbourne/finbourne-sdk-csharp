# Finbourne.Sdk.Lusid.Model.SettlementActivity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ActivityId** | **string** | Required | A unique identifier for the settlement activity row, composed from the portfolio, activity type and the underlying transaction or settlement instruction. |
| **PortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ActivityType** | **string** | Required | The type of settlement activity: Expected for outstanding units that are due or overdue, or Settled for units that have settled. Available values: Expected, Settled. |
| **ActivityBasis** | **string** | Required | The basis on which the settlement activity arose: Inferred for outstanding units, Automatic for units settled per the portfolio&#39;s settlement configuration, or Instruction for units settled by a settlement instruction. Available values: Inferred, Automatic, Instruction. |
| **ActivityDate** | **DateTimeOffset** | Required | The date of the settlement activity. For Expected activity this is the query&#39;s end activity date; for Automatic settlement it is the contractual settlement date; for Instruction settlement it is the instruction&#39;s actual settlement date. |
| **SettlementCategory** | **string** | Required | The settlement category of the underlying movements. Available values: StockSettlement, CashSettlement, DeferredCashReceipt, NotApplicable. |
| **TransactionId** | **string** | Optional | The identifier of the transaction that gave rise to this settlement activity. Always populated for Expected and Settled activity. |
| **SettlementInstructionId** | **string** | Optional | The identifier of the settlement instruction that settled the activity. Populated only for Instruction settlement; null for Inferred and Automatic activity. |
| **HoldingIds** | **List&lt;long&gt;** | Optional | The identifiers of the holdings whose movements contributed to this settlement activity. |
| **LusidInstrumentId** | **string** | Required | The LUSID instrument identifier (LUID) of the instrument being settled. |
| **InstrumentScope** | **string** | Required | The scope in which the instrument is defined. |
| **ContractualSettlementDate** | **DateTimeOffset** | Required | The contractual settlement date of the underlying movements. |
| **CustodianAccountId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CustodianAccountNumber** | **string** | Optional | The account number of the associated custodian account, if any. |
| **CustodianAccountName** | **string** | Optional | The name of the associated custodian account, if any. |
| **Units** | **decimal** | Required | The signed number of units settled or expected to settle for this activity. |
| **Direction** | **string** | Required | The direction of the settlement from the portfolio&#39;s perspective. Available values: Debit, Credit. |
| **DaysOverdue** | **decimal?** | Optional | The number of days the activity is overdue, calculated as the activity date minus the contractual settlement date. Zero for settled activity. |
| **Transaction** | [OutputTransaction](OutputTransaction.md) | Optional | *No description available.* |
| **SettlementInstruction** | [TransactionSettlementInstruction](TransactionSettlementInstruction.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementActivity(
    activityId: "...",  // required — A unique identifier for the settlement activity row, composed from the portfolio, activity type and the underlying transaction or settlement instruction.
    portfolioId: new ResourceId(...),  // required
    activityType: "...",  // required — The type of settlement activity: Expected for outstanding units that are due or overdue, or Settled for units that have settled. Available values: Expected, Settled.
    activityBasis: "...",  // required — The basis on which the settlement activity arose: Inferred for outstanding units, Automatic for units settled per the portfolio&#39;s settlement configuration, or Instruction for units settled by a settlement instruction. Available values: Inferred, Automatic, Instruction.
    activityDate: DateTimeOffset.Now,  // required — The date of the settlement activity. For Expected activity this is the query&#39;s end activity date; for Automatic settlement it is the contractual settlement date; for Instruction settlement it is the instruction&#39;s actual settlement date.
    settlementCategory: "...",  // required — The settlement category of the underlying movements. Available values: StockSettlement, CashSettlement, DeferredCashReceipt, NotApplicable.
    transactionId: "...",  // optional — The identifier of the transaction that gave rise to this settlement activity. Always populated for Expected and Settled activity.
    settlementInstructionId: "...",  // optional — The identifier of the settlement instruction that settled the activity. Populated only for Instruction settlement; null for Inferred and Automatic activity.
    holdingIds: ,  // optional — The identifiers of the holdings whose movements contributed to this settlement activity.
    lusidInstrumentId: "...",  // required — The LUSID instrument identifier (LUID) of the instrument being settled.
    instrumentScope: "...",  // required — The scope in which the instrument is defined.
    contractualSettlementDate: DateTimeOffset.Now,  // required — The contractual settlement date of the underlying movements.
    custodianAccountId: new ResourceId(...),  // optional
    custodianAccountNumber: "...",  // optional — The account number of the associated custodian account, if any.
    custodianAccountName: "...",  // optional — The name of the associated custodian account, if any.
    units: 0.0d,  // required — The signed number of units settled or expected to settle for this activity.
    direction: "...",  // required — The direction of the settlement from the portfolio&#39;s perspective. Available values: Debit, Credit.
    daysOverdue: 0.0d,  // optional — The number of days the activity is overdue, calculated as the activity date minus the contractual settlement date. Zero for settled activity.
    transaction: new OutputTransaction(...),  // optional
    settlementInstruction: new TransactionSettlementInstruction(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementActivity>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [OutputTransaction](OutputTransaction.md)
- [TransactionSettlementInstruction](TransactionSettlementInstruction.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

