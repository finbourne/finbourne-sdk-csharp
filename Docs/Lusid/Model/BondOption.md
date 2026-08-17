# Finbourne.Sdk.Lusid.Model.BondOption

LUSID representation of an OTC bilateral option (call or put) on a single mastered cash bond  (Bond, ComplexBond or InflationLinkedBond). Quote-driven valuation with an upfront premium;  European exercise only, cash-settled in the current scope (physical settlement is future work).
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **Strike** | **decimal** | Required | The strike as a clean price, percent of par (real/unindexed for a linker). |
| **ContractSize** | **decimal** | Required | The face amount per contract (e.g. 1,000,000). Together with the per-100 clean-price strike this  turns the strike and payoff into money: strikePerUnit &#x3D; strike / 100 * contractSize. |
| **DeliveryType** | **string** | Required | How does the option settle. Only Cash is supported for a BondOption.                Supported string (enumeration) values are: [Cash, Physical]. |
| **ExerciseDates** | **List&lt;DateTimeOffset&gt;** | Required | The exercise dates; exactly one entry, equal to the expiry date (European only in scope). |
| **ExerciseType** | **string** | Optional | Type of optionality that is present. Only European is supported for a BondOption.                Supported string (enumeration) values are: [European, Bermudan, American]. |
| **ExpiryDate** | **DateTimeOffset** | Required | This is the date when the option expires, i.e. the LAST exercise date of the option.  The property is internal, we may change it in the future (think about Bermuda options). |
| **OptionType** | **string** | Required | Type of optionality for the option.                Supported string (enumeration) values are: [Call, Put]. |
| **Premium** | [Premium](Premium.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Required | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap. Default: `InstrumentTypeEnum.BondOption` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondOption(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    domCcy: "...",  // required — The domestic currency of the instrument.
    strike: 0.0d,  // required — The strike as a clean price, percent of par (real/unindexed for a linker).
    contractSize: 0.0d,  // required — The face amount per contract (e.g. 1,000,000). Together with the per-100 clean-price strike this  turns the strike and payoff into money: strikePerUnit &#x3D; strike / 100 * contractSize.
    deliveryType: "...",  // required — How does the option settle. Only Cash is supported for a BondOption.                Supported string (enumeration) values are: [Cash, Physical].
    exerciseDates: ,  // required — The exercise dates; exactly one entry, equal to the expiry date (European only in scope).
    exerciseType: "...",  // optional — Type of optionality that is present. Only European is supported for a BondOption.                Supported string (enumeration) values are: [European, Bermudan, American].
    expiryDate: DateTimeOffset.Now,  // required — This is the date when the option expires, i.e. the LAST exercise date of the option.  The property is internal, we may change it in the future (think about Bermuda options).
    optionType: "...",  // required — Type of optionality for the option.                Supported string (enumeration) values are: [Call, Put].
    premium: new Premium(...),  // optional
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    tradingConventions: new TradingConventions(...),  // optional
    underlying: new LusidInstrument(...),  // required
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondOption>(json);
```


- [Premium](Premium.md)
- [TimeZoneConventions](TimeZoneConventions.md)
- [TradingConventions](TradingConventions.md)
- [LusidInstrument](LusidInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

