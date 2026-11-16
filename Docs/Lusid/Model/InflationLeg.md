# Finbourne.Sdk.Lusid.Model.InflationLeg

LUSID representation of an Inflation Leg.  This leg instrument is part of the InflationSwap instrument, but can also be used as a standalone instrument.  The implementation supports the following inflation leg types:  * Zero Coupon inflation leg (CPI Leg), with a single payment at maturity.  * Year on Year inflation leg  * LPI Swap Leg (capped and floored YoY)
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Required | *No description available.* |
| **BaseCPI** | **decimal?** | Optional | Optional BaseCPI, if specified it will be used in place of BaseCPI(StartDate).  This should not be required for standard inflation swaps. |
| **CalculationType** | **string** | Required | The calculation type.  ZeroCoupon is used for CPILegs where there is a single payment at maturity of  Notional * (CPI(T) / CPI(T0) - 1)  where CPI(T0) is the BaseCPI of this leg  YearOnYear is used for YoY and LPI swap legs where there is a series of annual payments  Notional * dayCount * (CPI(t) / CPI(t-1) - 1)  If a cap and floor is added to this it becomes an LPI swap leg.  Compounded is used for inflation swap legs where there is a series of annual payments  Notional * dayCount * (CPI(t) / CPI(T0) - 1)  i.e. the BaseCPI is used every year. These swaps are not as common as CPI or    IndexedCoupon is used for the coupon stream of an inflation-linked bond, where each period pays  Notional * FixedRate * dayCount * IndexRatio(t)  and IndexRatio(t) is CPI(t) / BaseCPI rounded to IndexPrecision, as on InflationLinkedBond.                Supported string (enumeration) values are: [ZeroCoupon, YearOnYear, Compounded, IndexedCoupon]. |
| **CapRate** | **decimal?** | Optional | Optional cap on a YearOnYear leg: each period&#39;s 12-month inflation rate is clamped to at most this rate before  the accrual fraction is applied, at any payment frequency, so an LPI leg caps each year at 5%. In the legs  form of an InflationSwap it is rejected on a ZeroCoupon, Compounded or IndexedCoupon leg, where it would clamp  the total change since the start. In the deprecated inflationLeg form a ZeroCoupon or Compounded cap keeps  clamping that total change, as today. |
| **FloorRate** | **decimal?** | Optional | Optional floor on a YearOnYear leg: each period&#39;s 12-month inflation rate is clamped to at least this rate  before the accrual fraction is applied, at any payment frequency, so a 0% floor stops deflation being paid.  In the legs form of an InflationSwap it is rejected on a ZeroCoupon, Compounded or IndexedCoupon leg, where it  would clamp the total change since the start. In the deprecated inflationLeg form a ZeroCoupon or Compounded  floor keeps clamping that total change, as today. |
| **InflationIndexConventions** | [InflationIndexConventions](InflationIndexConventions.md) | Required | *No description available.* |
| **Notional** | **decimal** | Required | The notional |
| **PayReceive** | **string** | Optional | PayReceive flag for the inflation leg.  This field is optional and defaults to Pay.    Supported string (enumeration) values are: [Pay, Receive]. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **FixedRate** | **decimal?** | Optional | The real coupon rate of an IndexedCoupon leg: each period pays Notional * FixedRate * dayCount * IndexRatio.  Required when CalculationType is IndexedCoupon and not allowed otherwise. |
| **BaseCPIDate** | **DateTimeOffset?** | Optional | Optional date the base CPI is observed on, with the same meaning as on InflationLinkedBond: the un-lagged  date (for a bond asset swap, the bond&#39;s dated date) whose reference CPI is the base. Defaults to the StartDate.  Ignored when BaseCPI is given. |
| **IndexPrecision** | **int** | Optional | Number of decimal places the IndexedCoupon index ratio is rounded to, as on InflationLinkedBond. Defaults to 5. |
| **PrincipalProtection** | **bool** | Optional | Whether an indexed final notional exchange is floored at par, paying max(IndexRatio, 1) times the amount, as on  InflationLinkedBond. Coupons are never floored. Defaults to true. |
| **NotionalExchangeType** | **string** | Optional | Which notional exchanges the leg makes. The start exchange pays the un-indexed amount against the leg; the  maturity exchange pays the amount times the index ratio with the leg, floored at par under PrincipalProtection.                Supported string (enumeration) values are: [None, Initial, Final, Both].  Defaults to \&quot;None\&quot; if not set. |
| **InitialExchangeAmount** | **decimal?** | Optional | The amount exchanged at the start of the leg, when NotionalExchangeType is Initial or Both. Defaults to the  notional. Never indexed. Must be non-negative. |
| **FinalExchangeAmount** | **decimal?** | Optional | The real amount exchanged at maturity, when NotionalExchangeType is Final or Both. Defaults to the notional.  Paid times the index ratio, floored at par under PrincipalProtection. Must be non-negative. |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest, WholeLoanFacility, StripBond. Default: `InstrumentTypeEnum.InflationLeg` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationLeg(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    flowConventions: new FlowConventions(...),  // required
    baseCPI: 0.0d,  // optional — Optional BaseCPI, if specified it will be used in place of BaseCPI(StartDate).  This should not be required for standard inflation swaps.
    calculationType: "...",  // required — The calculation type.  ZeroCoupon is used for CPILegs where there is a single payment at maturity of  Notional * (CPI(T) / CPI(T0) - 1)  where CPI(T0) is the BaseCPI of this leg  YearOnYear is used for YoY and LPI swap legs where there is a series of annual payments  Notional * dayCount * (CPI(t) / CPI(t-1) - 1)  If a cap and floor is added to this it becomes an LPI swap leg.  Compounded is used for inflation swap legs where there is a series of annual payments  Notional * dayCount * (CPI(t) / CPI(T0) - 1)  i.e. the BaseCPI is used every year. These swaps are not as common as CPI or    IndexedCoupon is used for the coupon stream of an inflation-linked bond, where each period pays  Notional * FixedRate * dayCount * IndexRatio(t)  and IndexRatio(t) is CPI(t) / BaseCPI rounded to IndexPrecision, as on InflationLinkedBond.                Supported string (enumeration) values are: [ZeroCoupon, YearOnYear, Compounded, IndexedCoupon].
    capRate: 0.0d,  // optional — Optional cap on a YearOnYear leg: each period&#39;s 12-month inflation rate is clamped to at most this rate before  the accrual fraction is applied, at any payment frequency, so an LPI leg caps each year at 5%. In the legs  form of an InflationSwap it is rejected on a ZeroCoupon, Compounded or IndexedCoupon leg, where it would clamp  the total change since the start. In the deprecated inflationLeg form a ZeroCoupon or Compounded cap keeps  clamping that total change, as today.
    floorRate: 0.0d,  // optional — Optional floor on a YearOnYear leg: each period&#39;s 12-month inflation rate is clamped to at least this rate  before the accrual fraction is applied, at any payment frequency, so a 0% floor stops deflation being paid.  In the legs form of an InflationSwap it is rejected on a ZeroCoupon, Compounded or IndexedCoupon leg, where it  would clamp the total change since the start. In the deprecated inflationLeg form a ZeroCoupon or Compounded  floor keeps clamping that total change, as today.
    inflationIndexConventions: new InflationIndexConventions(...),  // required
    notional: 0.0d,  // required — The notional
    payReceive: "...",  // optional — PayReceive flag for the inflation leg.  This field is optional and defaults to Pay.    Supported string (enumeration) values are: [Pay, Receive].
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    fixedRate: 0.0d,  // optional — The real coupon rate of an IndexedCoupon leg: each period pays Notional * FixedRate * dayCount * IndexRatio.  Required when CalculationType is IndexedCoupon and not allowed otherwise.
    baseCPIDate: DateTimeOffset.Now,  // optional — Optional date the base CPI is observed on, with the same meaning as on InflationLinkedBond: the un-lagged  date (for a bond asset swap, the bond&#39;s dated date) whose reference CPI is the base. Defaults to the StartDate.  Ignored when BaseCPI is given.
    indexPrecision: 0,  // optional — Number of decimal places the IndexedCoupon index ratio is rounded to, as on InflationLinkedBond. Defaults to 5.
    principalProtection: true,  // optional — Whether an indexed final notional exchange is floored at par, paying max(IndexRatio, 1) times the amount, as on  InflationLinkedBond. Coupons are never floored. Defaults to true.
    notionalExchangeType: "...",  // optional — Which notional exchanges the leg makes. The start exchange pays the un-indexed amount against the leg; the  maturity exchange pays the amount times the index ratio with the leg, floored at par under PrincipalProtection.                Supported string (enumeration) values are: [None, Initial, Final, Both].  Defaults to \&quot;None\&quot; if not set.
    initialExchangeAmount: 0.0d,  // optional — The amount exchanged at the start of the leg, when NotionalExchangeType is Initial or Both. Defaults to the  notional. Never indexed. Must be non-negative.
    finalExchangeAmount: 0.0d,  // optional — The real amount exchanged at maturity, when NotionalExchangeType is Final or Both. Defaults to the notional.  Paid times the index ratio, floored at par under PrincipalProtection. Must be non-negative.
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest, WholeLoanFacility, StripBond.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationLeg>(json);
```


- [FlowConventions](FlowConventions.md)
- [InflationIndexConventions](InflationIndexConventions.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

