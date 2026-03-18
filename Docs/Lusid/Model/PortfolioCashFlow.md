# Finbourne.Sdk.Lusid.Model.PortfolioCashFlow

The details for the cashflow for a given portfolio.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupById** | **int** | Required | The groupBy subHoldings and currency. |
| **SequenceNumber** | **int** | Required | Sequence number determining the order of the cash flow records. |
| **EffectiveDate** | **DateTimeOffset** | Optional | Indicates the date when the cash-flow settles. |
| **SubHoldingKeys** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio. |
| **Type** | **string** | Required | Indicates the record type (Closed, Open, Activity). |
| **MovementName** | **string** | Required | Indicates the specific movement of the transaction that generated this cash flow. |
| **Cashflow** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Balance** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **FxRate** | **decimal** | Required | Exchange rate between the currency of this cash flow and the reporting currency. |
| **CashflowReportingCurrency** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **BalanceReportingCurrency** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **TranslationGainLoss** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **CostBasisReportingCurrency** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Transaction** | [Transaction](Transaction.md) | Optional | *No description available.* |
| **UnrealisedGainLossReportingCurrency** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioCashFlow(
    groupById: 0,  // required — The groupBy subHoldings and currency.
    sequenceNumber: 0,  // required — Sequence number determining the order of the cash flow records.
    effectiveDate: DateTimeOffset.Now,  // optional — Indicates the date when the cash-flow settles.
    subHoldingKeys: new PerpetualProperty(...),  // optional — The sub-holding properties which identify the holding. Each property will be from the &#39;Transaction&#39; domain. These are configured on a transaction portfolio.
    type: "...",  // required — Indicates the record type (Closed, Open, Activity).
    movementName: "...",  // required — Indicates the specific movement of the transaction that generated this cash flow.
    cashflow: new CurrencyAndAmount(...),  // required
    balance: new CurrencyAndAmount(...),  // required
    fxRate: 0.0d,  // required — Exchange rate between the currency of this cash flow and the reporting currency.
    cashflowReportingCurrency: new CurrencyAndAmount(...),  // required
    balanceReportingCurrency: new CurrencyAndAmount(...),  // required
    translationGainLoss: new CurrencyAndAmount(...),  // required
    costBasisReportingCurrency: new CurrencyAndAmount(...),  // required
    transaction: new Transaction(...),  // optional
    unrealisedGainLossReportingCurrency: new CurrencyAndAmount(...),  // required
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioCashFlow>(json);
```

- [PerpetualProperty](PerpetualProperty.md) — used in `SubHoldingKeys`
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Transaction](Transaction.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

