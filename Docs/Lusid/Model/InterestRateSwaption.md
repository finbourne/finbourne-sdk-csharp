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
| **BusinessDayConvention** | **string** | Optional | Business day convention for option exercise date to settlement date calculation.  Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].                Defaults to \&quot;F\&quot;. |
| **SettlementCalendars** | **List&lt;string&gt;** | Optional | Holiday calendars for option exercise date to settlement date calculation. |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.InterestRateSwaption` |


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
    businessDayConvention: "...",  // optional — Business day convention for option exercise date to settlement date calculation.  Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].                Defaults to \&quot;F\&quot;.
    settlementCalendars: ,  // optional — Holiday calendars for option exercise date to settlement date calculation.
    instrumentType: "..."  // required — The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo
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


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

