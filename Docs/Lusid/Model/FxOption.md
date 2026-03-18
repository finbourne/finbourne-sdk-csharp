# Finbourne.Sdk.Lusid.Model.FxOption

LUSID representation of an FX Option.  Including Vanilla, American, European, and Digital (Binary) options.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **DomAmount** | **decimal?** | Optional | The Amount of DomCcy that will be exchanged if the option is exercised.  This amount should be a positive number, with the Call/Put flag used to indicate direction.  The corresponding amount of FgnCcy that will be exchanged is this amount times the strike.  Note there is no rounding performed on this computed value.  This is an optional field, if not set the option ContractSize will default to 1. |
| **FgnCcy** | **string** | Required | The foreign currency of the FX. |
| **FgnAmount** | **decimal?** | Optional | For a vanilla FxOption contract, FgnAmount cannot be set.  In case of a digital FxOption (IsPayoffDigital&#x3D;&#x3D;true)  a payoff (if the option is in the money) can be either  in domestic or in foreign currency - for the latter  FgnAmount must be set.  Note: It is invalid to have FgnAmount and DomAmount  at the same time. |
| **Strike** | **decimal?** | Optional | The strike of the option. |
| **Barriers** | [List&lt;Barrier&gt;](Barrier.md) | Optional | For a barrier option the list should not be empty. Up to two barriers are supported.  An option cannot be at the same time barrier- and touch-option.  One (or both) of the lists must be empty. |
| **ExerciseType** | **string** | Optional | Type of optionality that is present; European, American.    Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set. |
| **IsCallNotPut** | **bool** | Required | True if the option is a call, false if the option is a put. |
| **IsDeliveryNotCash** | **bool** | Required | True if the option delivers the FX underlying, False if the option is settled in cash. |
| **IsPayoffDigital** | **bool** | Optional | By default IsPayoffDigital is false. If IsPayoffDigital&#x3D;true,  the option is &#39;digital&#39;, and the option payoff is 0 or 1 unit of currency,  instead of a vanilla CallPayoff&#x3D;max(spot-strike,0) or PutPayoff&#x3D;max(strike-spot,0). |
| **OptionMaturityDate** | **DateTimeOffset** | Required | The maturity date of the option. |
| **OptionSettlementDate** | **DateTimeOffset** | Required | The settlement date of the option. |
| **PayoutStyle** | **string** | Optional | PayoutStyle for touch options.                For options without touch optionality, payoutStyle should not be set.  For options with touch optionality (where the touches data has been set), payoutStyle must be defined and cannot be None.    Supported string (enumeration) values are: [Deferred, Immediate].  Defaults to \&quot;None\&quot; if not set. |
| **Premium** | [Premium](Premium.md) | Optional | *No description available.* |
| **Touches** | [List&lt;Touch&gt;](Touch.md) | Optional | For a touch option the list should not be empty. Up to two touches are supported.  An option cannot be at the same time barrier- and touch-option.  One (or both) of the lists must be empty. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.FxOption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxOption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    domCcy: "...",  // required — The domestic currency of the instrument.
    domAmount: 0.0d,  // optional — The Amount of DomCcy that will be exchanged if the option is exercised.  This amount should be a positive number, with the Call/Put flag used to indicate direction.  The corresponding amount of FgnCcy that will be exchanged is this amount times the strike.  Note there is no rounding performed on this computed value.  This is an optional field, if not set the option ContractSize will default to 1.
    fgnCcy: "...",  // required — The foreign currency of the FX.
    fgnAmount: 0.0d,  // optional — For a vanilla FxOption contract, FgnAmount cannot be set.  In case of a digital FxOption (IsPayoffDigital&#x3D;&#x3D;true)  a payoff (if the option is in the money) can be either  in domestic or in foreign currency - for the latter  FgnAmount must be set.  Note: It is invalid to have FgnAmount and DomAmount  at the same time.
    strike: 0.0d,  // optional — The strike of the option.
    barriers: new List<Barrier>(),  // optional — For a barrier option the list should not be empty. Up to two barriers are supported.  An option cannot be at the same time barrier- and touch-option.  One (or both) of the lists must be empty.
    exerciseType: "...",  // optional — Type of optionality that is present; European, American.    Supported string (enumeration) values are: [European, American].  Defaults to \&quot;European\&quot; if not set.
    isCallNotPut: true,  // required — True if the option is a call, false if the option is a put.
    isDeliveryNotCash: true,  // required — True if the option delivers the FX underlying, False if the option is settled in cash.
    isPayoffDigital: true,  // optional — By default IsPayoffDigital is false. If IsPayoffDigital&#x3D;true,  the option is &#39;digital&#39;, and the option payoff is 0 or 1 unit of currency,  instead of a vanilla CallPayoff&#x3D;max(spot-strike,0) or PutPayoff&#x3D;max(strike-spot,0).
    optionMaturityDate: DateTimeOffset.Now,  // required — The maturity date of the option.
    optionSettlementDate: DateTimeOffset.Now,  // required — The settlement date of the option.
    payoutStyle: "...",  // optional — PayoutStyle for touch options.                For options without touch optionality, payoutStyle should not be set.  For options with touch optionality (where the touches data has been set), payoutStyle must be defined and cannot be None.    Supported string (enumeration) values are: [Deferred, Immediate].  Defaults to \&quot;None\&quot; if not set.
    premium: new Premium(...),  // optional
    touches: new List<Touch>(),  // optional — For a touch option the list should not be empty. Up to two touches are supported.  An option cannot be at the same time barrier- and touch-option.  One (or both) of the lists must be empty.
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
var instance = JsonConvert.DeserializeObject<FxOption>(json);
```


- [Barrier](Barrier.md) — used in `Barriers`
- [Premium](Premium.md)
- [Touch](Touch.md) — used in `Touches`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

