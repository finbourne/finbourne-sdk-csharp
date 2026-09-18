# Finbourne.Sdk.Lusid.Model.PortfolioTransactionDataset

Contains the run-time parameters that are appropriate for check definitions  with datasetSchema.type = \"PortfolioContents\" and datasetSchema.entityType = \"Transaction\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset?** | Optional | The asAt date to fetch the data. Nullable. Defaults to latest. |
| **FromEffectiveDate** | **DateTimeOffset?** | Optional | The earliest transaction date to check, inclusive. Nullable. Unbounded if not provided. |
| **ToEffectiveDate** | **DateTimeOffset?** | Optional | The latest transaction date to check, inclusive. Nullable — the window is unbounded above if not  provided. This value also resolves as the run&#39;s effectiveAt, so portfolios are resolved and transactions  decorated as of it; when not provided, that defaults to latest. Must be on or after fromEffectiveDate  when both are provided. |
| **PortfolioScope** | **string** | Optional | The scope of the portfolios whose transactions to check. Nullable. Every scope is checked if not provided. |
| **PortfolioSelectorAttribute** | **string** | Optional | An attribute (field name or propertyKey) to use to narrow down the portfolios whose transactions are  checked. Cannot be provided without portfolioSelectorValue, and vice versa. |
| **PortfolioSelectorValue** | **string** | Optional | The value of the above attribute used to narrow down the portfolios. Cannot be provided without  portfolioSelectorAttribute, and vice versa. |
| **TransactionSelectorAttribute** | **string** | Optional | An attribute (field name or propertyKey) to use to narrow down the transactions checked within those  portfolios. Cannot be provided without transactionSelectorValue, and vice versa. |
| **TransactionSelectorValue** | **string** | Optional | The value of the above attribute used to narrow down the transactions. Cannot be provided without  transactionSelectorAttribute, and vice versa. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioTransactionDataset(
    asAt: DateTimeOffset.Now,  // optional — The asAt date to fetch the data. Nullable. Defaults to latest.
    fromEffectiveDate: DateTimeOffset.Now,  // optional — The earliest transaction date to check, inclusive. Nullable. Unbounded if not provided.
    toEffectiveDate: DateTimeOffset.Now,  // optional — The latest transaction date to check, inclusive. Nullable — the window is unbounded above if not  provided. This value also resolves as the run&#39;s effectiveAt, so portfolios are resolved and transactions  decorated as of it; when not provided, that defaults to latest. Must be on or after fromEffectiveDate  when both are provided.
    portfolioScope: "...",  // optional — The scope of the portfolios whose transactions to check. Nullable. Every scope is checked if not provided.
    portfolioSelectorAttribute: "...",  // optional — An attribute (field name or propertyKey) to use to narrow down the portfolios whose transactions are  checked. Cannot be provided without portfolioSelectorValue, and vice versa.
    portfolioSelectorValue: "...",  // optional — The value of the above attribute used to narrow down the portfolios. Cannot be provided without  portfolioSelectorAttribute, and vice versa.
    transactionSelectorAttribute: "...",  // optional — An attribute (field name or propertyKey) to use to narrow down the transactions checked within those  portfolios. Cannot be provided without transactionSelectorValue, and vice versa.
    transactionSelectorValue: "..."  // optional — The value of the above attribute used to narrow down the transactions. Cannot be provided without  transactionSelectorAttribute, and vice versa.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioTransactionDataset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

