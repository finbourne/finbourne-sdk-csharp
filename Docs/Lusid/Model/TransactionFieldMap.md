# Finbourne.Sdk.Lusid.Model.TransactionFieldMap

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransactionId** | **string** | Required | *No description available.* |
| **Type** | **string** | Required | *No description available.* |
| **Source** | **string** | Required | *No description available.* |
| **Instrument** | **string** | Required | *No description available.* |
| **TransactionDate** | **string** | Required | *No description available.* |
| **SettlementDate** | **string** | Required | *No description available.* |
| **Units** | **string** | Required | *No description available.* |
| **TransactionPrice** | [TransactionPriceAndType](TransactionPriceAndType.md) | Optional | *No description available.* |
| **TransactionCurrency** | **string** | Required | *No description available.* |
| **ExchangeRate** | **string** | Optional | *No description available.* |
| **TotalConsideration** | [TransactionCurrencyAndAmount](TransactionCurrencyAndAmount.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionFieldMap(
    transactionId: "...",  // required
    type: "...",  // required
    source: "...",  // required
    instrument: "...",  // required
    transactionDate: "...",  // required
    settlementDate: "...",  // required
    units: "...",  // required
    transactionPrice: new TransactionPriceAndType(...),  // optional
    transactionCurrency: "...",  // required
    exchangeRate: "...",  // optional
    totalConsideration: new TransactionCurrencyAndAmount(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionFieldMap>(json);
```

- [TransactionPriceAndType](TransactionPriceAndType.md)
- [TransactionCurrencyAndAmount](TransactionCurrencyAndAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

