# Finbourne.Sdk.Lusid.Model.PortfolioTransactionAdjustment

> **Inherits from:** [NavActivityAdjustmentResponse](NavActivityAdjustmentResponse.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NavActivityAdjustmentSource** | **string** | Required | The post closed activity source of the given entity, for example Manual. Available values: Undefined, Manual, Auto. |
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **PortfolioScope** | **string** | Required | The portfolio scope of the given entity |
| **PortfolioCode** | **string** | Required | The portfolio code of the given entity |
| **TransactionId** | **string** | Required | The transaction Id of the PortfolioTransaction being adjusted |
| **NavActivityAdjustmentType** | **string** | Required | The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransactionAdjustment, PortfolioSettlementInstructionAdjustment, InstrumentActivityAdjustment, QuoteActivityAdjustment. Default: `NavActivityAdjustmentTypeEnum.PortfolioTransactionAdjustment` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioTransactionAdjustment(
    navActivityAdjustmentSource: "...",  // required — The post closed activity source of the given entity, for example Manual. Available values: Undefined, Manual, Auto.
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    portfolioScope: "...",  // required — The portfolio scope of the given entity
    portfolioCode: "...",  // required — The portfolio code of the given entity
    transactionId: "...",  // required — The transaction Id of the PortfolioTransaction being adjusted
    navActivityAdjustmentType: "..."  // required — The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransactionAdjustment, PortfolioSettlementInstructionAdjustment, InstrumentActivityAdjustment, QuoteActivityAdjustment.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioTransactionAdjustment>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

