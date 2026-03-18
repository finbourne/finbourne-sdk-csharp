# Finbourne.Sdk.Lusid.Model.PortfolioSettlementConfiguration

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StockSettlement** | [SettlementConfigurationCategory](SettlementConfigurationCategory.md) | Optional | *No description available.* |
| **CashSettlement** | [SettlementConfigurationCategory](SettlementConfigurationCategory.md) | Optional | *No description available.* |
| **DeferredCashReceipt** | [SettlementConfigurationCategory](SettlementConfigurationCategory.md) | Optional | *No description available.* |
| **TransactionMatchingAlternativeId** | [TransactionMatchingAlternativeId](TransactionMatchingAlternativeId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioSettlementConfiguration(
    stockSettlement: new SettlementConfigurationCategory(...),  // optional
    cashSettlement: new SettlementConfigurationCategory(...),  // optional
    deferredCashReceipt: new SettlementConfigurationCategory(...),  // optional
    transactionMatchingAlternativeId: new TransactionMatchingAlternativeId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioSettlementConfiguration>(json);
```


## Related Models

- [SettlementConfigurationCategory](SettlementConfigurationCategory.md)
- [SettlementConfigurationCategory](SettlementConfigurationCategory.md)
- [SettlementConfigurationCategory](SettlementConfigurationCategory.md)
- [TransactionMatchingAlternativeId](TransactionMatchingAlternativeId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

