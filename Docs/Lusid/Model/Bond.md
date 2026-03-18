# Finbourne.Sdk.Lusid.Model.Bond

LUSID representation of a Vanilla Fixed Rate Bond.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The Start date of the bond, this is normally when accrual of the first coupon begins. |
| **MaturityDate** | **DateTimeOffset** | Required | The Maturity date of the bond, this is when the last coupon accrual period ends.  Note that while most bonds have their last payment on this date there are some cases where the final payment is the next working day. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. This should be the same as the Currency set on the FlowConventions. |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Required | *No description available.* |
| **Principal** | **decimal** | Required | The face-value or principal for the bond at outset.  This might be reduced through its lifetime in the event of amortisation or similar. |
| **CouponRate** | **decimal** | Required | Simple coupon rate. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | External market codes and identifiers for the bond, e.g. ISIN. |
| **ExDividendDays** | **int?** | Optional | Optional. Number of calendar days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, then there is no ex-dividend period.                NOTE: This field is deprecated.  If you wish to set the ExDividendDays on a bond, please use the ExDividendConfiguration. |
| **InitialCouponDate** | **DateTimeOffset?** | Optional | Optional and to be DEPRECATED. If set, this is the date at which the bond begins to accrue interest. Instead, this information should be entered in the field StartDate. |
| **FirstCouponPayDate** | **DateTimeOffset?** | Optional | The date that the first coupon of the bond is paid. This is required for bonds that have a long first coupon or short first coupon. The first coupon pay date is used  as an anchor to compare with the start date and determine if this is a long/short coupon period. |
| **CalculationType** | **string** | Optional | The calculation type applied to the bond coupon amount. This is required for bonds that have a particular type of computing the period coupon, such as simple compounding,  irregular coupons etc.  The default CalculationType is &#x60;Standard&#x60;, which returns a coupon amount equal to Principal * Coupon Rate / Coupon Frequency. Coupon Frequency is 12M / Payment Frequency.  Payment Frequency can be 1M, 3M, 6M, 12M etc. So Coupon Frequency can be 12, 4, 2, 1 respectively.    Supported string (enumeration) values are: [Standard, DayCountCoupon, NoCalculationFloater, BrazilFixedCoupon, StandardWithCappedAccruedInterest]. |
| **RoundingConventions** | [List&lt;RoundingConvention&gt;](RoundingConvention.md) | Optional | Rounding conventions for analytics, if any. |
| **ExDividendConfiguration** | [ExDividendConfiguration](ExDividendConfiguration.md) | Optional | *No description available.* |
| **OriginalIssuePrice** | **decimal?** | Optional | The price the bond was issued at. This is to be entered as a percentage of par, for example a value of 98.5 would represent 98.5%. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.Bond` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Bond(
    startDate: DateTimeOffset.Now,  // required — The Start date of the bond, this is normally when accrual of the first coupon begins.
    maturityDate: DateTimeOffset.Now,  // required — The Maturity date of the bond, this is when the last coupon accrual period ends.  Note that while most bonds have their last payment on this date there are some cases where the final payment is the next working day.
    domCcy: "...",  // required — The domestic currency of the instrument. This should be the same as the Currency set on the FlowConventions.
    flowConventions: new FlowConventions(...),  // required
    principal: 0.0d,  // required — The face-value or principal for the bond at outset.  This might be reduced through its lifetime in the event of amortisation or similar.
    couponRate: 0.0d,  // required — Simple coupon rate.
    identifiers: ,  // optional — External market codes and identifiers for the bond, e.g. ISIN.
    exDividendDays: 0,  // optional — Optional. Number of calendar days in the ex-dividend period.  If the settlement date falls in the ex-dividend period then the coupon paid is zero and the accrued interest is negative.  If set, this must be a non-negative number.  If not set, or set to 0, then there is no ex-dividend period.                NOTE: This field is deprecated.  If you wish to set the ExDividendDays on a bond, please use the ExDividendConfiguration.
    initialCouponDate: DateTimeOffset.Now,  // optional — Optional and to be DEPRECATED. If set, this is the date at which the bond begins to accrue interest. Instead, this information should be entered in the field StartDate.
    firstCouponPayDate: DateTimeOffset.Now,  // optional — The date that the first coupon of the bond is paid. This is required for bonds that have a long first coupon or short first coupon. The first coupon pay date is used  as an anchor to compare with the start date and determine if this is a long/short coupon period.
    calculationType: "...",  // optional — The calculation type applied to the bond coupon amount. This is required for bonds that have a particular type of computing the period coupon, such as simple compounding,  irregular coupons etc.  The default CalculationType is &#x60;Standard&#x60;, which returns a coupon amount equal to Principal * Coupon Rate / Coupon Frequency. Coupon Frequency is 12M / Payment Frequency.  Payment Frequency can be 1M, 3M, 6M, 12M etc. So Coupon Frequency can be 12, 4, 2, 1 respectively.    Supported string (enumeration) values are: [Standard, DayCountCoupon, NoCalculationFloater, BrazilFixedCoupon, StandardWithCappedAccruedInterest].
    roundingConventions: new List<RoundingConvention>(),  // optional — Rounding conventions for analytics, if any.
    exDividendConfiguration: new ExDividendConfiguration(...),  // optional
    originalIssuePrice: 0.0d,  // optional — The price the bond was issued at. This is to be entered as a percentage of par, for example a value of 98.5 would represent 98.5%.
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
var instance = JsonConvert.DeserializeObject<Bond>(json);
```


- [FlowConventions](FlowConventions.md)
- [RoundingConvention](RoundingConvention.md) — used in `RoundingConventions`
- [ExDividendConfiguration](ExDividendConfiguration.md)
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

