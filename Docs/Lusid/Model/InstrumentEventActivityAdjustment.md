# Finbourne.Sdk.Lusid.Model.InstrumentEventActivityAdjustment

> **Inherits from:** [NavActivityAdjustmentResponse](NavActivityAdjustmentResponse.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NavActivityAdjustmentSource** | **string** | Required | The post closed activity source of the given entity, for example Manual. Available values: Undefined, Manual, Auto. |
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **CorporateActionSourceScope** | **string** | Required | The scope of the corporate action source that the instrument event belongs to. |
| **CorporateActionSourceCode** | **string** | Required | The code of the corporate action source that the instrument event belongs to. |
| **InstrumentEventId** | **string** | Required | The Id of the instrument event being adjusted. |
| **NavActivityAdjustmentType** | **string** | Required | The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransactionAdjustment, PortfolioSettlementInstructionAdjustment, InstrumentActivityAdjustment, QuoteActivityAdjustment, ComplexMarketDataActivityAdjustment, InstrumentEventActivityAdjustment. Default: `NavActivityAdjustmentTypeEnum.InstrumentEventActivityAdjustment` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventActivityAdjustment(
    navActivityAdjustmentSource: "...",  // required — The post closed activity source of the given entity, for example Manual. Available values: Undefined, Manual, Auto.
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    corporateActionSourceScope: "...",  // required — The scope of the corporate action source that the instrument event belongs to.
    corporateActionSourceCode: "...",  // required — The code of the corporate action source that the instrument event belongs to.
    instrumentEventId: "...",  // required — The Id of the instrument event being adjusted.
    navActivityAdjustmentType: "..."  // required — The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransactionAdjustment, PortfolioSettlementInstructionAdjustment, InstrumentActivityAdjustment, QuoteActivityAdjustment, ComplexMarketDataActivityAdjustment, InstrumentEventActivityAdjustment.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventActivityAdjustment>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

