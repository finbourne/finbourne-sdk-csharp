# Finbourne.Sdk.Lusid.Model.LegDefinition

Definition of the set of flow and index conventions along with other miscellaneous information required to generate an instrument leg.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ConventionName** | [FlowConventionName](FlowConventionName.md) | Optional | *No description available.* |
| **Conventions** | [FlowConventions](FlowConventions.md) | Optional | *No description available.* |
| **IndexConvention** | [IndexConvention](IndexConvention.md) | Optional | *No description available.* |
| **IndexConventionName** | [FlowConventionName](FlowConventionName.md) | Optional | *No description available.* |
| **NotionalExchangeType** | **string** | Required | what type of notional exchange does the leg have    Supported string (enumeration) values are: [None, Initial, Final, Both]. |
| **PayReceive** | **string** | Required | Is the leg to be paid or received    Supported string (enumeration) values are: [Pay, Receive]. |
| **RateOrSpread** | **decimal** | Required | Is there either a fixed rate (non-zero) or spread to be paid over the value of the leg. |
| **ResetConvention** | **string** | Optional | Control how resets are generated relative to swap payment convention(s).    Supported string (enumeration) values are: [InAdvance, InArrears].  Defaults to \&quot;InAdvance\&quot; if not set. |
| **StubType** | **string** | Required | If a stub is required should it be at the front or back of the leg.    Supported string (enumeration) values are: [None, ShortFront, ShortBack, LongBack, LongFront, Both]. |
| **Compounding** | [Compounding](Compounding.md) | Optional | *No description available.* |
| **Amortisation** | [StepSchedule](StepSchedule.md) | Optional | *No description available.* |
| **FirstRegularPaymentDate** | **DateTimeOffset?** | Optional | Optional payment date of the first regular coupon.  Must be greater than the StartDate.  If set, the regular coupon schedule will be built such that the first regular coupon  will end on this date. The start date of this coupon will be calculated as normal and  a stub coupon will be created from the StartDate to the start of the first regular coupon. |
| **FirstCouponType** | **string** | Optional | Optional coupon type setting for the first coupon, can be used with Stub coupons.  If set to \&quot;ProRata\&quot; (the default), the coupon year fraction is calculated as normal,  however if set to \&quot;Full\&quot; the year fraction is overwritten with the standard year fraction  for a regular ful\&quot; coupon. Note this does not use the day count convention but rather is defined  directly from the tenor (i.e. a quarterly leg will be set to 0.25).    Supported string (enumeration) values are: [ProRata, Full]. |
| **LastRegularPaymentDate** | **DateTimeOffset?** | Optional | Optional payment date of the last regular coupon.  Must be less than the Maturity date.  If set, the regular coupon schedule will be built up to this date and the final  coupon will be a stub between this date and the Maturity date. |
| **LastCouponType** | **string** | Optional | Optional coupon type setting for the last coupon, can be used with Stub coupons.  If set to \&quot;ProRata\&quot; (the default), the coupon year fraction is calculated as normal,  however if set to \&quot;Full\&quot; the year fraction is overwritten with the standard year fraction  for a regular ful\&quot; coupon. Note this does not use the day count convention but rather is defined  directly from the tenor (i.e. a quarterly leg will be set to 0.25).    Supported string (enumeration) values are: [ProRata, Full]. |
| **FxLinkedNotionalSchedule** | [FxLinkedNotionalSchedule](FxLinkedNotionalSchedule.md) | Optional | *No description available.* |
| **IntermediateNotionalExchange** | **bool?** | Optional | Indicates whether there are intermediate notional exchanges. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LegDefinition(
    conventionName: new FlowConventionName(...),  // optional
    conventions: new FlowConventions(...),  // optional
    indexConvention: new IndexConvention(...),  // optional
    indexConventionName: new FlowConventionName(...),  // optional
    notionalExchangeType: "...",  // required — what type of notional exchange does the leg have    Supported string (enumeration) values are: [None, Initial, Final, Both].
    payReceive: "...",  // required — Is the leg to be paid or received    Supported string (enumeration) values are: [Pay, Receive].
    rateOrSpread: 0.0d,  // required — Is there either a fixed rate (non-zero) or spread to be paid over the value of the leg.
    resetConvention: "...",  // optional — Control how resets are generated relative to swap payment convention(s).    Supported string (enumeration) values are: [InAdvance, InArrears].  Defaults to \&quot;InAdvance\&quot; if not set.
    stubType: "...",  // required — If a stub is required should it be at the front or back of the leg.    Supported string (enumeration) values are: [None, ShortFront, ShortBack, LongBack, LongFront, Both].
    compounding: new Compounding(...),  // optional
    amortisation: new StepSchedule(...),  // optional
    firstRegularPaymentDate: DateTimeOffset.Now,  // optional — Optional payment date of the first regular coupon.  Must be greater than the StartDate.  If set, the regular coupon schedule will be built such that the first regular coupon  will end on this date. The start date of this coupon will be calculated as normal and  a stub coupon will be created from the StartDate to the start of the first regular coupon.
    firstCouponType: "...",  // optional — Optional coupon type setting for the first coupon, can be used with Stub coupons.  If set to \&quot;ProRata\&quot; (the default), the coupon year fraction is calculated as normal,  however if set to \&quot;Full\&quot; the year fraction is overwritten with the standard year fraction  for a regular ful\&quot; coupon. Note this does not use the day count convention but rather is defined  directly from the tenor (i.e. a quarterly leg will be set to 0.25).    Supported string (enumeration) values are: [ProRata, Full].
    lastRegularPaymentDate: DateTimeOffset.Now,  // optional — Optional payment date of the last regular coupon.  Must be less than the Maturity date.  If set, the regular coupon schedule will be built up to this date and the final  coupon will be a stub between this date and the Maturity date.
    lastCouponType: "...",  // optional — Optional coupon type setting for the last coupon, can be used with Stub coupons.  If set to \&quot;ProRata\&quot; (the default), the coupon year fraction is calculated as normal,  however if set to \&quot;Full\&quot; the year fraction is overwritten with the standard year fraction  for a regular ful\&quot; coupon. Note this does not use the day count convention but rather is defined  directly from the tenor (i.e. a quarterly leg will be set to 0.25).    Supported string (enumeration) values are: [ProRata, Full].
    fxLinkedNotionalSchedule: new FxLinkedNotionalSchedule(...),  // optional
    intermediateNotionalExchange: true  // optional — Indicates whether there are intermediate notional exchanges.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LegDefinition>(json);
```


## Related Models

- [FlowConventionName](FlowConventionName.md)
- [FlowConventions](FlowConventions.md)
- [IndexConvention](IndexConvention.md)
- [FlowConventionName](FlowConventionName.md)
- [Compounding](Compounding.md)
- [StepSchedule](StepSchedule.md)
- [FxLinkedNotionalSchedule](FxLinkedNotionalSchedule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

