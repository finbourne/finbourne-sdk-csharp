# Finbourne.Sdk.Lusid.Model.FundCashStatementRow

A single row in a Fund Cash Statement report.  Each row represents a settled cash movement with running balance, cost basis,  average rate, and realised FX PnL.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupById** | **int** | Optional | The groupBy subHoldings and currency. |
| **SequenceNumber** | **int** | Optional | Sequence number determining the order of the cash flow records. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio. |
| **SourceId** | **string** | Optional | The transaction ID that sourced this cash movement. |
| **CashStatementActionType** | **string** | Optional | The action type: Default, Reversal, TrueUp, AvgRateCorrection, Opening, or Closing. |
| **AccountingDate** | **DateTimeOffset** | Optional | The accounting date of the cash movement. |
| **ActivityDate** | **DateTimeOffset** | Optional | The activity date (trade/settlement date) of the cash movement. |
| **MovementName** | **string** | Optional | The movement type (e.g. Receivable_Cash_Trade, Payable_Cash_Trade). |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstructionType** | **string** | Optional | The settlement instruction type: Automatic, Instructed_Complete, Instructed - Cancel Automatic. |
| **DiaryEntryCode** | **string** | Optional | The diary entry code of the valuation point this row belongs to. |
| **OriginDiaryEntryCode** | **string** | Optional | For Reversal/TrueUp rows: the diary entry code of the period the original row belonged to. |
| **CashflowLocal** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **BalanceLocal** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **CashflowBase** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **RealisedFxPnl** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **CostBasisBase** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **AvgRate** | **decimal?** | Optional | Weighted average FX rate (costBasisBase / balanceLocal). Null when balance is zero. |
| **FxRateMovement** | **decimal?** | Optional | FX rate for this specific movement (CashflowBase / CashFlowLocal). Null when localAmount is zero. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundCashStatementRow(
    groupById: 0,  // optional — The groupBy subHoldings and currency.
    sequenceNumber: 0,  // optional — Sequence number determining the order of the cash flow records.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio.
    sourceId: "...",  // optional — The transaction ID that sourced this cash movement.
    cashStatementActionType: "...",  // optional — The action type: Default, Reversal, TrueUp, AvgRateCorrection, Opening, or Closing.
    accountingDate: DateTimeOffset.Now,  // optional — The accounting date of the cash movement.
    activityDate: DateTimeOffset.Now,  // optional — The activity date (trade/settlement date) of the cash movement.
    movementName: "...",  // optional — The movement type (e.g. Receivable_Cash_Trade, Payable_Cash_Trade).
    portfolioId: new ResourceId(...),  // optional
    instructionType: "...",  // optional — The settlement instruction type: Automatic, Instructed_Complete, Instructed - Cancel Automatic.
    diaryEntryCode: "...",  // optional — The diary entry code of the valuation point this row belongs to.
    originDiaryEntryCode: "...",  // optional — For Reversal/TrueUp rows: the diary entry code of the period the original row belonged to.
    cashflowLocal: new CurrencyAndAmount(...),  // optional
    balanceLocal: new CurrencyAndAmount(...),  // optional
    cashflowBase: new CurrencyAndAmount(...),  // optional
    realisedFxPnl: new CurrencyAndAmount(...),  // optional
    costBasisBase: new CurrencyAndAmount(...),  // optional
    avgRate: 0.0d,  // optional — Weighted average FX rate (costBasisBase / balanceLocal). Null when balance is zero.
    fxRateMovement: 0.0d,  // optional — FX rate for this specific movement (CashflowBase / CashFlowLocal). Null when localAmount is zero.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundCashStatementRow>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

