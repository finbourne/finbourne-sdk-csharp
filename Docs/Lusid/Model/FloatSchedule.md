# Finbourne.Sdk.Lusid.Model.FloatSchedule

Schedule for floating rate coupon payments.
> **Inherits from:** [Schedule](Schedule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Optional | Date from which LUSID starts generating the payment schedule. |
| **MaturityDate** | **DateTimeOffset** | Optional | Last date of the payment generation schedule. May not necessarily be the maturity date  of the underlying instrument (e.g. in case the instrument has multiple payment schedules). |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **ConventionName** | [FlowConventionName](FlowConventionName.md) | Optional | *No description available.* |
| **ExDividendDays** | **int?** | Optional | Optional. Number of calendar days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, then there is no ex-dividend period.                NOTE: This field is deprecated.  If you wish to set the ExDividendDays on a bond, please use the ExDividendConfiguration. |
| **IndexConventionName** | [FlowConventionName](FlowConventionName.md) | Optional | *No description available.* |
| **IndexConventions** | [IndexConvention](IndexConvention.md) | Optional | *No description available.* |
| **Notional** | **decimal** | Optional | Scaling factor, the quantity outstanding on which the rate will be paid. |
| **PaymentCurrency** | **string** | Required | Payment currency. This does not have to be the same as the nominal bond or observation/reset currency. |
| **Spread** | **decimal** | Optional | Spread over floating rate given as a fraction. |
| **StubType** | **string** | Optional | When a payment schedule doesn&#39;t have regular payment intervals just because of the  first and/or last coupons of the schedule, we call those irregular coupons stubs.  This configuration specifies what type of stub is used when building the schedule  Supported values are:  None &#x3D; this is a regular payment schedule with no stubs. DO NOT use it with irregular schedules or you will get incorrect and unexpected behaviour.  ShortFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is shorter than the regular payment period.  ShortBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is shorter than the regular payment period.  LongFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is longer than the regular payment period.  LongBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is longer than the regular payment period.  Both &#x3D; this is an irregular payment schedule where both the first and the last coupons are irregular, and the length of these periods is calculated based on the first coupon payment date that should have been explicitly set. |
| **ExDividendConfiguration** | [ExDividendConfiguration](ExDividendConfiguration.md) | Optional | *No description available.* |
| **Compounding** | [Compounding](Compounding.md) | Optional | *No description available.* |
| **ResetConvention** | **string** | Optional | Control how resets are generated relative to payment convention(s).    Supported string (enumeration) values are: [InAdvance, InArrears].  Defaults to \&quot;InAdvance\&quot; if not set. |
| **UseAnnualisedDirectRates** | **bool** | Optional | Flag indicating whether to use daily updated annualised interest  rates for calculating the accrued interest. Defaults to false. |
| **CapRate** | **decimal?** | Optional | The maximum floating rate which a cashflow can accrue. |
| **FloorRate** | **decimal?** | Optional | The minimum floating rate which a cashflow can accrue. |
| **ScheduleType** | **string** | Required | The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid Default: `ScheduleTypeEnum.FloatSchedule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FloatSchedule(
    startDate: DateTimeOffset.Now,  // optional — Date from which LUSID starts generating the payment schedule.
    maturityDate: DateTimeOffset.Now,  // optional — Last date of the payment generation schedule. May not necessarily be the maturity date  of the underlying instrument (e.g. in case the instrument has multiple payment schedules).
    flowConventions: new FlowConventions(...),  // optional
    conventionName: new FlowConventionName(...),  // optional
    exDividendDays: 0,  // optional — Optional. Number of calendar days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, then there is no ex-dividend period.                NOTE: This field is deprecated.  If you wish to set the ExDividendDays on a bond, please use the ExDividendConfiguration.
    indexConventionName: new FlowConventionName(...),  // optional
    indexConventions: new IndexConvention(...),  // optional
    notional: 0.0d,  // optional — Scaling factor, the quantity outstanding on which the rate will be paid.
    paymentCurrency: "...",  // required — Payment currency. This does not have to be the same as the nominal bond or observation/reset currency.
    spread: 0.0d,  // optional — Spread over floating rate given as a fraction.
    stubType: "...",  // optional — When a payment schedule doesn&#39;t have regular payment intervals just because of the  first and/or last coupons of the schedule, we call those irregular coupons stubs.  This configuration specifies what type of stub is used when building the schedule  Supported values are:  None &#x3D; this is a regular payment schedule with no stubs. DO NOT use it with irregular schedules or you will get incorrect and unexpected behaviour.  ShortFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is shorter than the regular payment period.  ShortBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is shorter than the regular payment period.  LongFront &#x3D; this is an irregular payment schedule where only the first coupon is irregular, and covers a payment period that is longer than the regular payment period.  LongBack &#x3D; this is an irregular payment schedule where only the last coupon is irregular, and covers a payment period that is longer than the regular payment period.  Both &#x3D; this is an irregular payment schedule where both the first and the last coupons are irregular, and the length of these periods is calculated based on the first coupon payment date that should have been explicitly set.
    exDividendConfiguration: new ExDividendConfiguration(...),  // optional
    compounding: new Compounding(...),  // optional
    resetConvention: "...",  // optional — Control how resets are generated relative to payment convention(s).    Supported string (enumeration) values are: [InAdvance, InArrears].  Defaults to \&quot;InAdvance\&quot; if not set.
    useAnnualisedDirectRates: true,  // optional — Flag indicating whether to use daily updated annualised interest  rates for calculating the accrued interest. Defaults to false.
    capRate: 0.0d,  // optional — The maximum floating rate which a cashflow can accrue.
    floorRate: 0.0d,  // optional — The minimum floating rate which a cashflow can accrue.
    scheduleType: "..."  // required — The available values are: FixedSchedule, FloatSchedule, OptionalitySchedule, StepSchedule, Exercise, FxRateSchedule, FxLinkedNotionalSchedule, BondConversionSchedule, Invalid
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FloatSchedule>(json);
```


- [FlowConventions](FlowConventions.md)
- [FlowConventionName](FlowConventionName.md)
- [FlowConventionName](FlowConventionName.md)
- [IndexConvention](IndexConvention.md)
- [ExDividendConfiguration](ExDividendConfiguration.md)
- [Compounding](Compounding.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

