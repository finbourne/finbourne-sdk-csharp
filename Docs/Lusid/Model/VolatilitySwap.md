# Finbourne.Sdk.Lusid.Model.VolatilitySwap

LUSID representation of an OTC variance or volatility swap. A single-leg, bullet instrument with no  schedule, no interim cashflows and no accrual. Its market value is supplied by lookup pricing as  Quantity x Notional x Price / PriceDenominator, where the unit price arrives via the quote store  already netted against the strike. The variance/volatility distinction is expressed purely through the  scalar (1 for volatility swaps, 100 for variance swaps) and instrument  properties; it is not a first-class field.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument, in which the looked-up price and market value are  denominated. Quotes supplied in a minor unit of this currency (e.g. GBp) are re-denominated  to it by the lookup pricer. |
| **Strike** | **decimal?** | Optional | The variance or volatility strike agreed at trade date, stored for reference only.  Not used in valuation or close-out. |
| **Notional** | **decimal** | Required | The agreed notional for the swap. The sign conveys direction (a negative notional held long  produces a negative market value). |
| **PriceDenominator** | **int** | Required | Scalar divisor applied in the market value calculation:  MktVal &#x3D; Quantity x Notional x Price / PriceDenominator.  1 for volatility swaps (VOLS) and 100 for variance swaps (VARS). Must be positive. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **Underlying** | **string** | Optional | Free-text reference label identifying the underlying index or asset (e.g. &#39;SPX&#39;, &#39;SX5E&#39;, &#39;KOSPI2&#39;).  Reference only; not used in valuation. |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption. Default: `InstrumentTypeEnum.VolatilitySwap` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new VolatilitySwap(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    domCcy: "...",  // required — The domestic currency of the instrument, in which the looked-up price and market value are  denominated. Quotes supplied in a minor unit of this currency (e.g. GBp) are re-denominated  to it by the lookup pricer.
    strike: 0.0d,  // optional — The variance or volatility strike agreed at trade date, stored for reference only.  Not used in valuation or close-out.
    notional: 0.0d,  // required — The agreed notional for the swap. The sign conveys direction (a negative notional held long  produces a negative market value).
    priceDenominator: 0,  // required — Scalar divisor applied in the market value calculation:  MktVal &#x3D; Quantity x Notional x Price / PriceDenominator.  1 for volatility swaps (VOLS) and 100 for variance swaps (VARS). Must be positive.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    underlying: "...",  // optional — Free-text reference label identifying the underlying index or asset (e.g. &#39;SPX&#39;, &#39;SX5E&#39;, &#39;KOSPI2&#39;).  Reference only; not used in valuation.
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VolatilitySwap>(json);
```


- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

