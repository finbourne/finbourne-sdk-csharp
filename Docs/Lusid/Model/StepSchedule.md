# Finbourne.Sdk.Lusid.Model.StepSchedule

Schedule that steps at known dated points in time.  Used in representation of a sinking bond, also called amortisation, steps in coupons for fixed bonds and spreads for floating bonds.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LevelType** | **string** | Required | The type of shift or adjustment that the quantity represents.    Supported string (enumeration) values are: [Absolute, AbsoluteShift, Percentage, AbsolutePercentage]. |
| **StepScheduleType** | **string** | Required | The type of step that this schedule is for.  Supported string (enumeration) values are: [Coupon, Notional, Spread]. |
| **Steps** | [List&lt;LevelStep&gt;](LevelStep.md) | Required | The level steps which are applied. |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.StepSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StepSchedule(
    levelType: "...",  // required — The type of shift or adjustment that the quantity represents.    Supported string (enumeration) values are: [Absolute, AbsoluteShift, Percentage, AbsolutePercentage].
    stepScheduleType: "...",  // required — The type of step that this schedule is for.  Supported string (enumeration) values are: [Coupon, Notional, Spread].
    steps: new List<LevelStep>(),  // required — The level steps which are applied.
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StepSchedule>(json);
```


- [LevelStep](LevelStep.md) — used in `Steps`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

