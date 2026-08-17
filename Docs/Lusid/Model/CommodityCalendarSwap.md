# Finbourne.Sdk.Lusid.Model.CommodityCalendarSwap

LUSID representation of an OTC bilateral commodity calendar swap.  The swap is a strip of periodic commodity forwards struck at a single strike, cash-settled at each  period end against a calendar-average commodity price, with the position amortising as each period  settles. Its present value is Quantity x Price, where the price is supplied externally pre-netted  (the calendar average minus strike) via the quote store. LUSID calculates no analytics for this  instrument, and it can only be priced by lookup pricing. The periodic settlement schedule is  currently stored and validated only; only the maturity lifecycle event is generated.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **Strike** | **decimal?** | Optional | Agreed price per unit at trade inception. Reference only - not used in the market value  calculation, which consumes the pre-netted price from the quote store. |
| **CommodityCalendarSchedule** | [CommodityCalendarSchedule](CommodityCalendarSchedule.md) | Required | *No description available.* |
| **DeliveryType** | **string** | Required | Whether the swap settles in cash or through physical delivery of the underlying.  Only cash settlement is supported.                Supported string (enumeration) values are: [Cash, Physical]. Available values: Cash, Physical. |
| **QuantityPerPeriod** | **decimal** | Required | The notional commodity quantity referenced by each settlement period. The initial holding is  this quantity multiplied by the number of periods, stepping down by this quantity as each  period settles. |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap. Default: `InstrumentTypeEnum.CommodityCalendarSwap` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CommodityCalendarSwap(
    domCcy: "...",  // required — The domestic currency of the instrument.
    strike: 0.0d,  // optional — Agreed price per unit at trade inception. Reference only - not used in the market value  calculation, which consumes the pre-netted price from the quote store.
    commodityCalendarSchedule: new CommodityCalendarSchedule(...),  // required
    deliveryType: "...",  // required — Whether the swap settles in cash or through physical delivery of the underlying.  Only cash settlement is supported.                Supported string (enumeration) values are: [Cash, Physical]. Available values: Cash, Physical.
    quantityPerPeriod: 0.0d,  // required — The notional commodity quantity referenced by each settlement period. The initial holding is  this quantity multiplied by the number of periods, stepping down by this quantity as each  period settles.
    underlying: new LusidInstrument(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CommodityCalendarSwap>(json);
```


- [CommodityCalendarSchedule](CommodityCalendarSchedule.md)
- [LusidInstrument](LusidInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

