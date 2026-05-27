# Finbourne.Sdk.Lusid.Model.NavSettlementConfigurationCategory

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CalculateInstructionToPortfolioRate** | **bool?** | Optional | An optional flag that allows for the calculation of the instruction to portfolio rate for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. |
| **CalculateTradeDateToSettlementFxPnL** | **bool?** | Optional | An optional flag that allows for the calculation of FxPnL between Trade and Settlement Date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NavSettlementConfigurationCategory(
    calculateInstructionToPortfolioRate: true,  // optional — An optional flag that allows for the calculation of the instruction to portfolio rate for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction.
    calculateTradeDateToSettlementFxPnL: true  // optional — An optional flag that allows for the calculation of FxPnL between Trade and Settlement Date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NavSettlementConfigurationCategory>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

