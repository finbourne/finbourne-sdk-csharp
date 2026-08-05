# Finbourne.Sdk.Lusid.Model.VolSurfaceShiftDefinition

> **Inherits from:** [ScenarioShiftDefinition](ScenarioShiftDefinition.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Instrument** | **string** | Required | *No description available.* |
| **Amount** | **decimal** | Required | *No description available.* |
| **Strike** | **decimal?** | Optional | *No description available.* |
| **Expiry** | **string** | Optional | *No description available.* |
| **ShiftType** | **string** | Required | Available values: Absolute, Relative. |
| **ScenarioShiftType** | **string** | Required | Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition. Default: `ScenarioShiftTypeEnum.VolSurfaceShiftDefinition` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VolSurfaceShiftDefinition(
    instrument: "...",  // required
    amount: 0.0d,  // required
    strike: 0.0d,  // optional
    expiry: "...",  // optional
    shiftType: "...",  // required — Available values: Absolute, Relative.
    scenarioShiftType: "..."  // required — Available values: RateCurveShiftDefinition, FxShiftDefinition, PriceShiftDefinition, VolSurfaceShiftDefinition, MdkrGroupShiftDefinition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VolSurfaceShiftDefinition>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

