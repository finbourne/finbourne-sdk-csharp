# Finbourne.Sdk.Lusid.Model.ExchangeTradedOption

LUSID representation of an Exchange Traded Option.  Including, but not limited to, Equity Options, Bond Options, Index Options, Future Options, and Interest Rate Options.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **ContractDetails** | [ExchangeTradedOptionContractDetails](ExchangeTradedOptionContractDetails.md) | Required | *No description available.* |
| **Contracts** | **decimal** | Required | The number of contracts held. |
| **RefSpotPrice** | **decimal?** | Optional | The reference price at which the contract was entered into. Optional.  If omitted, the option has no reference price of its own.  Under ConstantTimeValueOfMoney, a holding with a notional cost (for example from Transaction/default/NotionalAmount) is then valued like a future, against its notional cost plus the variation margin settled to date.  A holding without a notional cost is then valued at its full market price.  If 0, the reference is taken from the holding&#39;s cost.  Any other value is used as given.  Writes through Luminesce that do not supply RefSpotPrice store 0. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest, WholeLoanFacility, StripBond. Default: `InstrumentTypeEnum.ExchangeTradedOption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExchangeTradedOption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    contractDetails: new ExchangeTradedOptionContractDetails(...),  // required
    contracts: 0.0d,  // required — The number of contracts held.
    refSpotPrice: 0.0d,  // optional — The reference price at which the contract was entered into. Optional.  If omitted, the option has no reference price of its own.  Under ConstantTimeValueOfMoney, a holding with a notional cost (for example from Transaction/default/NotionalAmount) is then valued like a future, against its notional cost plus the variation margin settled to date.  A holding without a notional cost is then valued at its full market price.  If 0, the reference is taken from the holding&#39;s cost.  Any other value is used as given.  Writes through Luminesce that do not supply RefSpotPrice store 0.
    tradingConventions: new TradingConventions(...),  // optional
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest, WholeLoanFacility, StripBond.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExchangeTradedOption>(json);
```


- [ExchangeTradedOptionContractDetails](ExchangeTradedOptionContractDetails.md)
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

