# Finbourne.Sdk.Lusid.Model.InstrumentEventActivity

> **Inherits from:** [NavActivityAdjustment](NavActivityAdjustment.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **CorporateActionSourceScope** | **string** | Required | The scope of the corporate action source that the instrument event belongs to. |
| **CorporateActionSourceCode** | **string** | Required | The code of the corporate action source that the instrument event belongs to. |
| **InstrumentEventId** | **string** | Required | The Id of the instrument event being adjusted. |
| **NavActivityAdjustmentType** | **string** | Required | The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity, ComplexMarketDataActivity, InstrumentEventActivity. Default: `NavActivityAdjustmentTypeEnum.InstrumentEventActivity` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentEventActivity(
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    corporateActionSourceScope: "...",  // required — The scope of the corporate action source that the instrument event belongs to.
    corporateActionSourceCode: "...",  // required — The code of the corporate action source that the instrument event belongs to.
    instrumentEventId: "...",  // required — The Id of the instrument event being adjusted.
    navActivityAdjustmentType: "..."  // required — The type of the entity being applied, for example a PortfolioTransaction. Available values: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity, ComplexMarketDataActivity, InstrumentEventActivity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentEventActivity>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

