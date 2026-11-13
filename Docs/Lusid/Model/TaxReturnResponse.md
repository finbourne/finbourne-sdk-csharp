# Finbourne.Sdk.Lusid.Model.TaxReturnResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Period** | [TaxAccountingPeriod](TaxAccountingPeriod.md) | Optional | *No description available.* |
| **Status** | **string** | Optional | The workflow status of the return. Available values: Draft, Prepared, Reviewed, SignedOff, Final. Available values: Draft, Prepared, Reviewed, SignedOff, Final. |
| **Steps** | [List&lt;TaxReturnWorkflowStep&gt;](TaxReturnWorkflowStep.md) | Optional | The workflow history of the return in the order the steps were taken. |
| **LineA** | [List&lt;TaxReturnDisposalRow&gt;](TaxReturnDisposalRow.md) | Optional | Chargeable gains and allowable losses on actual disposals in the period. |
| **LineATotal** | **decimal** | Optional | The total of line A, in whole pounds. |
| **Vintages** | [List&lt;TaxReturnVintage&gt;](TaxReturnVintage.md) | Optional | The deemed-disposal vintages, one per period, that feed line D. |
| **Instalments** | [List&lt;TaxReturnSpreadInstalment&gt;](TaxReturnSpreadInstalment.md) | Optional | The instalments of earlier vintages that fall into the period. |
| **LineDTotal** | **decimal** | Optional | The total of line D, in whole pounds. |
| **LoanRelationships** | [List&lt;TaxReturnLoanRelationshipRow&gt;](TaxReturnLoanRelationshipRow.md) | Optional | The loan relationship and derivative holdings that make up line LR. Empty for a fund. |
| **LineLRTotal** | **decimal** | Optional | The total of line LR, in whole pounds. Zero for a fund. |
| **Outside** | [List&lt;TaxReturnExcludedRow&gt;](TaxReturnExcludedRow.md) | Optional | The holdings excluded from the return, with the reason. |
| **Summary** | [List&lt;TaxReturnMemoRow&gt;](TaxReturnMemoRow.md) | Optional | Memo rows such as the tax at the applicable rate and the minimum-profits trade profit. |
| **SyncBreakOpen** | **bool** | Optional | True when the tax records are out of sync with the ledger and the return cannot advance past Reviewed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnResponse(
    fundId: new ResourceId(...),  // optional
    period: new TaxAccountingPeriod(...),  // optional
    status: "...",  // optional — The workflow status of the return. Available values: Draft, Prepared, Reviewed, SignedOff, Final. Available values: Draft, Prepared, Reviewed, SignedOff, Final.
    steps: new List<TaxReturnWorkflowStep>(),  // optional — The workflow history of the return in the order the steps were taken.
    lineA: new List<TaxReturnDisposalRow>(),  // optional — Chargeable gains and allowable losses on actual disposals in the period.
    lineATotal: 0.0d,  // optional — The total of line A, in whole pounds.
    vintages: new List<TaxReturnVintage>(),  // optional — The deemed-disposal vintages, one per period, that feed line D.
    instalments: new List<TaxReturnSpreadInstalment>(),  // optional — The instalments of earlier vintages that fall into the period.
    lineDTotal: 0.0d,  // optional — The total of line D, in whole pounds.
    loanRelationships: new List<TaxReturnLoanRelationshipRow>(),  // optional — The loan relationship and derivative holdings that make up line LR. Empty for a fund.
    lineLRTotal: 0.0d,  // optional — The total of line LR, in whole pounds. Zero for a fund.
    outside: new List<TaxReturnExcludedRow>(),  // optional — The holdings excluded from the return, with the reason.
    summary: new List<TaxReturnMemoRow>(),  // optional — Memo rows such as the tax at the applicable rate and the minimum-profits trade profit.
    syncBreakOpen: true  // optional — True when the tax records are out of sync with the ledger and the return cannot advance past Reviewed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [TaxAccountingPeriod](TaxAccountingPeriod.md)
- [TaxReturnWorkflowStep](TaxReturnWorkflowStep.md) — used in `Steps`
- [TaxReturnDisposalRow](TaxReturnDisposalRow.md) — used in `LineA`
- [TaxReturnVintage](TaxReturnVintage.md) — used in `Vintages`
- [TaxReturnSpreadInstalment](TaxReturnSpreadInstalment.md) — used in `Instalments`
- [TaxReturnLoanRelationshipRow](TaxReturnLoanRelationshipRow.md) — used in `LoanRelationships`
- [TaxReturnExcludedRow](TaxReturnExcludedRow.md) — used in `Outside`
- [TaxReturnMemoRow](TaxReturnMemoRow.md) — used in `Summary`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

