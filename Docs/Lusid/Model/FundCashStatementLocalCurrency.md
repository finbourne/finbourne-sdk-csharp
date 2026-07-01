# Finbourne.Sdk.Lusid.Model.FundCashStatementLocalCurrency

A single row in the local-currency Fund Cash Statement report. Each row is a settled cash  movement with a running balance in local currency only; base-currency columns are out of  scope for this variant and are not returned.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupById** | **int** | Optional | The groupBy subHoldings and currency. |
| **SequenceNumber** | **int** | Optional | Sequence number determining the order of the cash flow records. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio. |
| **SourceId** | **string** | Optional | The transaction ID that sourced this cash movement. |
| **CashStatementActionType** | **string** | Optional | The action type: Default, Reversal, TrueUp, SystemCorrection, Opening, or Closing. |
| **EntryType** | **string** | Optional | What drove the row: SystemGenerated (accounting-engine housekeeping such as a reversal/true-up around a backdated transaction) or UserEntered (a real cash movement booked by a user, e.g. a late trade or amendment). |
| **AccountingDate** | **DateTimeOffset** | Optional | The accounting date of the cash movement. |
| **ActivityDate** | **DateTimeOffset** | Optional | The activity date (trade/settlement date) of the cash movement. |
| **MovementName** | **string** | Optional | The movement type (e.g. Receivable_Cash_Trade, Payable_Cash_Trade). |
| **PortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstructionType** | **string** | Optional | The settlement instruction type: Automatic, Instructed_Complete, Instructed - Cancel Automatic. |
| **DiaryEntryCode** | **string** | Optional | The diary entry code of the valuation point this row belongs to. |
| **OriginDiaryEntryCode** | **string** | Optional | For Reversal/TrueUp rows: the diary entry code of the period the original row belonged to. |
| **CashflowLocal** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **BalanceLocal** | [CurrencyAndAmount](CurrencyAndAmount.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The requested properties decorated onto the cash statement row. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundCashStatementLocalCurrency(
    groupById: 0,  // optional — The groupBy subHoldings and currency.
    sequenceNumber: 0,  // optional — Sequence number determining the order of the cash flow records.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio.
    sourceId: "...",  // optional — The transaction ID that sourced this cash movement.
    cashStatementActionType: "...",  // optional — The action type: Default, Reversal, TrueUp, SystemCorrection, Opening, or Closing.
    entryType: "...",  // optional — What drove the row: SystemGenerated (accounting-engine housekeeping such as a reversal/true-up around a backdated transaction) or UserEntered (a real cash movement booked by a user, e.g. a late trade or amendment).
    accountingDate: DateTimeOffset.Now,  // optional — The accounting date of the cash movement.
    activityDate: DateTimeOffset.Now,  // optional — The activity date (trade/settlement date) of the cash movement.
    movementName: "...",  // optional — The movement type (e.g. Receivable_Cash_Trade, Payable_Cash_Trade).
    portfolioId: new ResourceId(...),  // optional
    instructionType: "...",  // optional — The settlement instruction type: Automatic, Instructed_Complete, Instructed - Cancel Automatic.
    diaryEntryCode: "...",  // optional — The diary entry code of the valuation point this row belongs to.
    originDiaryEntryCode: "...",  // optional — For Reversal/TrueUp rows: the diary entry code of the period the original row belonged to.
    cashflowLocal: new CurrencyAndAmount(...),  // optional
    balanceLocal: new CurrencyAndAmount(...),  // optional
    properties: new Property(...),  // optional — The requested properties decorated onto the cash statement row.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundCashStatementLocalCurrency>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [ResourceId](ResourceId.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

