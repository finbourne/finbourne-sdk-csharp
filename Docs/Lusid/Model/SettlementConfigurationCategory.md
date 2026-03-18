# Finbourne.Sdk.Lusid.Model.SettlementConfigurationCategory

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Method** | **string** | Optional | The method of settlement for the movements of the relevant type(s). Allowed values: &#39;Automatic&#39; and &#39;Instructed&#39;. A value of &#39;Instructed&#39; means that such movements can only be settled with a SettlementInstruction. A value of &#39;Automatic&#39; means that such movements will settle automatically but a SettlementInstruction will still override automatic settlement. |
| **CalculateInstructionToPortfolioRate** | **bool** | Optional | An optional flag that allows for the calculation of the instruction to portfolio rate for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. Defaults to false if not specified. |
| **CalculateInLieuSettlementAmount** | **bool** | Optional | An optional flag that allows for the calculation of the in lieu amount for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. Defaults to false if not specified. |
| **MethodOverride** | [SettlementConfigurationMethodOverride](SettlementConfigurationMethodOverride.md) | Optional | *No description available.* |
| **CalculateTradeDateToSettlementFxPnL** | **bool** | Optional | An optional flag that allows for the calculation of the in lieu amount for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. Defaults to false if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementConfigurationCategory(
    method: "...",  // optional — The method of settlement for the movements of the relevant type(s). Allowed values: &#39;Automatic&#39; and &#39;Instructed&#39;. A value of &#39;Instructed&#39; means that such movements can only be settled with a SettlementInstruction. A value of &#39;Automatic&#39; means that such movements will settle automatically but a SettlementInstruction will still override automatic settlement.
    calculateInstructionToPortfolioRate: true,  // optional — An optional flag that allows for the calculation of the instruction to portfolio rate for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. Defaults to false if not specified.
    calculateInLieuSettlementAmount: true,  // optional — An optional flag that allows for the calculation of the in lieu amount for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. Defaults to false if not specified.
    methodOverride: new SettlementConfigurationMethodOverride(...),  // optional
    calculateTradeDateToSettlementFxPnL: true  // optional — An optional flag that allows for the calculation of the in lieu amount for instructions with settlement category CashSettlement or DeferredCashReceipt, if it is not provided on the settlement instruction. Defaults to false if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementConfigurationCategory>(json);
```

- [SettlementConfigurationMethodOverride](SettlementConfigurationMethodOverride.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

