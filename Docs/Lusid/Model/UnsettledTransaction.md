# Finbourne.Sdk.Lusid.Model.UnsettledTransaction

A transaction that remains unsettled as at the valuation point, with per-bucket settlement status.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Transaction** | [OutputTransaction](OutputTransaction.md) | Optional | *No description available.* |
| **PortfolioId** | [PortfolioId](PortfolioId.md) | Optional | *No description available.* |
| **OverallSettlementStatus** | **string** | Optional | The overall settlement status of the transaction (Unsettled, PartSettled, Settled, None). |
| **OverallIsOverdue** | **bool** | Optional | Whether the transaction is overdue for settlement. |
| **CashSettlementStatus** | **string** | Optional | The settlement status of the cash component. |
| **CashIsOverdue** | **bool** | Optional | Whether the cash component is overdue for settlement. |
| **StockSettlementStatus** | **string** | Optional | The settlement status of the stock component. |
| **StockIsOverdue** | **bool** | Optional | Whether the stock component is overdue for settlement. |
| **DeferredCashSettlementStatus** | **string** | Optional | The settlement status of the deferred cash component. |
| **DeferredCashIsOverdue** | **bool** | Optional | Whether the deferred cash component is overdue for settlement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnsettledTransaction(
    transaction: new OutputTransaction(...),  // optional
    portfolioId: new PortfolioId(...),  // optional
    overallSettlementStatus: "...",  // optional — The overall settlement status of the transaction (Unsettled, PartSettled, Settled, None).
    overallIsOverdue: true,  // optional — Whether the transaction is overdue for settlement.
    cashSettlementStatus: "...",  // optional — The settlement status of the cash component.
    cashIsOverdue: true,  // optional — Whether the cash component is overdue for settlement.
    stockSettlementStatus: "...",  // optional — The settlement status of the stock component.
    stockIsOverdue: true,  // optional — Whether the stock component is overdue for settlement.
    deferredCashSettlementStatus: "...",  // optional — The settlement status of the deferred cash component.
    deferredCashIsOverdue: true  // optional — Whether the deferred cash component is overdue for settlement.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnsettledTransaction>(json);
```


## Related Models

- [OutputTransaction](OutputTransaction.md)
- [PortfolioId](PortfolioId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

