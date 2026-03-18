# Finbourne.Sdk.Lusid.Model.InflationLinkedBond

Inflation Linked Bond.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the bond. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Required | *No description available.* |
| **InflationIndexConventions** | [InflationIndexConventions](InflationIndexConventions.md) | Required | *No description available.* |
| **CouponRate** | **decimal** | Required | Simple coupon rate. |
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Optional | External market codes and identifiers for the bond, e.g. ISIN. |
| **BaseCPI** | **decimal?** | Optional | BaseCPI value. This is optional, if not provided the BaseCPI value will be calculated from the BaseCPIDate,  if that too is not present the StartDate will be used.                If provided then this value will always set the BaseCPI on this bond.                The BaseCPI of an inflation linked bond is calculated using the following logic:  - If a BaseCPI value is provided, this is used.  - Otherwise, if BaseCPIDate is provided, the CPI for this date is calculated and used.  - Otherwise, the CPI for the StartDate is calculated and used.                Note that if both BaseCPI and BaseCPIDate are set, the BaseCPI value will be used and the BaseCPIDate  will be ignored but can still be added for informative purposes.                Some bonds are issued with a BaseCPI date that does not correspond to the StartDate CPI value, in this  case the value should be provided here or with the BaseCPIDate. |
| **BaseCPIDate** | **DateTimeOffset?** | Optional | BaseCPIDate. This is optional. Gives the date that the BaseCPI is calculated for.                Note this is an un-lagged date (similar to StartDate) so the Bond ObservationLag will  be applied to this date when calculating the CPI.                The BaseCPI of an inflation linked bond is calculated using the following logic:  - If a BaseCPI value is provided, this is used.  - Otherwise, if BaseCPIDate is provided, the CPI for this date is calculated and used.  - Otherwise, the CPI for the StartDate is calculated and used.                Note that if both BaseCPI and BaseCPIDate are set, the BaseCPI value will be used and the BaseCPIDate  will be ignored but can still be added for informative purposes.                Some bonds are issued with a BaseCPI date that does not correspond to the StartDate CPI value, in this  case the value should be provided here or with the actual BaseCPI. |
| **CalculationType** | **string** | Optional | The calculation type applied to the bond coupon and principal amount.  The default CalculationType is &#x60;Standard&#x60;.    Supported string (enumeration) values are: [Standard, Quarterly, Ratio, Brazil, StandardAccruedOnly, RatioAccruedOnly, StandardWithCappedAccruedInterest]. |
| **ExDividendDays** | **int?** | Optional | Number of Good Business Days before the next coupon payment, in which the bond goes ex-dividend. |
| **IndexPrecision** | **int** | Optional | Number of decimal places used to round IndexRatio. This defaults to 5 if not set. |
| **Principal** | **decimal** | Required | The face-value or principal for the bond at outset. |
| **PrincipalProtection** | **bool** | Optional | If true then the principal is protected in that the redemption amount will be at least the face value (Principal).  This is typically set to true for inflation linked bonds issued by the United States and France (for example).  This is typically set to false for inflation linked bonds issued by the United Kingdom (post 2005).  For other sovereigns this can vary from issue to issue.  If not set this property defaults to true.  This is sometimes referred to as Deflation protection or an inflation floor of 0%. |
| **StubType** | **string** | Optional | StubType. Most Inflation linked bonds have a ShortFront stub type so this is the default, however in some cases  with a long front stub LongFront should be selected.  StubType Both is not supported for InflationLinkedBonds.    Supported string (enumeration) values are: [ShortFront, ShortBack, LongBack, LongFront, Both]. |
| **RoundingConventions** | [List&lt;RoundingConvention&gt;](RoundingConvention.md) | Optional | Rounding conventions for analytics, if any. |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **OriginalIssuePrice** | **decimal?** | Optional | The price the bond was issued at. This is to be entered as a percentage of par, for example a value of 98.5 would represent 98.5%. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.InflationLinkedBond` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationLinkedBond(
    startDate: DateTimeOffset.Now,  // required — The start date of the bond.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    flowConventions: new FlowConventions(...),  // required
    inflationIndexConventions: new InflationIndexConventions(...),  // required
    couponRate: 0.0d,  // required — Simple coupon rate.
    identifiers: ,  // optional — External market codes and identifiers for the bond, e.g. ISIN.
    baseCPI: 0.0d,  // optional — BaseCPI value. This is optional, if not provided the BaseCPI value will be calculated from the BaseCPIDate,  if that too is not present the StartDate will be used.                If provided then this value will always set the BaseCPI on this bond.                The BaseCPI of an inflation linked bond is calculated using the following logic:  - If a BaseCPI value is provided, this is used.  - Otherwise, if BaseCPIDate is provided, the CPI for this date is calculated and used.  - Otherwise, the CPI for the StartDate is calculated and used.                Note that if both BaseCPI and BaseCPIDate are set, the BaseCPI value will be used and the BaseCPIDate  will be ignored but can still be added for informative purposes.                Some bonds are issued with a BaseCPI date that does not correspond to the StartDate CPI value, in this  case the value should be provided here or with the BaseCPIDate.
    baseCPIDate: DateTimeOffset.Now,  // optional — BaseCPIDate. This is optional. Gives the date that the BaseCPI is calculated for.                Note this is an un-lagged date (similar to StartDate) so the Bond ObservationLag will  be applied to this date when calculating the CPI.                The BaseCPI of an inflation linked bond is calculated using the following logic:  - If a BaseCPI value is provided, this is used.  - Otherwise, if BaseCPIDate is provided, the CPI for this date is calculated and used.  - Otherwise, the CPI for the StartDate is calculated and used.                Note that if both BaseCPI and BaseCPIDate are set, the BaseCPI value will be used and the BaseCPIDate  will be ignored but can still be added for informative purposes.                Some bonds are issued with a BaseCPI date that does not correspond to the StartDate CPI value, in this  case the value should be provided here or with the actual BaseCPI.
    calculationType: "...",  // optional — The calculation type applied to the bond coupon and principal amount.  The default CalculationType is &#x60;Standard&#x60;.    Supported string (enumeration) values are: [Standard, Quarterly, Ratio, Brazil, StandardAccruedOnly, RatioAccruedOnly, StandardWithCappedAccruedInterest].
    exDividendDays: 0,  // optional — Number of Good Business Days before the next coupon payment, in which the bond goes ex-dividend.
    indexPrecision: 0,  // optional — Number of decimal places used to round IndexRatio. This defaults to 5 if not set.
    principal: 0.0d,  // required — The face-value or principal for the bond at outset.
    principalProtection: true,  // optional — If true then the principal is protected in that the redemption amount will be at least the face value (Principal).  This is typically set to true for inflation linked bonds issued by the United States and France (for example).  This is typically set to false for inflation linked bonds issued by the United Kingdom (post 2005).  For other sovereigns this can vary from issue to issue.  If not set this property defaults to true.  This is sometimes referred to as Deflation protection or an inflation floor of 0%.
    stubType: "...",  // optional — StubType. Most Inflation linked bonds have a ShortFront stub type so this is the default, however in some cases  with a long front stub LongFront should be selected.  StubType Both is not supported for InflationLinkedBonds.    Supported string (enumeration) values are: [ShortFront, ShortBack, LongBack, LongFront, Both].
    roundingConventions: new List<RoundingConvention>(),  // optional — Rounding conventions for analytics, if any.
    tradingConventions: new TradingConventions(...),  // optional
    originalIssuePrice: 0.0d,  // optional — The price the bond was issued at. This is to be entered as a percentage of par, for example a value of 98.5 would represent 98.5%.
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
var instance = JsonConvert.DeserializeObject<InflationLinkedBond>(json);
```


- [FlowConventions](FlowConventions.md)
- [InflationIndexConventions](InflationIndexConventions.md)
- [RoundingConvention](RoundingConvention.md) — used in `RoundingConventions`
- [TradingConventions](TradingConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

