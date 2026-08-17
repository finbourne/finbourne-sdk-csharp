# Finbourne.Sdk.Lusid.Model.CommodityCalendarSchedule

Schedule describing the periodic calendar-average settlement periods of a commodity calendar swap.  Each period settles in cash against the average of the observed commodity price over the period.  The schedule is currently stored and validated only; period expansion is not yet implemented.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Optional | The date from which the first settlement period accrues. |
| **MaturityDate** | **DateTimeOffset** | Optional | The date on which the final settlement period ends. |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **PaymentCurrency** | **string** | Optional | The currency in which each periodic cash settlement is paid. |
| **StubType** | **string** | Optional | How any non-integral first or last period is handled when generating the settlement periods.  If not specified, this defaults to None.                Supported string (enumeration) values are: [ShortFront, ShortBack, LongBack, LongFront, Both]. Available values: None, ShortFront, ShortBack, LongBack, LongFront, Both, Invalid. |
| **ScheduleType** | **string** | Required | Available values: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, PikSchedule, CommodityCalendarSchedule, Invalid, CancelSchedule. Default: `ScheduleTypeEnum.CommodityCalendarSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CommodityCalendarSchedule(
    startDate: DateTimeOffset.Now,  // optional — The date from which the first settlement period accrues.
    maturityDate: DateTimeOffset.Now,  // optional — The date on which the final settlement period ends.
    flowConventions: new FlowConventions(...),  // optional
    paymentCurrency: "...",  // optional — The currency in which each periodic cash settlement is paid.
    stubType: "...",  // optional — How any non-integral first or last period is handled when generating the settlement periods.  If not specified, this defaults to None.                Supported string (enumeration) values are: [ShortFront, ShortBack, LongBack, LongFront, Both]. Available values: None, ShortFront, ShortBack, LongBack, LongFront, Both, Invalid.
    scheduleType: "..."  // required — Available values: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, PikSchedule, CommodityCalendarSchedule, Invalid, CancelSchedule.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CommodityCalendarSchedule>(json);
```


- [FlowConventions](FlowConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

