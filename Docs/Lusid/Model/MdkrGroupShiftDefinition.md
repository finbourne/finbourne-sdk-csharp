# Finbourne.Sdk.Lusid.Model.MdkrGroupShiftDefinition

A group of keyed market data key rules (e.g. bid/mid/ask). When the scenario is used in a  valuation, each key's rule re-resolves the matching market data dependencies independently and  produces its own result column named scenario:key, alongside the base column - which continues to  resolve through the recipe's own rules in the standard waterfall, whether or not the same rules  appear here.
> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Rules** | [List&lt;KeyedMarketDataKeyRule&gt;](KeyedMarketDataKeyRule.md) | Required | The keyed rules of the group. Keys must be unique within the group; each key produces one  result column. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition. Default: `ScenarioShiftTypeEnum.MdkrGroupShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MdkrGroupShiftDefinition(
    rules: new List<KeyedMarketDataKeyRule>(),  // required — The keyed rules of the group. Keys must be unique within the group; each key produces one  result column.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MdkrGroupShiftDefinition>(json);
```



- [KeyedMarketDataKeyRule](KeyedMarketDataKeyRule.md) — used in `Rules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

