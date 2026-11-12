# Finbourne.Sdk.Lusid.Model.StripBond

A stripped bond: an entitlement to one side of a mastered parent bond's cash flows. An interest-only strip  receives the interest the parent pays, on a notional that runs down with the parent's principal; a  principal-only strip receives the parent's principal and none of its interest. The strip carries no schedule,  coupon or conventions of its own: it points at the parent through a MasteredInstrument and reads the parent's  cash flows, pool factor, dates and conventions from the parent's live definition, so a re-upsert of the parent  reaches every strip on it. One unit of a strip is one unit of the parent's original face.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AllowNegativeYield** | **bool?** | Optional | Whether a negative effective yield books negative income. Null means false: a negative effective yield is  then applied as zero, so the whole receipt returns capital. |
| **StripType** | **string** | Required | Which side of the parent&#39;s flows the strip receives: InterestOnly receives the parent&#39;s interest,  PrincipalOnly receives the parent&#39;s principal.                Supported string (enumeration) values are: [InterestOnly, PrincipalOnly]. Available values: InterestOnly, PrincipalOnly. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Required | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest, WholeLoanFacility, StripBond. Default: `InstrumentTypeEnum.StripBond` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StripBond(
    allowNegativeYield: true,  // optional — Whether a negative effective yield books negative income. Null means false: a negative effective yield is  then applied as zero, so the whole receipt returns capital.
    stripType: "...",  // required — Which side of the parent&#39;s flows the strip receives: InterestOnly receives the parent&#39;s interest,  PrincipalOnly receives the parent&#39;s principal.                Supported string (enumeration) values are: [InterestOnly, PrincipalOnly]. Available values: InterestOnly, PrincipalOnly.
    tradingConventions: new TradingConventions(...),  // optional
    underlying: new LusidInstrument(...),  // required
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest, WholeLoanFacility, StripBond.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StripBond>(json);
```


- [TradingConventions](TradingConventions.md)
- [LusidInstrument](LusidInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

