# Finbourne.Sdk.Lusid.Model.TermDeposit

LUSID representation of a Term Deposit.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. For term deposits this is the start date of the interest calculation period. |
| **MaturityDate** | **DateTimeOffset** | Required | The maturity date of the instrument. For term deposits this is the last date of the interest calculation period. |
| **ContractSize** | **decimal** | Required | The principal amount of the term deposit. |
| **FlowConvention** | [FlowConventions](FlowConventions.md) | Required | *No description available.* |
| **Rate** | **decimal** | Required | The fixed rate for the term deposit. Specified as a decimal, e.g 0.03 is meant to be 3% interest |
| **DomCcy** | **string** | Optional | The domestic currency of the instrument. This should be the same as the Currency set on the FlowConventions.  You do not need to populate this field for Term Deposits in LUSID as all functionality is driven by the Currency set on the FlowConventions.  LUSID will not store values saved on this field. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.TermDeposit` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TermDeposit(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. For term deposits this is the start date of the interest calculation period.
    maturityDate: DateTimeOffset.Now,  // required — The maturity date of the instrument. For term deposits this is the last date of the interest calculation period.
    contractSize: 0.0d,  // required — The principal amount of the term deposit.
    flowConvention: new FlowConventions(...),  // required
    rate: 0.0d,  // required — The fixed rate for the term deposit. Specified as a decimal, e.g 0.03 is meant to be 3% interest
    domCcy: "...",  // optional — The domestic currency of the instrument. This should be the same as the Currency set on the FlowConventions.  You do not need to populate this field for Term Deposits in LUSID as all functionality is driven by the Currency set on the FlowConventions.  LUSID will not store values saved on this field.
    tradingConventions: new TradingConventions(...),  // optional
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
var instance = JsonConvert.DeserializeObject<TermDeposit>(json);
```


- [FlowConventions](FlowConventions.md)
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

