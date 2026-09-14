# Finbourne.Sdk.Lusid.Model.DutchAuctionEvent

Dutch Auction Event (DTCH) — a voluntary corporate action with price-discovery, proration,  and per-holder bid audit. Tri-modal: CASH (uniform clearing-price cash buyback via  TenderOfferElection), SECU (clean security-for-security exchange via SecurityOfferElection),  or CASE (security exchange with signed per-unit cash settlement via CashAndSecurityOfferElection).
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Optional | Settlement date for both the security and cash legs of the auction. |
| **MarketDeadlineDate** | **DateTimeOffset** | Optional | Issuer or acquirer instruction deadline. |
| **Currency** | **string** | Optional | Event settlement currency (ISO 4217). Optional: when absent the settlement currency is  taken from the elected path (TenderOfferCurrency, CashOfferCurrency or  FractionalUnitsCashCurrency as applicable). |
| **TenderOfferElections** | [List&lt;TenderOfferElection&gt;](TenderOfferElection.md) | Optional | List of possible TenderOfferElections for this event. Populated on the CASH path (Count &#x3D;&#x3D; 1);  empty on the SECU and CASE paths. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | List of possible SecurityOfferElections for this event. Populated on the SECU path (Count &#x3D;&#x3D; 1);  empty on the CASH and CASE paths. |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible CashAndSecurityOfferElections for this event. Populated on the CASE path  (Count &#x3D;&#x3D; 1); empty on the CASH and SECU paths. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | List of possible LapseElections for this event. Required on all three paths (Count &#x3D;&#x3D; 1).  Allows the holder to opt out of the offer (NOAC). |
| **MixedLotConstituentsElections** | [List&lt;MixedLotConstituentsElection&gt;](MixedLotConstituentsElection.md) | Optional | List of possible MixedLotConstituentsElections for this event, if any. Each election settles into one or more  distinct new securities and/or cash legs of its own, in place of the single event-level NewInstrument the  SecurityOffer and CashAndSecurityOffer paths resolve to.    Several may be present: a Dutch Auction commonly offers a number of mutually exclusive destinations, and each  is described by its own election. Not applicable to the CASH path, which has no security leg to multiply. |
| **UnknownProceedsElections** | [List&lt;UnknownProceedsElection&gt;](UnknownProceedsElection.md) | Optional | List of possible unknown-proceeds elections for this event (UNKNOWN) — the outturn is not yet known. |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | Account-servicer response deadline. Defaults to MarketDeadlineDate when not supplied.  When provided, must be on or before MarketDeadlineDate. |
| **EarlyResponseDeadline** | **DateTimeOffset?** | Optional | Early-participation deadline. When provided, must be on or before ResponseDeadlineDate. |
| **ExDate** | **DateTimeOffset?** | Optional | The ex date of the event. Optional; carried for cross-event consistency. |
| **RecordDate** | **DateTimeOffset?** | Optional | The record date of the event. Optional and not required by AMI-SeCo for DTCH  (the event is instruction-driven via QINS, not record-date-driven). |
| **AnnouncementDate** | **DateTimeOffset?** | Optional | Public announcement date of the auction. Optional. |
| **TargetQuantity** | **decimal?** | Optional | Total quantity of securities sought by the issuer or acquirer. Optional. |
| **ProrationRate** | **decimal** | Optional | Proportional adjustment applied to the security and cash legs on all paths.  Must be in (0, 1]. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Optional | *No description available.* |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | Cash-in-lieu price per fractional unit on the SECU and CASE paths.  Null indicates round-down disposition of fractional remainders.  Distinct from the CASE path&#39;s main cash settlement (which lives on CashAndSecurityOfferElection). |
| **FractionalUnitsCashCurrency** | **string** | Optional | Currency of the cash-in-lieu paid on fractional remainders on the SECU and CASE paths.  Required when FractionalUnitsCashPrice is non-null. |
| **BidPrice** | **decimal?** | Optional | Per-holder bid price submitted at instruction time. Audit-only; no calculation impact. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent. Default: `InstrumentEventTypeEnum.DutchAuctionEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DutchAuctionEvent(
    paymentDate: DateTimeOffset.Now,  // optional — Settlement date for both the security and cash legs of the auction.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — Issuer or acquirer instruction deadline.
    currency: "...",  // optional — Event settlement currency (ISO 4217). Optional: when absent the settlement currency is  taken from the elected path (TenderOfferCurrency, CashOfferCurrency or  FractionalUnitsCashCurrency as applicable).
    tenderOfferElections: new List<TenderOfferElection>(),  // optional — List of possible TenderOfferElections for this event. Populated on the CASH path (Count &#x3D;&#x3D; 1);  empty on the SECU and CASE paths.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — List of possible SecurityOfferElections for this event. Populated on the SECU path (Count &#x3D;&#x3D; 1);  empty on the CASH and CASE paths.
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible CashAndSecurityOfferElections for this event. Populated on the CASE path  (Count &#x3D;&#x3D; 1); empty on the CASH and SECU paths.
    lapseElections: new List<LapseElection>(),  // optional — List of possible LapseElections for this event. Required on all three paths (Count &#x3D;&#x3D; 1).  Allows the holder to opt out of the offer (NOAC).
    mixedLotConstituentsElections: new List<MixedLotConstituentsElection>(),  // optional — List of possible MixedLotConstituentsElections for this event, if any. Each election settles into one or more  distinct new securities and/or cash legs of its own, in place of the single event-level NewInstrument the  SecurityOffer and CashAndSecurityOffer paths resolve to.    Several may be present: a Dutch Auction commonly offers a number of mutually exclusive destinations, and each  is described by its own election. Not applicable to the CASH path, which has no security leg to multiply.
    unknownProceedsElections: new List<UnknownProceedsElection>(),  // optional — List of possible unknown-proceeds elections for this event (UNKNOWN) — the outturn is not yet known.
    responseDeadlineDate: DateTimeOffset.Now,  // optional — Account-servicer response deadline. Defaults to MarketDeadlineDate when not supplied.  When provided, must be on or before MarketDeadlineDate.
    earlyResponseDeadline: DateTimeOffset.Now,  // optional — Early-participation deadline. When provided, must be on or before ResponseDeadlineDate.
    exDate: DateTimeOffset.Now,  // optional — The ex date of the event. Optional; carried for cross-event consistency.
    recordDate: DateTimeOffset.Now,  // optional — The record date of the event. Optional and not required by AMI-SeCo for DTCH  (the event is instruction-driven via QINS, not record-date-driven).
    announcementDate: DateTimeOffset.Now,  // optional — Public announcement date of the auction. Optional.
    targetQuantity: 0.0d,  // optional — Total quantity of securities sought by the issuer or acquirer. Optional.
    prorationRate: 0.0d,  // optional — Proportional adjustment applied to the security and cash legs on all paths.  Must be in (0, 1].
    newInstrument: new NewInstrument(...),  // optional
    fractionalUnitsCashPrice: 0.0d,  // optional — Cash-in-lieu price per fractional unit on the SECU and CASE paths.  Null indicates round-down disposition of fractional remainders.  Distinct from the CASE path&#39;s main cash settlement (which lives on CashAndSecurityOfferElection).
    fractionalUnitsCashCurrency: "...",  // optional — Currency of the cash-in-lieu paid on fractional remainders on the SECU and CASE paths.  Required when FractionalUnitsCashPrice is non-null.
    bidPrice: 0.0d,  // optional — Per-holder bid price submitted at instruction time. Audit-only; no calculation impact.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DutchAuctionEvent>(json);
```


- [TenderOfferElection](TenderOfferElection.md) — used in `TenderOfferElections`
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`
- [MixedLotConstituentsElection](MixedLotConstituentsElection.md) — used in `MixedLotConstituentsElections`
- [UnknownProceedsElection](UnknownProceedsElection.md) — used in `UnknownProceedsElections`
- [NewInstrument](NewInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

