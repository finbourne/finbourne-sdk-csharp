# Finbourne.Sdk.Lusid.Model.TransactionSettlementSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OverallStatus** | [CategorySettlementStatus](CategorySettlementStatus.md) | Required | *No description available.* |
| **StockStatus** | [CategorySettlementStatus](CategorySettlementStatus.md) | Required | *No description available.* |
| **CashStatus** | [CategorySettlementStatus](CategorySettlementStatus.md) | Required | *No description available.* |
| **DeferredCashReceiptStatus** | [CategorySettlementStatus](CategorySettlementStatus.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionSettlementSummary(
    overallStatus: new CategorySettlementStatus(...),  // required
    stockStatus: new CategorySettlementStatus(...),  // required
    cashStatus: new CategorySettlementStatus(...),  // required
    deferredCashReceiptStatus: new CategorySettlementStatus(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionSettlementSummary>(json);
```


## Related Models

- [CategorySettlementStatus](CategorySettlementStatus.md)
- [CategorySettlementStatus](CategorySettlementStatus.md)
- [CategorySettlementStatus](CategorySettlementStatus.md)
- [CategorySettlementStatus](CategorySettlementStatus.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

