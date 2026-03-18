# Finbourne.Sdk.Lusid.Model.QuoteActivity

> **Inherits from:** [NavActivityAdjustment](NavActivityAdjustment.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The EffectiveAt time of the quote event that need to be added to the closed period. |
| **EntityUniqueId** | **string** | Required | The EntityUniqueId from the quote which needs to be added as a post close activity. |
| **InstrumentId** | **string** | Required | The InstrumentId from the quote which needs to be added as a post close activity. |
| **NavActivityAdjustmentType** | **string** | Required | . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity Default: `NavActivityAdjustmentTypeEnum.QuoteActivity` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QuoteActivity(
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    effectiveAt: new DateTimeOrCutLabel(...),  // required — The EffectiveAt time of the quote event that need to be added to the closed period.
    entityUniqueId: "...",  // required — The EntityUniqueId from the quote which needs to be added as a post close activity.
    instrumentId: "...",  // required — The InstrumentId from the quote which needs to be added as a post close activity.
    navActivityAdjustmentType: "..."  // required — . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QuoteActivity>(json);
```


- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

