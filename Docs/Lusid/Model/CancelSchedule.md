# Finbourne.Sdk.Lusid.Model.CancelSchedule

Cancel schedule represents the embedded option on a cancellable swap, allowing one party to  terminate the swap on one or more predefined dates.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CancelDates** | **List&lt;DateTimeOffset&gt;** | Required | The dates on which cancellation may be elected. |
| **CancelType** | **string** | Required | The type of cancellation option: European (single cancel date) or Bermudan (two or more).                Supported string (enumeration) values are: [European, Bermudan]. Available values: European, Bermudan. |
| **NoticeConvention** | [NoticeConvention](NoticeConvention.md) | Required | *No description available.* |
| **ScheduleType** | **string** | Required | Available values: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, PikSchedule, Invalid, CancelSchedule. Default: `ScheduleTypeEnum.CancelSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CancelSchedule(
    cancelDates: ,  // required — The dates on which cancellation may be elected.
    cancelType: "...",  // required — The type of cancellation option: European (single cancel date) or Bermudan (two or more).                Supported string (enumeration) values are: [European, Bermudan]. Available values: European, Bermudan.
    noticeConvention: new NoticeConvention(...),  // required
    scheduleType: "..."  // required — Available values: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, PikSchedule, Invalid, CancelSchedule.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CancelSchedule>(json);
```


- [NoticeConvention](NoticeConvention.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

