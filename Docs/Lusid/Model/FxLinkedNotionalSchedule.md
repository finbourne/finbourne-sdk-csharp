# Finbourne.Sdk.Lusid.Model.FxLinkedNotionalSchedule

Schedule for notional changes based on the change in FX rate.  Used in the representation of a resettable cross currency interest rate swap.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FxConventions** | [FxConventions](FxConventions.md) | Required | *No description available.* |
| **VaryingNotionalCurrency** | **string** | Required | The currency of the varying notional amount. |
| **VaryingNotionalFixingDates** | [RelativeDateOffset](RelativeDateOffset.md) | Required | *No description available.* |
| **VaryingNotionalInterimExchangePaymentDates** | [RelativeDateOffset](RelativeDateOffset.md) | Optional | *No description available.* |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.FxLinkedNotionalSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxLinkedNotionalSchedule(
    fxConventions: new FxConventions(...),  // required
    varyingNotionalCurrency: "...",  // required — The currency of the varying notional amount.
    varyingNotionalFixingDates: new RelativeDateOffset(...),  // required
    varyingNotionalInterimExchangePaymentDates: new RelativeDateOffset(...),  // optional
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxLinkedNotionalSchedule>(json);
```



- [FxConventions](FxConventions.md)
- [RelativeDateOffset](RelativeDateOffset.md)
- [RelativeDateOffset](RelativeDateOffset.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

