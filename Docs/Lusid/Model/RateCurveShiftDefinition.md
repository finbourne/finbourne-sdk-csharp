# Finbourne.Sdk.Lusid.Model.RateCurveShiftDefinition

> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Ccy** | **string** | Required | *No description available.* |
| **Amount** | **decimal** | Required | *No description available.* |
| **StartTenor** | **string** | Optional | *No description available.* |
| **EndTenor** | **string** | Optional | *No description available.* |
| **ShiftType** | **string** | Required | Available values: Parallel, Steepen, Flatten, Twist. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, EquityShiftDefinition, VolSurfaceShiftDefinition. Default: `ScenarioShiftTypeEnum.RateCurveShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RateCurveShiftDefinition(
    ccy: "...",  // required
    amount: 0.0d,  // required
    startTenor: "...",  // optional
    endTenor: "...",  // optional
    shiftType: "...",  // required — Available values: Parallel, Steepen, Flatten, Twist.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, EquityShiftDefinition, VolSurfaceShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RateCurveShiftDefinition>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

