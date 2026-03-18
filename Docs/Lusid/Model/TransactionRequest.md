# Finbourne.Sdk.Lusid.Model.TransactionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | The unique identifier of the transaction. |
| **Type** | **string** | Required | The type of the transaction, for example &#39;Buy&#39; or &#39;Sell&#39;. The transaction type must have been pre-configured using the System Configuration API. If not, this operation will succeed but you are not able to calculate holdings for the portfolio that include this transaction. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Required | A set of instrument identifiers that can resolve the transaction to a unique instrument. |
| **TransactionDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The date of the transaction. |
| **SettlementDate** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The settlement date of the transaction. |
| **Units** | **decimal** | Required | The number of units of the transacted instrument. |
| **TransactionPrice** | [TransactionPrice](TransactionPrice.md) | Optional | *No description available.* |
| **TotalConsideration** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **ExchangeRate** | **decimal?** | Optional | The exchange rate between the transaction and settlement currency (settlement currency being represented by TotalConsideration.Currency). For example, if the transaction currency is USD and the settlement currency is GBP, this would be the appropriate USD/GBP rate. |
| **TransactionCurrency** | **string** | Optional | The transaction currency. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | A list of unique transaction properties and associated values to store for the transaction. Each property must be from the &#39;Transaction&#39; domain. |
| **CounterpartyId** | **string** | Optional | The identifier for the counterparty of the transaction. |
| **Source** | **string** | Optional | The source of the transaction. This is used to look up the appropriate transaction group set in the transaction type configuration. |
| **OtcConfirmation** | [OtcConfirmation](OtcConfirmation.md) | Optional | *No description available.* |
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AllocationId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CustodianAccountId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TransactionGroupId** | **string** | Optional | The identifier for grouping economic events across multiple transactions |
| **StrategyTag** | [List&lt;Strategy&gt;](Strategy.md) | Optional | A list of strategies representing the allocation of units across multiple sub-holding keys |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionRequest(
    transactionId: "...",  // required — The unique identifier of the transaction.
    type: "...",  // required — The type of the transaction, for example &#39;Buy&#39; or &#39;Sell&#39;. The transaction type must have been pre-configured using the System Configuration API. If not, this operation will succeed but you are not able to calculate holdings for the portfolio that include this transaction.
    instrumentIdentifiers: ,  // required — A set of instrument identifiers that can resolve the transaction to a unique instrument.
    transactionDate: new DateTimeOrCutLabel(...),  // required — The date of the transaction.
    settlementDate: new DateTimeOrCutLabel(...),  // required — The settlement date of the transaction.
    units: 0.0d,  // required — The number of units of the transacted instrument.
    transactionPrice: new TransactionPrice(...),  // optional
    totalConsideration: new CurrencyAndAmount(...),  // required
    exchangeRate: 0.0d,  // optional — The exchange rate between the transaction and settlement currency (settlement currency being represented by TotalConsideration.Currency). For example, if the transaction currency is USD and the settlement currency is GBP, this would be the appropriate USD/GBP rate.
    transactionCurrency: "...",  // optional — The transaction currency.
    properties: new PerpetualProperty(...),  // optional — A list of unique transaction properties and associated values to store for the transaction. Each property must be from the &#39;Transaction&#39; domain.
    counterpartyId: "...",  // optional — The identifier for the counterparty of the transaction.
    source: "...",  // optional — The source of the transaction. This is used to look up the appropriate transaction group set in the transaction type configuration.
    otcConfirmation: new OtcConfirmation(...),  // optional
    orderId: new ResourceId(...),  // optional
    allocationId: new ResourceId(...),  // optional
    custodianAccountId: new ResourceId(...),  // optional
    transactionGroupId: "...",  // optional — The identifier for grouping economic events across multiple transactions
    strategyTag: new List<Strategy>()  // optional — A list of strategies representing the allocation of units across multiple sub-holding keys
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionRequest>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `TransactionDate`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `SettlementDate`
- [TransactionPrice](TransactionPrice.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [OtcConfirmation](OtcConfirmation.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [Strategy](Strategy.md) — used in `StrategyTag`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

