# Finbourne.Sdk.Lusid.Model.PortfolioTransactionResult

Represents transaction details for a data quality check result.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Optional | The type of the entity. Always \&quot;Transaction\&quot;. |
| **TransactionView** | **string** | Optional | Whether this is an input or an output transaction |
| **AsAt** | **DateTimeOffset** | Optional | The as-at timestamp for the transaction |
| **TransactionDate** | **DateTimeOffset** | Optional | The transaction date |
| **TransactionId** | **string** | Optional | The transaction&#39;s identifier within its portfolio |
| **EntityUniqueId** | **string** | Optional | The transaction&#39;s unique identifier across portfolios |
| **SourcePortfolioScope** | **string** | Optional | The scope of the portfolio this transaction came from |
| **SourcePortfolioCode** | **string** | Optional | The code of the portfolio this transaction came from |
| **SourcePortfolioEntityUniqueId** | **string** | Optional | The unique identifier of the portfolio this transaction came from |
| **SourcePortfolioDisplayName** | **string** | Optional | The display name of the portfolio this transaction came from |
| **LusidInstrumentId** | **string** | Optional | The LUSID instrument identifier of the instrument transacted |
| **InstrumentDisplayName** | **string** | Optional | The name of the instrument transacted |
| **TransactionType** | **string** | Optional | The transaction type, e.g. Buy, Sell |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioTransactionResult(
    entityType: "...",  // optional — The type of the entity. Always \&quot;Transaction\&quot;.
    transactionView: "...",  // optional — Whether this is an input or an output transaction
    asAt: DateTimeOffset.Now,  // optional — The as-at timestamp for the transaction
    transactionDate: DateTimeOffset.Now,  // optional — The transaction date
    transactionId: "...",  // optional — The transaction&#39;s identifier within its portfolio
    entityUniqueId: "...",  // optional — The transaction&#39;s unique identifier across portfolios
    sourcePortfolioScope: "...",  // optional — The scope of the portfolio this transaction came from
    sourcePortfolioCode: "...",  // optional — The code of the portfolio this transaction came from
    sourcePortfolioEntityUniqueId: "...",  // optional — The unique identifier of the portfolio this transaction came from
    sourcePortfolioDisplayName: "...",  // optional — The display name of the portfolio this transaction came from
    lusidInstrumentId: "...",  // optional — The LUSID instrument identifier of the instrument transacted
    instrumentDisplayName: "...",  // optional — The name of the instrument transacted
    transactionType: "..."  // optional — The transaction type, e.g. Buy, Sell
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioTransactionResult>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

