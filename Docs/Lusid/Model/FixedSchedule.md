# Finbourne.Sdk.Lusid.Model.FixedSchedule

Schedule for fixed coupon payments
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | Date from which LUSID starts generating the payment schedule. |
| **MaturityDate** | **DateTimeOffset** | Required | Last date of the payment generation schedule. May not necessarily be the maturity date  of the underlying instrument (e.g. in case the instrument has multiple payment schedules). |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **CouponRate** | **decimal** | Optional | Coupon rate given as a fraction. |
| **ConventionName** | [FlowConventionName](FlowConventionName.md) | Optional | *No description available.* |
| **ExDividendDays** | **int?** | Optional | Optional. Number of calendar days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, then there is no ex-dividend period.                NOTE: This field is deprecated.  If you wish to set the ExDividendDays on a bond, please use the ExDividendConfiguration. |
| **Notional** | **decimal** | Optional | Scaling factor, the quantity outstanding on which the rate will be paid. |
| **PaymentCurrency** | **string** | Required | Payment currency. This does not have to be the same as the nominal bond or observation/reset currency. |
| **StubType** | **string** | Optional | When a payment schedule doesn&#39;t have regular payment intervals just because of the  first and/or last coupons of the schedule, we call those irregular coupons stubs.  This configuration specifies what type of stub is used when building the schedule  Supported values are:  None &#x3D; this is a regular payment schedule with no stubs. DO NOT use it with irregular schedules or you will get incorrect and unexpected behaviour.  ShortFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is shorter than the regular payment period.  ShortBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is shorter than the regular payment period.  LongFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is longer than the regular payment period.  LongBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is longer than the regular payment period.  Both &#x3D; this is an irregular payment schedule where both the first and the last coupons are irregular, and the length of these periods is calculated based on the first coupon payment date that should have been explicitly set. |
| **ExDividendConfiguration** | [ExDividendConfiguration](ExDividendConfiguration.md) | Optional | *No description available.* |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.FixedSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FixedSchedule(
    startDate: DateTimeOffset.Now,  // required — Date from which LUSID starts generating the payment schedule.
    maturityDate: DateTimeOffset.Now,  // required — Last date of the payment generation schedule. May not necessarily be the maturity date  of the underlying instrument (e.g. in case the instrument has multiple payment schedules).
    flowConventions: new FlowConventions(...),  // optional
    couponRate: 0.0d,  // optional — Coupon rate given as a fraction.
    conventionName: new FlowConventionName(...),  // optional
    exDividendDays: 0,  // optional — Optional. Number of calendar days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, then there is no ex-dividend period.                NOTE: This field is deprecated.  If you wish to set the ExDividendDays on a bond, please use the ExDividendConfiguration.
    notional: 0.0d,  // optional — Scaling factor, the quantity outstanding on which the rate will be paid.
    paymentCurrency: "...",  // required — Payment currency. This does not have to be the same as the nominal bond or observation/reset currency.
    stubType: "...",  // optional — When a payment schedule doesn&#39;t have regular payment intervals just because of the  first and/or last coupons of the schedule, we call those irregular coupons stubs.  This configuration specifies what type of stub is used when building the schedule  Supported values are:  None &#x3D; this is a regular payment schedule with no stubs. DO NOT use it with irregular schedules or you will get incorrect and unexpected behaviour.  ShortFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is shorter than the regular payment period.  ShortBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is shorter than the regular payment period.  LongFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is longer than the regular payment period.  LongBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is longer than the regular payment period.  Both &#x3D; this is an irregular payment schedule where both the first and the last coupons are irregular, and the length of these periods is calculated based on the first coupon payment date that should have been explicitly set.
    exDividendConfiguration: new ExDividendConfiguration(...),  // optional
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FixedSchedule>(json);
```


- [FlowConventions](FlowConventions.md)
- [FlowConventionName](FlowConventionName.md)
- [ExDividendConfiguration](ExDividendConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

