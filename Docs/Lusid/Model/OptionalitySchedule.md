# Finbourne.Sdk.Lusid.Model.OptionalitySchedule

Optionality Schedule represents a class for creation of schedules for optionality (call, put)
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExerciseType** | **string** | Optional | The exercise type of the optionality schedule (American or European).  For American type, the bond is perpetually callable from a given exercise date until it matures, or the next date in the schedule.  For European type, the bond is only callable on a given exercise date.    Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set. |
| **OptionEntries** | [List&lt;OptionEntry&gt;](OptionEntry.md) | Optional | The dates at which the bond call/put may be actioned, and associated strikes. |
| **OptionType** | **string** | Optional | Type of optionality for the schedule.    Supported string (enumeration) values are: [Call, Put].  Defaults to \&quot;Call\&quot; if not set. |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.OptionalitySchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OptionalitySchedule(
    exerciseType: "...",  // optional — The exercise type of the optionality schedule (American or European).  For American type, the bond is perpetually callable from a given exercise date until it matures, or the next date in the schedule.  For European type, the bond is only callable on a given exercise date.    Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.
    optionEntries: new List<OptionEntry>(),  // optional — The dates at which the bond call/put may be actioned, and associated strikes.
    optionType: "...",  // optional — Type of optionality for the schedule.    Supported string (enumeration) values are: [Call, Put].  Defaults to \&quot;Call\&quot; if not set.
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionalitySchedule>(json);
```


- [OptionEntry](OptionEntry.md) — used in `OptionEntries`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

