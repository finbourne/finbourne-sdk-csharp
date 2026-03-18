# Finbourne.Sdk.Lusid.Model.EquityOption

LUSID representation of a plain vanilla OTC Equity Option.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **OptionMaturityDate** | **DateTimeOffset** | Required | The maturity date of the option. |
| **OptionSettlementDate** | **DateTimeOffset?** | Optional | The settlement date of the option. |
| **DeliveryType** | **string** | Required | Is the option cash settled or physical delivery of option    Supported string (enumeration) values are: [Cash, Physical]. |
| **OptionType** | **string** | Required | Type of optionality for the option    Supported string (enumeration) values are: [Call, Put]. |
| **Strike** | **decimal** | Required | The strike of the option. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **UnderlyingIdentifier** | **string** | Optional | The market identifier type of the underlying code, e.g RIC.    Supported string (enumeration) values are: [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].  Optional field, should be used in combination with the Code field.  Not compatible with the Underlying field. |
| **Code** | **string** | Optional | The identifying code for the equity underlying, e.g. &#39;IBM.N&#39;.  Optional field, should be used in combination with the UnderlyingIdentifier field.  Not compatible with the Underlying field. |
| **EquityOptionType** | **string** | Optional | Equity option types. E.g. Vanilla (default), RightsIssue, Warrant.    Supported string (enumeration) values are: [Vanilla, RightsIssue, Warrant]. |
| **NumberOfShares** | **decimal?** | Optional | The amount of shares to exchange if the option is exercised. |
| **Premium** | [Premium](Premium.md) | Optional | *No description available.* |
| **ExerciseType** | **string** | Optional | Type of optionality that is present; European, American.    Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set. |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **DeliveryDays** | **int** | Optional | Number of business days between exercise date and settlement of the option payoff or underlying.  Defaults to 0 if not set. |
| **BusinessDayConvention** | **string** | Optional | Business day convention for option exercise date to settlement date calculation.  Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].  Defaults to \&quot;F\&quot; if not set. |
| **SettlementCalendars** | **List&lt;string&gt;** | Optional | Holiday calendars for option exercise date to settlement date calculation. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.EquityOption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquityOption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    optionMaturityDate: DateTimeOffset.Now,  // required — The maturity date of the option.
    optionSettlementDate: DateTimeOffset.Now,  // optional — The settlement date of the option.
    deliveryType: "...",  // required — Is the option cash settled or physical delivery of option    Supported string (enumeration) values are: [Cash, Physical].
    optionType: "...",  // required — Type of optionality for the option    Supported string (enumeration) values are: [Call, Put].
    strike: 0.0d,  // required — The strike of the option.
    domCcy: "...",  // required — The domestic currency of the instrument.
    underlyingIdentifier: "...",  // optional — The market identifier type of the underlying code, e.g RIC.    Supported string (enumeration) values are: [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].  Optional field, should be used in combination with the Code field.  Not compatible with the Underlying field.
    code: "...",  // optional — The identifying code for the equity underlying, e.g. &#39;IBM.N&#39;.  Optional field, should be used in combination with the UnderlyingIdentifier field.  Not compatible with the Underlying field.
    equityOptionType: "...",  // optional — Equity option types. E.g. Vanilla (default), RightsIssue, Warrant.    Supported string (enumeration) values are: [Vanilla, RightsIssue, Warrant].
    numberOfShares: 0.0d,  // optional — The amount of shares to exchange if the option is exercised.
    premium: new Premium(...),  // optional
    exerciseType: "...",  // optional — Type of optionality that is present; European, American.    Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.
    underlying: new LusidInstrument(...),  // optional
    deliveryDays: 0,  // optional — Number of business days between exercise date and settlement of the option payoff or underlying.  Defaults to 0 if not set.
    businessDayConvention: "...",  // optional — Business day convention for option exercise date to settlement date calculation.  Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].  Defaults to \&quot;F\&quot; if not set.
    settlementCalendars: ,  // optional — Holiday calendars for option exercise date to settlement date calculation.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    instrumentType: "..."  // required — The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EquityOption>(json);
```


- [Premium](Premium.md)
- [LusidInstrument](LusidInstrument.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

