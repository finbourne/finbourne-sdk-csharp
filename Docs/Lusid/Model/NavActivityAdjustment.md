# Finbourne.Sdk.Lusid.Model.NavActivityAdjustment

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NavActivityAdjustmentType** | **string** | Required | . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NavActivityAdjustment(
    navActivityAdjustmentType: "..."  // required — . The available values are: PortfolioTransaction, PortfolioSettlementInstruction, InstrumentActivity, QuoteActivity
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NavActivityAdjustment>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

