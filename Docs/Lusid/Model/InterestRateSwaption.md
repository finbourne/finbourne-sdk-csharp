# Finbourne.Sdk.Lusid.Model.InterestRateSwaption

LUSID representation of an Interest Rate Swaption.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **PayOrReceiveFixed** | **string** | Required | Pay or Receive the fixed leg of the underlying swap.    Supported string (enumeration) values are: [Pay, Receive]. |
| **Premium** | [Premium](Premium.md) | Optional | *No description available.* |
| **DeliveryMethod** | **string** | Required | How does the option settle    Supported string (enumeration) values are: [Cash, Physical]. |
| **Swap** | [InterestRateSwap](InterestRateSwap.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **DeliveryDays** | **int** | Optional | Number of business days between exercise date and settlement of the option payoff or underlying.                Defaults to 0. |
| **BusinessDayConvention** | **string** | Optional | Business day convention for option exercise date to settlement date calculation.  Default value: F. Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid. |
| **SettlementCalendars** | **List&lt;string&gt;** | Optional | Holiday calendars for option exercise date to settlement date calculation. |
| **DomCcy** | **string** | Optional | The currency the option settles in.                If not specified, the currency of the underlying swap is used. When specified it must be one of  the currencies of the underlying swap. |
| **ExerciseDate** | **DateTimeOffset?** | Optional | The date the option expires, and for European exercise the date it is exercised.                If not specified, the start date of the underlying swap is used. |
| **ExerciseType** | **string** | Optional | Type of optionality that is present; European, American.                Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.                A European option is exercised on its exercise date, so its exercise event is generated with  that date already set. An American option may be exercised at any point in its life, so it  carries no scheduled date and the exercise date is supplied on the exercise event instead.                The swap delivered on exercise keeps the start date it was defined with, so exercising early  or late leaves it aged or forward-starting relative to the exercise. Keeping that swap  correct for the intended exercise is the responsibility of whoever defines it. |
| **Strike** | **decimal?** | Optional | The rate the option strikes against.                May only be specified when the underlying swap has no single fixed leg, as otherwise that leg&#39;s  fixed rate is the strike. It must be specified when the underlying swap has two fixed legs, as  there is then no single rate to strike against. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap. Default: `InstrumentTypeEnum.InterestRateSwaption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InterestRateSwaption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    payOrReceiveFixed: "...",  // required — Pay or Receive the fixed leg of the underlying swap.    Supported string (enumeration) values are: [Pay, Receive].
    premium: new Premium(...),  // optional
    deliveryMethod: "...",  // required — How does the option settle    Supported string (enumeration) values are: [Cash, Physical].
    swap: new InterestRateSwap(...),  // optional
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    underlying: new LusidInstrument(...),  // optional
    deliveryDays: 0,  // optional — Number of business days between exercise date and settlement of the option payoff or underlying.                Defaults to 0.
    businessDayConvention: "...",  // optional — Business day convention for option exercise date to settlement date calculation.  Default value: F. Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid.
    settlementCalendars: ,  // optional — Holiday calendars for option exercise date to settlement date calculation.
    domCcy: "...",  // optional — The currency the option settles in.                If not specified, the currency of the underlying swap is used. When specified it must be one of  the currencies of the underlying swap.
    exerciseDate: DateTimeOffset.Now,  // optional — The date the option expires, and for European exercise the date it is exercised.                If not specified, the start date of the underlying swap is used.
    exerciseType: "...",  // optional — Type of optionality that is present; European, American.                Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.                A European option is exercised on its exercise date, so its exercise event is generated with  that date already set. An American option may be exercised at any point in its life, so it  carries no scheduled date and the exercise date is supplied on the exercise event instead.                The swap delivered on exercise keeps the start date it was defined with, so exercising early  or late leaves it aged or forward-starting relative to the exercise. Keeping that swap  correct for the intended exercise is the responsibility of whoever defines it.
    strike: 0.0d,  // optional — The rate the option strikes against.                May only be specified when the underlying swap has no single fixed leg, as otherwise that leg&#39;s  fixed rate is the strike. It must be specified when the underlying swap has two fixed legs, as  there is then no single rate to strike against.
    tradingConventions: new TradingConventions(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InterestRateSwaption>(json);
```


- [Premium](Premium.md)
- [InterestRateSwap](InterestRateSwap.md)
- [TimeZoneConventions](TimeZoneConventions.md)
- [LusidInstrument](LusidInstrument.md)
- [TradingConventions](TradingConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

