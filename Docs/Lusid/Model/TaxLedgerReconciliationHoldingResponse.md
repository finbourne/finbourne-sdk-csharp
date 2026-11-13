# Finbourne.Sdk.Lusid.Model.TaxLedgerReconciliationHoldingResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Period** | [TaxAccountingPeriod](TaxAccountingPeriod.md) | Optional | *No description available.* |
| **HoldingId** | **string** | Optional | The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier. |
| **InstrumentId** | **string** | Optional | The LUSID unique identifier of the instrument. |
| **InstrumentName** | **string** | Optional | The name of the instrument. |
| **PortfolioCode** | **string** | Optional | The code of the portfolio the holding sits in, or the pooled marker for a company. |
| **LedgerRealised** | **decimal** | Optional | The realised gain or loss recorded in the ledger for the holding. |
| **LedgerUnrealisedMovement** | **decimal** | Optional | The movement in unrealised gain or loss recorded in the ledger for the holding. |
| **TaxRealisedUnindexed** | **decimal** | Optional | The realised gain or loss for tax before indexation. |
| **TaxUnrealisedMovementUnindexed** | **decimal** | Optional | The movement in the unrealised gain or loss for tax before indexation. |
| **DeemedDisposalNet** | **decimal** | Optional | The net deemed-disposal amount for the holding. |
| **LoanRelationshipNet** | **decimal** | Optional | The net loan relationship credit or debit for the holding. |
| **Category** | **string** | Optional | The reconciliation category of the difference, when there is one. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest. |
| **Difference** | **decimal** | Optional | The difference between the two sides. |
| **Explanation** | **string** | Optional | The explanation of the difference. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxLedgerReconciliationHoldingResponse(
    fundId: new ResourceId(...),  // optional
    period: new TaxAccountingPeriod(...),  // optional
    holdingId: "...",  // optional — The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier.
    instrumentId: "...",  // optional — The LUSID unique identifier of the instrument.
    instrumentName: "...",  // optional — The name of the instrument.
    portfolioCode: "...",  // optional — The code of the portfolio the holding sits in, or the pooled marker for a company.
    ledgerRealised: 0.0d,  // optional — The realised gain or loss recorded in the ledger for the holding.
    ledgerUnrealisedMovement: 0.0d,  // optional — The movement in unrealised gain or loss recorded in the ledger for the holding.
    taxRealisedUnindexed: 0.0d,  // optional — The realised gain or loss for tax before indexation.
    taxUnrealisedMovementUnindexed: 0.0d,  // optional — The movement in the unrealised gain or loss for tax before indexation.
    deemedDisposalNet: 0.0d,  // optional — The net deemed-disposal amount for the holding.
    loanRelationshipNet: 0.0d,  // optional — The net loan relationship credit or debit for the holding.
    category: "...",  // optional — The reconciliation category of the difference, when there is one. Available values: ExcludedHoldings, TaxCostAdjustments, OutOfSync, Scope, PoolAveraging, Matching, Indexation, KinkTest.
    difference: 0.0d,  // optional — The difference between the two sides.
    explanation: "..."  // optional — The explanation of the difference.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxLedgerReconciliationHoldingResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxAccountingPeriod](TaxAccountingPeriod.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

