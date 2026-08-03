# Finbourne.Sdk.Lusid.Model.ToBeAnnouncedOption

LUSID representation of an OTC option on a ToBeAnnounced (TBA) forward contract.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **ExpiryDate** | **DateTimeOffset** | Required | The date on which the option expires, i.e. the last exercise date of the option. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **OptionType** | **string** | Required | Type of optionality for the option.                Supported string (enumeration) values are: [Call, Put]. |
| **Strike** | **decimal** | Required | The strike of the option. |
| **DeliveryType** | **string** | Required | Is the option cash settled or physical delivery of the underlying TBA.                Supported string (enumeration) values are: [Cash, Physical]. |
| **Underlying** | [MasteredInstrument](MasteredInstrument.md) | Required | *No description available.* |
| **ExerciseType** | **string** | Required | Type of optionality that is present; European only in this scope.                Supported string (enumeration) values are: [European]. |
| **Premium** | [Premium](Premium.md) | Required | *No description available.* |
| **DeliveryDays** | **int** | Optional | Number of business days between exercise date and settlement of the option payoff or underlying.  Defaults to 0 if not set. |
| **BusinessDayConvention** | **string** | Optional | Business day convention for option exercise date to settlement date calculation.  Default value: F. Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid. |
| **SettlementCalendars** | **List&lt;string&gt;** | Optional | Holiday calendar for option exercise date to settlement date calculation. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption. Default: `InstrumentTypeEnum.ToBeAnnouncedOption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ToBeAnnouncedOption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    expiryDate: DateTimeOffset.Now,  // required — The date on which the option expires, i.e. the last exercise date of the option.
    domCcy: "...",  // required — The domestic currency of the instrument.
    optionType: "...",  // required — Type of optionality for the option.                Supported string (enumeration) values are: [Call, Put].
    strike: 0.0d,  // required — The strike of the option.
    deliveryType: "...",  // required — Is the option cash settled or physical delivery of the underlying TBA.                Supported string (enumeration) values are: [Cash, Physical].
    underlying: new MasteredInstrument(...),  // required
    exerciseType: "...",  // required — Type of optionality that is present; European only in this scope.                Supported string (enumeration) values are: [European].
    premium: new Premium(...),  // required
    deliveryDays: 0,  // optional — Number of business days between exercise date and settlement of the option payoff or underlying.  Defaults to 0 if not set.
    businessDayConvention: "...",  // optional — Business day convention for option exercise date to settlement date calculation.  Default value: F. Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid.
    settlementCalendars: ,  // optional — Holiday calendar for option exercise date to settlement date calculation.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    tradingConventions: new TradingConventions(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ToBeAnnouncedOption>(json);
```


- [MasteredInstrument](MasteredInstrument.md)
- [Premium](Premium.md)
- [TimeZoneConventions](TimeZoneConventions.md)
- [TradingConventions](TradingConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

