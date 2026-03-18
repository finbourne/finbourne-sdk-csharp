# Finbourne.Sdk.Lusid.Model.InstrumentActivity

> **Inherits from:** [NavActivityAdjustment](NavActivityAdjustment.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAt** | **DateTimeOffset** | Required | The asAt time for which the adjustment is being applied. |
| **Scope** | **string** | Required | The Scope of the given entity |
| **LusidInstrumentId** | **string** | Required | The LusidInstrumentId of the given entity |
| **NavActivityAdjustmentType** | **string** | Required | . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity Default: `NavActivityAdjustmentTypeEnum.InstrumentActivity` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentActivity(
    asAt: DateTimeOffset.Now,  // required — The asAt time for which the adjustment is being applied.
    scope: "...",  // required — The Scope of the given entity
    lusidInstrumentId: "...",  // required — The LusidInstrumentId of the given entity
    navActivityAdjustmentType: "..."  // required — . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentActivity>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

