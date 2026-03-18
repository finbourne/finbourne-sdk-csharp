# Finbourne.Sdk.Lusid.Model.ComplexBond

LUSID representation of a Complex Bond.  Including Floating, Fixed-to-float, Sinkable, Callable, Puttable, and Mortgage Backed Securities.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | External market codes and identifiers for the bond, e.g. ISIN. |
| **CalculationType** | **string** | Optional | The calculation type applied to the bond coupon amount. This is required for bonds that have a particular type of computing the period coupon, such as simple compounding,  irregular coupons etc.  The default CalculationType is &#x60;Standard&#x60;, which returns a coupon amount equal to Principal * Coupon Rate / Coupon Frequency. Coupon Frequency is 12M / Payment Frequency.  Payment Frequency can be 1M, 3M, 6M, 12M etc. So Coupon Frequency can be 12, 4, 2, 1 respectively.    Supported string (enumeration) values are: [Standard, DayCountCoupon, NoCalculationFloater, BrazilFixedCoupon, StandardWithCappedAccruedInterest]. |
| **Schedules** | [List&lt;Schedule&gt;](Schedule.md) | Optional | schedules. |
| **OriginalIssuePrice** | **decimal?** | Optional | The price the complex bond was issued at. This is to be entered as a percentage of par, for example a value of 98.5 would represent 98.5%. |
| **RoundingConventions** | [List&lt;RoundingConvention&gt;](RoundingConvention.md) | Optional | Rounding conventions for analytics, if any. |
| **AssetBacked** | **bool?** | Optional | If this flag is set to true, then the outstanding notional and principal repayments will be calculated based  on pool factors in the quote store. Usually AssetBacked bonds also require a RollConvention setting of   within the FlowConventions any given rates schedule (to ensure payment dates always happen on the same day  of the month) and US Agency MBSs with Pay Delay features also require their rates schedules to include an  ExDividendConfiguration to drive the lag between interest accrual and payment. |
| **AssetPoolIdentifier** | **string** | Optional | Identifier used to retrieve pool factor information about this bond from the quote store. This is typically  the bond&#39;s ISIN, but can also be ClientInternal. Please ensure you align the MarketDataKeyRule with the  correct Quote (Quote.ClientInternal.* or Quote.Isin.*) |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.ComplexBond` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplexBond(
    identifiers: ,  // optional — External market codes and identifiers for the bond, e.g. ISIN.
    calculationType: "...",  // optional — The calculation type applied to the bond coupon amount. This is required for bonds that have a particular type of computing the period coupon, such as simple compounding,  irregular coupons etc.  The default CalculationType is &#x60;Standard&#x60;, which returns a coupon amount equal to Principal * Coupon Rate / Coupon Frequency. Coupon Frequency is 12M / Payment Frequency.  Payment Frequency can be 1M, 3M, 6M, 12M etc. So Coupon Frequency can be 12, 4, 2, 1 respectively.    Supported string (enumeration) values are: [Standard, DayCountCoupon, NoCalculationFloater, BrazilFixedCoupon, StandardWithCappedAccruedInterest].
    schedules: new List<Schedule>(),  // optional — schedules.
    originalIssuePrice: 0.0d,  // optional — The price the complex bond was issued at. This is to be entered as a percentage of par, for example a value of 98.5 would represent 98.5%.
    roundingConventions: new List<RoundingConvention>(),  // optional — Rounding conventions for analytics, if any.
    assetBacked: true,  // optional — If this flag is set to true, then the outstanding notional and principal repayments will be calculated based  on pool factors in the quote store. Usually AssetBacked bonds also require a RollConvention setting of   within the FlowConventions any given rates schedule (to ensure payment dates always happen on the same day  of the month) and US Agency MBSs with Pay Delay features also require their rates schedules to include an  ExDividendConfiguration to drive the lag between interest accrual and payment.
    assetPoolIdentifier: "...",  // optional — Identifier used to retrieve pool factor information about this bond from the quote store. This is typically  the bond&#39;s ISIN, but can also be ClientInternal. Please ensure you align the MarketDataKeyRule with the  correct Quote (Quote.ClientInternal.* or Quote.Isin.*)
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
var instance = JsonConvert.DeserializeObject<ComplexBond>(json);
```


- [Schedule](Schedule.md) — used in `Schedules`
- [RoundingConvention](RoundingConvention.md) — used in `RoundingConventions`
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

