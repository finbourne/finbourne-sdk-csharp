# Finbourne.Sdk.Lusid.Model.PikSchedule

A PikSchedule represents Payment-in-Kind features for a ComplexBond.  It works in conjunction with existing FixedSchedules or FloatSchedules to define  how interest is paid during duration of the schedule.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the PIK schedule period. |
| **MaturityDate** | **DateTimeOffset** | Required | The end date of the PIK schedule period. |
| **IsPikFractionElectable** | **bool** | Optional | If true, the PIK fraction is electable at each payment date.  Defaults to false. |
| **PikFraction** | **decimal?** | Optional | The fraction of the coupon that is paid in kind, where 0 means fully cash and 1 means fully PIK.  Required if IsPikFractionElectable is false or null. Must satisfy 0 &lt;&#x3D; pikFraction &lt;&#x3D; 1. |
| **PikPaymentType** | **string** | Optional | The type of PIK payment to be used for the duration of this schedule.  InterestCapitalisation adds the paid-in-kind portion to the bond&#39;s current face;  AdditionalSecurities settles it by delivering units of another instrument, named on each  period&#39;s PikBondInterestEvent; Electable leaves the choice to a per-period election.                Supported string (enumeration) values are: [Electable, InterestCapitalisation, AdditionalSecurities]. |
| **PikRate** | **decimal?** | Optional | The PIK interest rate. Must be greater than or equal to zero.  null indicates no override PIK interest rate. |
| **PikSpread** | **decimal?** | Optional | The PIK spread to be added to the base rate for the final PIK rate.  null indicates no spread on base rate. |
| **ScheduleType** | **string** | Required | Available values: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, PikSchedule, Invalid, CancelSchedule. Default: `ScheduleTypeEnum.PikSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PikSchedule(
    startDate: DateTimeOffset.Now,  // required — The start date of the PIK schedule period.
    maturityDate: DateTimeOffset.Now,  // required — The end date of the PIK schedule period.
    isPikFractionElectable: true,  // optional — If true, the PIK fraction is electable at each payment date.  Defaults to false.
    pikFraction: 0.0d,  // optional — The fraction of the coupon that is paid in kind, where 0 means fully cash and 1 means fully PIK.  Required if IsPikFractionElectable is false or null. Must satisfy 0 &lt;&#x3D; pikFraction &lt;&#x3D; 1.
    pikPaymentType: "...",  // optional — The type of PIK payment to be used for the duration of this schedule.  InterestCapitalisation adds the paid-in-kind portion to the bond&#39;s current face;  AdditionalSecurities settles it by delivering units of another instrument, named on each  period&#39;s PikBondInterestEvent; Electable leaves the choice to a per-period election.                Supported string (enumeration) values are: [Electable, InterestCapitalisation, AdditionalSecurities].
    pikRate: 0.0d,  // optional — The PIK interest rate. Must be greater than or equal to zero.  null indicates no override PIK interest rate.
    pikSpread: 0.0d,  // optional — The PIK spread to be added to the base rate for the final PIK rate.  null indicates no spread on base rate.
    scheduleType: "..."  // required — Available values: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, PikSchedule, Invalid, CancelSchedule.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PikSchedule>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

