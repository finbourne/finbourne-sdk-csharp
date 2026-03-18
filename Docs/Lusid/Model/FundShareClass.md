# Finbourne.Sdk.Lusid.Model.FundShareClass

LUSID representation of a FundShareClass.  A ShareClass represents a pool of shares, held by investors, within a fund.   A ShareClass can represent a differing investment approach by either Fees,   Income, Currency Risk and Investor type.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShortCode** | **string** | Required | A short identifier, unique across a single fund, usually made up of the ShareClass components. Eg \&quot;A Accumulation Euro Hedged Class\&quot; could become \&quot;A Acc H EUR\&quot;. |
| **FundShareClassType** | **string** | Required | The type of distribution that the ShareClass will calculate. Can be either &#39;Income&#39; or &#39;Accumulation&#39; - Income classes will pay out and Accumulation classes will retain their ShareClass attributable income.    Supported string (enumeration) values are: [Income, Accumulation]. |
| **DistributionPaymentType** | **string** | Required | The tax treatment applied to any distributions calculated within the ShareClass. Can be either &#39;Net&#39; (Distribution Calculated net of tax) or &#39;Gross&#39; (Distribution calculated gross of tax).    Supported string (enumeration) values are: [Gross, Net]. |
| **Hedging** | **string** | Required | A flag to indicate the ShareClass is operating currency hedging as a means to limit currency risk as part of it&#39;s investment strategy.    Supported string (enumeration) values are: [Invalid, None, ApplyHedging]. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **RoundingConventions** | [List&lt;SimpleRoundingConvention&gt;](SimpleRoundingConvention.md) | Optional | Rounding Convention used for the FundShareClass quotes |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.FundShareClass` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundShareClass(
    shortCode: "...",  // required — A short identifier, unique across a single fund, usually made up of the ShareClass components. Eg \&quot;A Accumulation Euro Hedged Class\&quot; could become \&quot;A Acc H EUR\&quot;.
    fundShareClassType: "...",  // required — The type of distribution that the ShareClass will calculate. Can be either &#39;Income&#39; or &#39;Accumulation&#39; - Income classes will pay out and Accumulation classes will retain their ShareClass attributable income.    Supported string (enumeration) values are: [Income, Accumulation].
    distributionPaymentType: "...",  // required — The tax treatment applied to any distributions calculated within the ShareClass. Can be either &#39;Net&#39; (Distribution Calculated net of tax) or &#39;Gross&#39; (Distribution calculated gross of tax).    Supported string (enumeration) values are: [Gross, Net].
    hedging: "...",  // required — A flag to indicate the ShareClass is operating currency hedging as a means to limit currency risk as part of it&#39;s investment strategy.    Supported string (enumeration) values are: [Invalid, None, ApplyHedging].
    domCcy: "...",  // required — The domestic currency of the instrument.
    roundingConventions: new List<SimpleRoundingConvention>(),  // optional — Rounding Convention used for the FundShareClass quotes
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
var instance = JsonConvert.DeserializeObject<FundShareClass>(json);
```


- [SimpleRoundingConvention](SimpleRoundingConvention.md) — used in `RoundingConventions`
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

