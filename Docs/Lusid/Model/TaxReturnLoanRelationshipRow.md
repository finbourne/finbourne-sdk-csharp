# Finbourne.Sdk.Lusid.Model.TaxReturnLoanRelationshipRow

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **HoldingId** | **string** | Optional | The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier. |
| **InstrumentId** | **string** | Optional | The LUSID unique identifier of the instrument. |
| **InstrumentName** | **string** | Optional | The name of the instrument. |
| **PortfolioCode** | **string** | Optional | The code of the portfolio the holding sits in, or the pooled marker for a company. |
| **LedgerAmount** | **decimal** | Optional | The loan relationship credit or debit recorded in the ledger. |
| **UpliftExcluded** | **decimal** | Optional | The uplift excluded from the loan relationship figure. |
| **NetCreditDebit** | **decimal** | Optional | The net loan relationship credit or debit, after the uplift is excluded. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxReturnLoanRelationshipRow(
    holdingId: "...",  // optional — The identifier of the holding. For a company this is the pooled LUSID instrument identifier, for a fund the portfolio code and instrument identifier.
    instrumentId: "...",  // optional — The LUSID unique identifier of the instrument.
    instrumentName: "...",  // optional — The name of the instrument.
    portfolioCode: "...",  // optional — The code of the portfolio the holding sits in, or the pooled marker for a company.
    ledgerAmount: 0.0d,  // optional — The loan relationship credit or debit recorded in the ledger.
    upliftExcluded: 0.0d,  // optional — The uplift excluded from the loan relationship figure.
    netCreditDebit: 0.0d  // optional — The net loan relationship credit or debit, after the uplift is excluded.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxReturnLoanRelationshipRow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

