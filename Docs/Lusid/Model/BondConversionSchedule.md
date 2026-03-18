# Finbourne.Sdk.Lusid.Model.BondConversionSchedule

A BondConversionSchedule object represents a class containing the  information required for the creation of convertible features in a ComplexBond
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | The market identifier(s) of the share that the bond converts to. The instrument  will not fail validation if no identifier is supplied. |
| **BondConversionEntries** | [List&lt;BondConversionEntry&gt;](BondConversionEntry.md) | Optional | The dates at which the bond may be converted and associated information required about the conversion. |
| **ConversionTrigger** | **string** | Required | Corporate event that triggers a conversion    Supported string (enumeration) values are: [NextEquityFinancing, IpoConversion, KnownDates, SoftCall]. |
| **DeliveryType** | **string** | Optional | Is a conversion made into cash or into shares?  Defaults to \&quot;Physical\&quot; if not set.    Supported string (enumeration) values are: [Cash, Physical]. |
| **ExerciseType** | **string** | Required | The exercise type of the conversion schedule (American or European).  For American type, the bond is convertible from a given exercise date until the next date in the schedule, or until it matures.  For European type, the bond is only convertible on the given exercise date.    Supported string (enumeration) values are: [European, Bermudan, American]. |
| **IncludesAccrued** | **bool** | Optional | Set this to true if a accrued interest is included in the conversion. Defaults to true. |
| **MandatoryConversion** | **bool** | Optional | Set this to true if a conversion is mandatory if the trigger occurs. Defaults to false. |
| **NotificationPeriodEnd** | **DateTimeOffset** | Optional | The last day in the notification period for the conversion of the bond |
| **NotificationPeriodStart** | **DateTimeOffset** | Optional | The first day in the notification period for the conversion of the bond |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.BondConversionSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondConversionSchedule(
    identifiers: ,  // optional — The market identifier(s) of the share that the bond converts to. The instrument  will not fail validation if no identifier is supplied.
    bondConversionEntries: new List<BondConversionEntry>(),  // optional — The dates at which the bond may be converted and associated information required about the conversion.
    conversionTrigger: "...",  // required — Corporate event that triggers a conversion    Supported string (enumeration) values are: [NextEquityFinancing, IpoConversion, KnownDates, SoftCall].
    deliveryType: "...",  // optional — Is a conversion made into cash or into shares?  Defaults to \&quot;Physical\&quot; if not set.    Supported string (enumeration) values are: [Cash, Physical].
    exerciseType: "...",  // required — The exercise type of the conversion schedule (American or European).  For American type, the bond is convertible from a given exercise date until the next date in the schedule, or until it matures.  For European type, the bond is only convertible on the given exercise date.    Supported string (enumeration) values are: [European, Bermudan, American].
    includesAccrued: true,  // optional — Set this to true if a accrued interest is included in the conversion. Defaults to true.
    mandatoryConversion: true,  // optional — Set this to true if a conversion is mandatory if the trigger occurs. Defaults to false.
    notificationPeriodEnd: DateTimeOffset.Now,  // optional — The last day in the notification period for the conversion of the bond
    notificationPeriodStart: DateTimeOffset.Now,  // optional — The first day in the notification period for the conversion of the bond
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondConversionSchedule>(json);
```


- [BondConversionEntry](BondConversionEntry.md) — used in `BondConversionEntries`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

