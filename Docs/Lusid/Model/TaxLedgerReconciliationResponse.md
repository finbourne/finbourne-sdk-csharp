# Finbourne.Sdk.Lusid.Model.TaxLedgerReconciliationResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Period** | [TaxAccountingPeriod](TaxAccountingPeriod.md) | Optional | *No description available.* |
| **LedgerCapitalGainLoss** | **decimal** | Optional | The realised and unrealised capital gain or loss recorded in the ledger for the period. |
| **ComparableTaxFigure** | **decimal** | Optional | The tax figure on the same basis as the ledger, before the return adjustments. |
| **Differences** | [List&lt;TaxReconciliationDifferenceRow&gt;](TaxReconciliationDifferenceRow.md) | Optional | The explained differences between the two sides, by holding. |
| **Unexplained** | **decimal** | Optional | The part of the difference not explained by any category. Nil when the reconciliation is complete. |
| **Bridge** | [List&lt;TaxReconciliationBridgeRow&gt;](TaxReconciliationBridgeRow.md) | Optional | The bridge from the ledger figure to the return total. |
| **ReturnTotal** | **decimal** | Optional | The total of lines A, D and LR. |
| **BridgeUnexplained** | **decimal** | Optional | The part of the bridge not explained. Nil when the bridge is complete. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxLedgerReconciliationResponse(
    fundId: new ResourceId(...),  // optional
    period: new TaxAccountingPeriod(...),  // optional
    ledgerCapitalGainLoss: 0.0d,  // optional — The realised and unrealised capital gain or loss recorded in the ledger for the period.
    comparableTaxFigure: 0.0d,  // optional — The tax figure on the same basis as the ledger, before the return adjustments.
    differences: new List<TaxReconciliationDifferenceRow>(),  // optional — The explained differences between the two sides, by holding.
    unexplained: 0.0d,  // optional — The part of the difference not explained by any category. Nil when the reconciliation is complete.
    bridge: new List<TaxReconciliationBridgeRow>(),  // optional — The bridge from the ledger figure to the return total.
    returnTotal: 0.0d,  // optional — The total of lines A, D and LR.
    bridgeUnexplained: 0.0d  // optional — The part of the bridge not explained. Nil when the bridge is complete.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxLedgerReconciliationResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxAccountingPeriod](TaxAccountingPeriod.md)
- [TaxReconciliationDifferenceRow](TaxReconciliationDifferenceRow.md) — used in `Differences`
- [TaxReconciliationBridgeRow](TaxReconciliationBridgeRow.md) — used in `Bridge`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

