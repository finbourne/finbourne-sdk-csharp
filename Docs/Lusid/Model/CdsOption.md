# Finbourne.Sdk.Lusid.Model.CdsOption

LUSID representation of an option on a single-name Credit Default Swap or a CDX/iTraxx index,  discriminated by the MasteredInstrumentType field of the referenced MasteredInstrument, which is derived  from the resolved type of the underlying. Referenced via a MasteredInstrument.  Quote-driven by default: it has no coupon or projected interim cashflow, its only cash movement being  the spot premium.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **Strike** | **decimal** | Required | The strike of the option. |
| **BusinessDayConvention** | **string** | Optional | Business day convention for the maturity-to-settlement date calculation.  Default value: F.                Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest]. Default value: F. Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid. Default: `"F"` |
| **DeliveryDays** | **int** | Optional | Number of business days between the option maturity date and settlement, used to compute  OptionSettlementDate when not explicitly overridden. Defaults to 2 if not set. Default: `2` |
| **DeliveryType** | **string** | Required | Is the option cash settled or physical delivery of the underlying.                Supported string (enumeration) values are: [Cash, Physical]. Available values: Cash, Physical. |
| **ExerciseType** | **string** | Optional | Type of optionality that is present; European only in this scope.  Default value: European.                Supported string (enumeration) values are: [European, Bermudan, American]. Default value: European. Available values: None, European, Bermudan, American. Default: `"European"` |
| **Notional** | **decimal** | Required | Fixed per-unit reference multiplier. Aggregate exposure &#x3D; Holding/Units x Notional; not a mutable total. |
| **OptionMaturityDate** | **DateTimeOffset** | Required | The last exercise date of the option. |
| **OptionSettlementDate** | **DateTimeOffset?** | Optional | Explicit override of the option&#39;s settlement date. If not supplied, it is computed as a  business-day-adjusted delivery of DeliveryDays after OptionMaturityDate. |
| **OptionType** | **string** | Required | The direction of the credit option: Payer or Receiver.                Supported string (enumeration) values are: [Payer, Receiver]. Available values: Payer, Receiver. |
| **Premium** | [Premium](Premium.md) | Optional | *No description available.* |
| **SettlementCalendars** | **List&lt;string&gt;** | Optional | Holiday calendars for the maturity-to-settlement date calculation. |
| **Underlying** | [MasteredInstrument](MasteredInstrument.md) | Optional | *No description available.* |
| **UnderlyingVersion** | **DateTimeOffset** | Required | The AsAt timestamp of the underlying&#39;s definition at the time this option was written, pinning  lookups of the underlying&#39;s composition and terms independently of subsequent index rolls or re-upserts. |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap. Default: `InstrumentTypeEnum.CdsOption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CdsOption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    domCcy: "...",  // required — The domestic currency of the instrument.
    strike: 0.0d,  // required — The strike of the option.
    businessDayConvention: "...",  // optional — Business day convention for the maturity-to-settlement date calculation.  Default value: F.                Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest]. Default value: F. Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid.
    deliveryDays: 0,  // optional — Number of business days between the option maturity date and settlement, used to compute  OptionSettlementDate when not explicitly overridden. Defaults to 2 if not set.
    deliveryType: "...",  // required — Is the option cash settled or physical delivery of the underlying.                Supported string (enumeration) values are: [Cash, Physical]. Available values: Cash, Physical.
    exerciseType: "...",  // optional — Type of optionality that is present; European only in this scope.  Default value: European.                Supported string (enumeration) values are: [European, Bermudan, American]. Default value: European. Available values: None, European, Bermudan, American.
    notional: 0.0d,  // required — Fixed per-unit reference multiplier. Aggregate exposure &#x3D; Holding/Units x Notional; not a mutable total.
    optionMaturityDate: DateTimeOffset.Now,  // required — The last exercise date of the option.
    optionSettlementDate: DateTimeOffset.Now,  // optional — Explicit override of the option&#39;s settlement date. If not supplied, it is computed as a  business-day-adjusted delivery of DeliveryDays after OptionMaturityDate.
    optionType: "...",  // required — The direction of the credit option: Payer or Receiver.                Supported string (enumeration) values are: [Payer, Receiver]. Available values: Payer, Receiver.
    premium: new Premium(...),  // optional
    settlementCalendars: ,  // optional — Holiday calendars for the maturity-to-settlement date calculation.
    underlying: new MasteredInstrument(...),  // optional
    underlyingVersion: DateTimeOffset.Now,  // required — The AsAt timestamp of the underlying&#39;s definition at the time this option was written, pinning  lookups of the underlying&#39;s composition and terms independently of subsequent index rolls or re-upserts.
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CdsOption>(json);
```


- [Premium](Premium.md)
- [MasteredInstrument](MasteredInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

