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
| **DomCcy** | **string** | Optional | The currency the option settles in.                Optional, and in almost all cases it should be left to default. If not specified, the currency of  the underlying swap is used, which for a cross-currency swap is the currency of its first leg.                A specified currency is taken as given and is not validated against the underlying swap, since  settling in another currency is rare but legitimate. Note that valuation of such a swaption is not  supported, as converting from the currency the swap is valued in needs an fx rate the instrument  does not define. |
| **ExerciseDate** | **DateTimeOffset?** | Optional | The date the option expires, and for European exercise the date it is exercised. For American  exercise it is the end of the window the option may be exercised in, so it should be set on the  instrument for the option to be exercisable up to the intended date.                If not specified, the start date of the underlying swap is used. |
| **ExerciseType** | **string** | Optional | Type of optionality that is present; European, American.                Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.                A European option is exercised on its exercise date, so its exercise event is generated with  that date already set. An American option may be exercised at any point up to that date, so the  date it is actually exercised on is supplied on the exercise event; set exerciseDate on the  instrument to open the window the event may fall in.                The swap delivered on exercise keeps the start date it was defined with, so exercising early  or late leaves it aged or forward-starting relative to the exercise. Keeping that swap  correct for the intended exercise is the responsibility of whoever defines it. In particular,  for an American physically settled swaption on a cross-currency underlying, neither the swap&#39;s  start date nor its fx notionals are determined at trade time, so amending the delivered swap  position after exercise is an operational step the client must carry out. |
| **Strike** | **decimal?** | Optional | The rate the option strikes against.                May only be specified when the underlying swap has no single fixed leg, as otherwise that leg&#39;s  fixed rate is the strike. It must be specified when the underlying swap has two fixed legs, as  there is then no single rate to strike against. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare. Default: `InstrumentTypeEnum.InterestRateSwaption` |


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
    domCcy: "...",  // optional — The currency the option settles in.                Optional, and in almost all cases it should be left to default. If not specified, the currency of  the underlying swap is used, which for a cross-currency swap is the currency of its first leg.                A specified currency is taken as given and is not validated against the underlying swap, since  settling in another currency is rare but legitimate. Note that valuation of such a swaption is not  supported, as converting from the currency the swap is valued in needs an fx rate the instrument  does not define.
    exerciseDate: DateTimeOffset.Now,  // optional — The date the option expires, and for European exercise the date it is exercised. For American  exercise it is the end of the window the option may be exercised in, so it should be set on the  instrument for the option to be exercisable up to the intended date.                If not specified, the start date of the underlying swap is used.
    exerciseType: "...",  // optional — Type of optionality that is present; European, American.                Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.                A European option is exercised on its exercise date, so its exercise event is generated with  that date already set. An American option may be exercised at any point up to that date, so the  date it is actually exercised on is supplied on the exercise event; set exerciseDate on the  instrument to open the window the event may fall in.                The swap delivered on exercise keeps the start date it was defined with, so exercising early  or late leaves it aged or forward-starting relative to the exercise. Keeping that swap  correct for the intended exercise is the responsibility of whoever defines it. In particular,  for an American physically settled swaption on a cross-currency underlying, neither the swap&#39;s  start date nor its fx notionals are determined at trade time, so amending the delivered swap  position after exercise is an operational step the client must carry out.
    strike: 0.0d,  // optional — The rate the option strikes against.                May only be specified when the underlying swap has no single fixed leg, as otherwise that leg&#39;s  fixed rate is the strike. It must be specified when the underlying swap has two fixed legs, as  there is then no single rate to strike against.
    tradingConventions: new TradingConventions(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare.
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

