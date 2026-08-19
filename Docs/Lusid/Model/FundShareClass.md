# Finbourne.Sdk.Lusid.Model.FundShareClass

LUSID representation of a FundShareClass.  A ShareClass represents a pool of shares, held by investors, within a fund.   A ShareClass can represent a differing investment approach by either Fees,   Income, Currency Risk and Investor type.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShortCode** | **string** | Required | A short identifier, unique across a single fund, usually made up of the ShareClass components. Eg \&quot;A Accumulation Euro Hedged Class\&quot; could become \&quot;A Acc H EUR\&quot;. |
| **FundShareClassType** | **string** | Optional | The type of distribution that the ShareClass will calculate. Can be either &#39;Income&#39; or &#39;Accumulation&#39; - Income classes will pay out and Accumulation classes will retain their ShareClass attributable income. Available values: Income, Accumulation. |
| **DistributionPaymentType** | **string** | Optional | The tax treatment applied to any distributions calculated within the ShareClass. Can be either &#39;Net&#39; (Distribution Calculated net of tax) or &#39;Gross&#39; (Distribution calculated gross of tax). Available values: Invalid, Gross, Net. |
| **DistributionType** | **string** | Optional | The type of distribution calculated for the ShareClass. Can be either &#39;Income&#39; or &#39;Accumulation&#39;. Available values: Income, Accumulation. |
| **Hedging** | **string** | Optional | A flag to indicate the ShareClass is operating currency hedging as a means to limit currency risk as part of its investment strategy. Available values: Invalid, None, ApplyHedging. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **RoundingConventions** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding Convention used for the FundShareClass quotes |
| **RoundingConventionUnits** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding Conventions used for the FundShareClass units |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap. Default: `InstrumentTypeEnum.FundShareClass` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundShareClass(
    shortCode: "...",  // required — A short identifier, unique across a single fund, usually made up of the ShareClass components. Eg \&quot;A Accumulation Euro Hedged Class\&quot; could become \&quot;A Acc H EUR\&quot;.
    fundShareClassType: "...",  // optional — The type of distribution that the ShareClass will calculate. Can be either &#39;Income&#39; or &#39;Accumulation&#39; - Income classes will pay out and Accumulation classes will retain their ShareClass attributable income. Available values: Income, Accumulation.
    distributionPaymentType: "...",  // optional — The tax treatment applied to any distributions calculated within the ShareClass. Can be either &#39;Net&#39; (Distribution Calculated net of tax) or &#39;Gross&#39; (Distribution calculated gross of tax). Available values: Invalid, Gross, Net.
    distributionType: "...",  // optional — The type of distribution calculated for the ShareClass. Can be either &#39;Income&#39; or &#39;Accumulation&#39;. Available values: Income, Accumulation.
    hedging: "...",  // optional — A flag to indicate the ShareClass is operating currency hedging as a means to limit currency risk as part of its investment strategy. Available values: Invalid, None, ApplyHedging.
    domCcy: "...",  // required — The domestic currency of the instrument.
    roundingConventions: new List<SimpleRoundingConvention>(),  // optional — Rounding Convention used for the FundShareClass quotes
    roundingConventionUnits: new List<SimpleRoundingConvention>(),  // optional — Rounding Conventions used for the FundShareClass units
    tradingConventions: new TradingConventions(...),  // optional
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundShareClass>(json);
```


- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventions`
- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventionUnits`
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

