# Finbourne.Sdk.Lusid.Model.FxForward

LUSID representation of an FX Forward.  Including FX Spot and Non-Deliverable Forwards.                This instrument has multiple legs, to see how legs are used in LUSID see [How does LUSID handle instrument legs?](https://support.lusid.com/docs/how-does-lusid-handle-instrument-legs).                | Leg Index | Leg Identifier | Description |  | - -- -- -- -- | - -- -- -- -- -- -- - | - -- -- -- -- -- |  | 1 | DomesticLeg | Cash flows in the domestic currency of the forward. |  | 2 | ForeignLeg | Cash flows in the foreign currency of the forward (not present for non-deliverable forwards). |
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **DomAmount** | **decimal** | Optional | The amount that is to be paid in the domestic currency on the maturity date.  Required unless isPooled is set. On a pooled FX forward the domestic amount is the contract size and  not a traded amount: leave it absent and it is populated as one, so that holding units are amounts of  the domestic currency. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **FgnAmount** | **decimal** | Optional | The amount that is to be paid in the foreign currency on the maturity date.  Required unless isPooled is set. On a pooled FX forward it must be absent or zero, because the whole  foreign consideration is carried by the transactions booked against the pool. |
| **FgnCcy** | **string** | Required | The foreign (other) currency of the instrument. In the NDF case, only payments are made in the domestic currency.  For the outright forward, currencies are exchanged. |
| **RefSpotRate** | **decimal** | Optional | The reference Fx Spot rate for currency pair Foreign-Domestic that was seen on the trade start date (time). |
| **IsNdf** | **bool** | Optional | Is the contract an Fx-Forward of \&quot;Non-Deliverable\&quot; type, meaning a single payment in the domestic currency based on the change in fx-rate vs  a reference rate is used.  Defaults to false if not set. |
| **FixingDate** | **DateTimeOffset** | Optional | The fixing date. |
| **SettlementCcy** | **string** | Optional | The settlement currency.  If provided, present value will be calculated in settlement currency, otherwise the domestic currency. Applies only to non-deliverable FX Forwards. |
| **BookedAsSpot** | **bool** | Optional | Boolean flag for FX Forward transactions booked with Spot settlement. This will default to False if not provided.  For information purposes only, this does not impact LUSID valuation, analytics, cashflows or events, but may be used by third party vendors. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **IsPooled** | **bool** | Optional | Declares the contract to be a pool, carrying no traded amounts of its own. A pool is defined once for a  currency pair and maturity date and traded repeatedly at different rates, so the traded amounts are carried  by the transactions booked against it rather than by the instrument. The domestic amount of a pool is  therefore the contract size and not a traded amount, and is pinned to one so that holding units are amounts  of the domestic currency; the foreign amount and the reference spot rate must be absent, because the whole  foreign consideration is carried by the transaction.                Orientation is part of a pool&#39;s identity: the domestic currency is the unit currency and the foreign  currency the consideration currency, so a USD/JPY pool and a JPY/USD pool are distinct instruments, and  transactions must be booked in the pool&#39;s own direction (transaction currency equal to the domestic  currency, settlement currency equal to the foreign currency). This will default to False if not provided. |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest. Default: `InstrumentTypeEnum.FxForward` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForward(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    domAmount: 0.0d,  // optional — The amount that is to be paid in the domestic currency on the maturity date.  Required unless isPooled is set. On a pooled FX forward the domestic amount is the contract size and  not a traded amount: leave it absent and it is populated as one, so that holding units are amounts of  the domestic currency.
    domCcy: "...",  // required — The domestic currency of the instrument.
    fgnAmount: 0.0d,  // optional — The amount that is to be paid in the foreign currency on the maturity date.  Required unless isPooled is set. On a pooled FX forward it must be absent or zero, because the whole  foreign consideration is carried by the transactions booked against the pool.
    fgnCcy: "...",  // required — The foreign (other) currency of the instrument. In the NDF case, only payments are made in the domestic currency.  For the outright forward, currencies are exchanged.
    refSpotRate: 0.0d,  // optional — The reference Fx Spot rate for currency pair Foreign-Domestic that was seen on the trade start date (time).
    isNdf: true,  // optional — Is the contract an Fx-Forward of \&quot;Non-Deliverable\&quot; type, meaning a single payment in the domestic currency based on the change in fx-rate vs  a reference rate is used.  Defaults to false if not set.
    fixingDate: DateTimeOffset.Now,  // optional — The fixing date.
    settlementCcy: "...",  // optional — The settlement currency.  If provided, present value will be calculated in settlement currency, otherwise the domestic currency. Applies only to non-deliverable FX Forwards.
    bookedAsSpot: true,  // optional — Boolean flag for FX Forward transactions booked with Spot settlement. This will default to False if not provided.  For information purposes only, this does not impact LUSID valuation, analytics, cashflows or events, but may be used by third party vendors.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    isPooled: true,  // optional — Declares the contract to be a pool, carrying no traded amounts of its own. A pool is defined once for a  currency pair and maturity date and traded repeatedly at different rates, so the traded amounts are carried  by the transactions booked against it rather than by the instrument. The domestic amount of a pool is  therefore the contract size and not a traded amount, and is pinned to one so that holding units are amounts  of the domestic currency; the foreign amount and the reference spot rate must be absent, because the whole  foreign consideration is carried by the transaction.                Orientation is part of a pool&#39;s identity: the domestic currency is the unit currency and the foreign  currency the consideration currency, so a USD/JPY pool and a JPY/USD pool are distinct instruments, and  transactions must be booked in the pool&#39;s own direction (transaction currency equal to the domestic  currency, settlement currency equal to the foreign currency). This will default to False if not provided.
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxForward>(json);
```


- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

