# Finbourne.Sdk.Lusid.Model.AccountedTransaction

The Valuation Point Data Response for the Fund and specified date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AccountingDate** | **DateTimeOffset** | Optional | The transaction&#39;s accounting date. |
| **JournalEntryAction** | **string** | Optional | The journal entry line action associated with this transaction. |
| **Transaction** | [OutputTransaction](OutputTransaction.md) | Optional | *No description available.* |
| **PortfolioId** | [PortfolioId](PortfolioId.md) | Optional | *No description available.* |
| **ValuationPointOrigin** | **string** | Optional | Designates if the transaction was originally part of the Valuation Point or if it was added as part of a Complex Close action. |
| **AddedOriginValuationPointCode** | **string** | Optional | The Valuation Point, only for transaction added as part of a Complex Close action. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccountedTransaction(
    accountingDate: DateTimeOffset.Now,  // optional — The transaction&#39;s accounting date.
    journalEntryAction: "...",  // optional — The journal entry line action associated with this transaction.
    transaction: new OutputTransaction(...),  // optional
    portfolioId: new PortfolioId(...),  // optional
    valuationPointOrigin: "...",  // optional — Designates if the transaction was originally part of the Valuation Point or if it was added as part of a Complex Close action.
    addedOriginValuationPointCode: "..."  // optional — The Valuation Point, only for transaction added as part of a Complex Close action.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccountedTransaction>(json);
```

- [OutputTransaction](OutputTransaction.md)
- [PortfolioId](PortfolioId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

