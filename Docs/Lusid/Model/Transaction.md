# Finbourne.Sdk.Lusid.Model.Transaction

A list of transactions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | The unique identifier for the transaction. |
| **Type** | **string** | Required | The type of the transaction e.g. &#39;Buy&#39;, &#39;Sell&#39;. The transaction type should have been pre-configured via the System Configuration API endpoint. |
| **InstrumentIdentifiers** | **Dictionary&lt;string, string&gt;** | Optional | A set of instrument identifiers that can resolve the transaction to a unique instrument. |
| **InstrumentScope** | **string** | Optional | The scope in which the transaction&#39;s instrument lies. |
| **InstrumentUid** | **string** | Required | The unique Lusid Instrument Id (LUID) of the instrument that the transaction is in. |
| **TransactionDate** | **DateTimeOffset** | Required | The date of the transaction. |
| **SettlementDate** | **DateTimeOffset** | Required | The settlement date of the transaction. |
| **Units** | **decimal** | Required | The number of units transacted in the associated instrument. |
| **TransactionPrice** | [TransactionPrice](TransactionPrice.md) | Optional | *No description available.* |
| **TotalConsideration** | [CurrencyAndAmount](CurrencyAndAmount.md) | Required | *No description available.* |
| **ExchangeRate** | **decimal?** | Optional | The exchange rate between the transaction and settlement currency (settlement currency being represented by the TotalConsideration.Currency). For example if the transaction currency is in USD and the settlement currency is in GBP this this the USD/GBP rate. |
| **TransactionCurrency** | **string** | Optional | The transaction currency. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Set of unique transaction properties and associated values to stored with the transaction. Each property will be from the &#39;Transaction&#39; domain. |
| **CounterpartyId** | **string** | Optional | The identifier for the counterparty of the transaction. |
| **Source** | **string** | Optional | The source of the transaction. This is used to look up the appropriate transaction group set in the transaction type configuration. |
| **EntryDateTime** | **DateTimeOffset** | Optional | The asAt datetime that the transaction was added to LUSID. |
| **OtcConfirmation** | [OtcConfirmation](OtcConfirmation.md) | Optional | *No description available.* |
| **TransactionStatus** | **string** | Optional | The status of the transaction. The available values are: Active, Amended, Cancelled, ActiveReversal, ActiveTrueUp, CancelledTrueUp |
| **CancelDateTime** | **DateTimeOffset?** | Optional | If the transaction has been cancelled, the asAt datetime that the transaction was cancelled. |
| **OrderId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AllocationId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CustodianAccount** | [CustodianAccount](CustodianAccount.md) | Optional | *No description available.* |
| **TransactionGroupId** | **string** | Optional | The identifier for grouping economic events across multiple transactions |
| **StrategyTag** | [List&lt;Strategy&gt;](Strategy.md) | Optional | A list of strategies representing the allocation of units across multiple sub-holding keys |
| **ResolvedTransactionTypeDetails** | [TransactionTypeDetails](TransactionTypeDetails.md) | Optional | *No description available.* |
| **DataModelMembership** | [DataModelMembership](DataModelMembership.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Transaction(
    transactionId: "...",  // required — The unique identifier for the transaction.
    type: "...",  // required — The type of the transaction e.g. &#39;Buy&#39;, &#39;Sell&#39;. The transaction type should have been pre-configured via the System Configuration API endpoint.
    instrumentIdentifiers: ,  // optional — A set of instrument identifiers that can resolve the transaction to a unique instrument.
    instrumentScope: "...",  // optional — The scope in which the transaction&#39;s instrument lies.
    instrumentUid: "...",  // required — The unique Lusid Instrument Id (LUID) of the instrument that the transaction is in.
    transactionDate: DateTimeOffset.Now,  // required — The date of the transaction.
    settlementDate: DateTimeOffset.Now,  // required — The settlement date of the transaction.
    units: 0.0d,  // required — The number of units transacted in the associated instrument.
    transactionPrice: new TransactionPrice(...),  // optional
    totalConsideration: new CurrencyAndAmount(...),  // required
    exchangeRate: 0.0d,  // optional — The exchange rate between the transaction and settlement currency (settlement currency being represented by the TotalConsideration.Currency). For example if the transaction currency is in USD and the settlement currency is in GBP this this the USD/GBP rate.
    transactionCurrency: "...",  // optional — The transaction currency.
    properties: new PerpetualProperty(...),  // optional — Set of unique transaction properties and associated values to stored with the transaction. Each property will be from the &#39;Transaction&#39; domain.
    counterpartyId: "...",  // optional — The identifier for the counterparty of the transaction.
    source: "...",  // optional — The source of the transaction. This is used to look up the appropriate transaction group set in the transaction type configuration.
    entryDateTime: DateTimeOffset.Now,  // optional — The asAt datetime that the transaction was added to LUSID.
    otcConfirmation: new OtcConfirmation(...),  // optional
    transactionStatus: "...",  // optional — The status of the transaction. The available values are: Active, Amended, Cancelled, ActiveReversal, ActiveTrueUp, CancelledTrueUp
    cancelDateTime: DateTimeOffset.Now,  // optional — If the transaction has been cancelled, the asAt datetime that the transaction was cancelled.
    orderId: new ResourceId(...),  // optional
    allocationId: new ResourceId(...),  // optional
    custodianAccount: new CustodianAccount(...),  // optional
    transactionGroupId: "...",  // optional — The identifier for grouping economic events across multiple transactions
    strategyTag: new List<Strategy>(),  // optional — A list of strategies representing the allocation of units across multiple sub-holding keys
    resolvedTransactionTypeDetails: new TransactionTypeDetails(...),  // optional
    dataModelMembership: new DataModelMembership(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Transaction>(json);
```

- [TransactionPrice](TransactionPrice.md)
- [CurrencyAndAmount](CurrencyAndAmount.md)
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`
- [OtcConfirmation](OtcConfirmation.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [CustodianAccount](CustodianAccount.md)
- [Strategy](Strategy.md) — used in `StrategyTag`
- [TransactionTypeDetails](TransactionTypeDetails.md)
- [DataModelMembership](DataModelMembership.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

