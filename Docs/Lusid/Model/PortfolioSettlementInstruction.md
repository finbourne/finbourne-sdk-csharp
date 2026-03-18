# Finbourne.Sdk.Lusid.Model.PortfolioSettlementInstruction

> **Inherits from:** [NavActivityAdjustment](NavActivityAdjustment.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **PortfolioScope** | **string** | Required | The portfolio scope of the given entity |
| **PortfolioCode** | **string** | Required | The portfolio code of the given entity |
| **SettlementInstructionId** | **string** | Required | The settlement instruction Id of the SettlementInstruction being adjusted |
| **NavActivityAdjustmentType** | **string** | Required | . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity Default: `NavActivityAdjustmentTypeEnum.PortfolioSettlementInstruction` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioSettlementInstruction(
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    portfolioScope: "...",  // required — The portfolio scope of the given entity
    portfolioCode: "...",  // required — The portfolio code of the given entity
    settlementInstructionId: "...",  // required — The settlement instruction Id of the SettlementInstruction being adjusted
    navActivityAdjustmentType: "..."  // required — . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioSettlementInstruction>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

