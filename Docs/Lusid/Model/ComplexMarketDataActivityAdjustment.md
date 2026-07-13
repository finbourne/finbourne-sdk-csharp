# Finbourne.Sdk.Lusid.Model.ComplexMarketDataActivityAdjustment

> **Inherits from:** [NavActivityAdjustmentResponse](NavActivityAdjustmentResponse.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NavActivityAdjustmentSource** | **string** | Required | The post closed activity source of the given entity, for example Manual. Available values: Undefined, Manual, Auto. |
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The EffectiveAt time of the entity event that need to be added to the closed period. |
| **EntityUniqueId** | **string** | Required | The EntityUniqueId from the entity which needs to be added as a post close activity. |
| **NavActivityAdjustmentType** | **string** | Required | The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransactionAdjustment, PortfolioSettlementInstructionAdjustment, InstrumentActivityAdjustment, QuoteActivityAdjustment, ComplexMarketDataActivityAdjustment. Default: `NavActivityAdjustmentTypeEnum.ComplexMarketDataActivityAdjustment` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplexMarketDataActivityAdjustment(
    navActivityAdjustmentSource: "...",  // required — The post closed activity source of the given entity, for example Manual. Available values: Undefined, Manual, Auto.
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    effectiveAt: new DateTimeOrCutLabel(...),  // required — The EffectiveAt time of the entity event that need to be added to the closed period.
    entityUniqueId: "...",  // required — The EntityUniqueId from the entity which needs to be added as a post close activity.
    navActivityAdjustmentType: "..."  // required — The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransactionAdjustment, PortfolioSettlementInstructionAdjustment, InstrumentActivityAdjustment, QuoteActivityAdjustment, ComplexMarketDataActivityAdjustment.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplexMarketDataActivityAdjustment>(json);
```


- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

