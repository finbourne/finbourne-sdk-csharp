# Finbourne.Sdk.Lusid.Model.TenderEvent

Tender Event (TEND).
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnnouncementDate** | **DateTimeOffset?** | Optional | The date the tender is announced. |
| **ExDate** | **DateTimeOffset** | Optional | The ex date (entitlement date) of the event. |
| **RecordDate** | **DateTimeOffset?** | Optional | Date you have to be the holder of record in order to participate in the tender. |
| **PaymentDate** | **DateTimeOffset** | Optional | The payment date of the event. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | The cash price paid in lieu of fractionalUnits. |
| **FractionalUnitsCashCurrency** | **string** | Optional | The currency of the cash paid in lieu of fractionalUnits. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | List of possible SecurityOfferElections for this event. |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible CashAndSecurityOfferElections for this event. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | List of possible CashOfferElections for this event. |
| **OfferType** | **string** | Optional | Informational ISO 20022 OfferTp indicator (e.g. \&quot;ACPR\&quot;). Optional. No calculation impact. |
| **AccruedInterestPerUnit** | **decimal?** | Optional | Optional per-unit accrued interest on the tendered face, from the last coupon date up to  (but excluding) PaymentDate. Bond instrument types only. If left empty, analytics-core  resolves it at event time from the bond&#39;s coupon schedule and market data. |
| **MinPieceSize** | **decimal?** | Optional | Bond-specific minimum instructable face amount. Optional. Must be strictly positive when set. |
| **MinIncrement** | **decimal?** | Optional | Bond-specific increment above MinPieceSize. Optional. When set, MinPieceSize must also be set.  Must be strictly positive. |
| **ProrationRate** | **decimal** | Optional | Proration applied when the offer is oversubscribed. Defaults to 1 if not set.  Must be greater than 0 and less than or equal to 1. Default: `1D` |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | Account-servicer SLA deadline for holder instruction. Optional at the DTO layer;  required under Voluntary participation on bond instrument types. |
| **MarketDeadlineDate** | **DateTimeOffset?** | Optional | Offeror&#39;s-agent deadline for holder instruction. Optional at the DTO layer;  required under Voluntary participation on bond instrument types. |
| **EarlyResponseDeadline** | **DateTimeOffset?** | Optional | Optional early-tender deadline. When set, must be on or before ResponseDeadlineDate. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent. Default: `InstrumentEventTypeEnum.TenderEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TenderEvent(
    announcementDate: DateTimeOffset.Now,  // optional — The date the tender is announced.
    exDate: DateTimeOffset.Now,  // optional — The ex date (entitlement date) of the event.
    recordDate: DateTimeOffset.Now,  // optional — Date you have to be the holder of record in order to participate in the tender.
    paymentDate: DateTimeOffset.Now,  // optional — The payment date of the event.
    newInstrument: new NewInstrument(...),  // required
    fractionalUnitsCashPrice: 0.0d,  // optional — The cash price paid in lieu of fractionalUnits.
    fractionalUnitsCashCurrency: "...",  // optional — The currency of the cash paid in lieu of fractionalUnits.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — List of possible SecurityOfferElections for this event.
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible CashAndSecurityOfferElections for this event.
    cashOfferElections: new List<CashOfferElection>(),  // optional — List of possible CashOfferElections for this event.
    offerType: "...",  // optional — Informational ISO 20022 OfferTp indicator (e.g. \&quot;ACPR\&quot;). Optional. No calculation impact.
    accruedInterestPerUnit: 0.0d,  // optional — Optional per-unit accrued interest on the tendered face, from the last coupon date up to  (but excluding) PaymentDate. Bond instrument types only. If left empty, analytics-core  resolves it at event time from the bond&#39;s coupon schedule and market data.
    minPieceSize: 0.0d,  // optional — Bond-specific minimum instructable face amount. Optional. Must be strictly positive when set.
    minIncrement: 0.0d,  // optional — Bond-specific increment above MinPieceSize. Optional. When set, MinPieceSize must also be set.  Must be strictly positive.
    prorationRate: 0.0d,  // optional — Proration applied when the offer is oversubscribed. Defaults to 1 if not set.  Must be greater than 0 and less than or equal to 1.
    responseDeadlineDate: DateTimeOffset.Now,  // optional — Account-servicer SLA deadline for holder instruction. Optional at the DTO layer;  required under Voluntary participation on bond instrument types.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — Offeror&#39;s-agent deadline for holder instruction. Optional at the DTO layer;  required under Voluntary participation on bond instrument types.
    earlyResponseDeadline: DateTimeOffset.Now,  // optional — Optional early-tender deadline. When set, must be on or before ResponseDeadlineDate.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TenderEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

