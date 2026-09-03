# Finbourne.Sdk.Lusid.Model.PreferredShare

LUSID representation of a preferred (preference) share: an equity-classified security that pays an  intrinsic, schedule-driven dividend of DividendRate x ParValue. The schedule is perpetual unless a  MaturityDate is supplied, in which case the share redeems at par on that date.  It carries Bond's shape rather than Equity's - StartDate, MaturityDate and FlowConventions are real,  settable properties - but its dividend is a flat amount per period rather than a day-count-weighted  coupon, and its schedule can be open ended.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is the first dividend accrual start date. |
| **MaturityDate** | **DateTimeOffset** | Optional | The redemption date of a dated series. Omit it for a perpetual, which is the default: there is  no sentinel date for the client to supply, and a distant date such as one in the year 9999 is  taken literally and schedules a par redemption on it. |
| **FlowConventions** | [FlowConventions](FlowConventions.md) | Required | *No description available.* |
| **Identifiers** | [PreferredShareAllOfIdentifiers](PreferredShareAllOfIdentifiers.md) | Optional | *No description available.* |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. It is the currency of the dividends and of ParValue. |
| **CallSchedule** | [OptionalitySchedule](OptionalitySchedule.md) | Optional | *No description available.* |
| **CfiCode** | **string** | Optional | The ISO 10962 CFI code, if the client stores one. Free text, not validated against the standard. |
| **ConversionSchedule** | [BondConversionSchedule](BondConversionSchedule.md) | Optional | *No description available.* |
| **DividendRate** | **decimal** | Required | The fixed annualised dividend rate applied to ParValue, so 0.06 is 6%. A scalar for the life of  the share: there is no rate reset, so a fixed-to-floating preferred carries the rate for the  current period and is re-upserted at each reset. |
| **FirstDividendDate** | **DateTimeOffset?** | Optional | Anchors a short or long first dividend period. Omitted means no stub. |
| **IsCumulative** | **bool** | Required | Whether a missed dividend accumulates as arrears rather than being forfeited. The client must  state it; there is no default. |
| **LotSize** | **int** | Optional | The minimum number of shares that can be traded at once. Microstructure only: it has no effect  on valuation or on cash flows. Defaults to 1. |
| **ParValue** | **decimal** | Required | The liquidation preference per share. It is the base for the dividend, for the call strike and  for the redemption amount. It is not a price multiplier. |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare. Default: `InstrumentTypeEnum.PreferredShare` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreferredShare(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is the first dividend accrual start date.
    maturityDate: DateTimeOffset.Now,  // optional — The redemption date of a dated series. Omit it for a perpetual, which is the default: there is  no sentinel date for the client to supply, and a distant date such as one in the year 9999 is  taken literally and schedules a par redemption on it.
    flowConventions: new FlowConventions(...),  // required
    identifiers: new PreferredShareAllOfIdentifiers(...),  // optional
    domCcy: "...",  // required — The domestic currency of the instrument. It is the currency of the dividends and of ParValue.
    callSchedule: new OptionalitySchedule(...),  // optional
    cfiCode: "...",  // optional — The ISO 10962 CFI code, if the client stores one. Free text, not validated against the standard.
    conversionSchedule: new BondConversionSchedule(...),  // optional
    dividendRate: 0.0d,  // required — The fixed annualised dividend rate applied to ParValue, so 0.06 is 6%. A scalar for the life of  the share: there is no rate reset, so a fixed-to-floating preferred carries the rate for the  current period and is re-upserted at each reset.
    firstDividendDate: DateTimeOffset.Now,  // optional — Anchors a short or long first dividend period. Omitted means no stub.
    isCumulative: true,  // required — Whether a missed dividend accumulates as arrears rather than being forfeited. The client must  state it; there is no default.
    lotSize: 0,  // optional — The minimum number of shares that can be traded at once. Microstructure only: it has no effect  on valuation or on cash flows. Defaults to 1.
    parValue: 0.0d,  // required — The liquidation preference per share. It is the base for the dividend, for the call strike and  for the redemption amount. It is not a price multiplier.
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreferredShare>(json);
```


- [FlowConventions](FlowConventions.md)
- [PreferredShareAllOfIdentifiers](PreferredShareAllOfIdentifiers.md)
- [OptionalitySchedule](OptionalitySchedule.md)
- [BondConversionSchedule](BondConversionSchedule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

