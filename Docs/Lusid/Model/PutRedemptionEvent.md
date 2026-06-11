# Finbourne.Sdk.Lusid.Model.PutRedemptionEvent

Put Redemption (BPUT) — early redemption of a bond at the holder's election under an  indenture-defined put option. Supports both Voluntary (the AMI-SeCo canonical shape) and  Mandatory (a deliberate market extension beyond SCoRE) participation on Bond, ComplexBond,  and InflationLinkedBond instruments. Cloned from RepurchaseOfferEvent (BIDS) and narrowed  to debt with a fixed event-level OfferPrice instead of a per-election holder-bid price.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Optional | Settlement date for the cash + security legs of the put redemption. |
| **OfferPrice** | **decimal** | Required | Put price per unit of face value (AMI-SeCo OFFR). Per-100 PRCT semantics —  &#x60;OfferPrice &#x3D; 100.00&#x60; means par; &#x60;97.50&#x60; means 97.5% of par. Must be strictly positive. |
| **Currency** | **string** | Required | Settlement currency of the cash leg (ISO 4217 3-letter code). |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Required | List of possible CashOfferElections. Exactly one entry per event in both Mandatory and Voluntary paths. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Required | List of possible LapseElections. Exactly one entry for Voluntary (NOAC default). Empty for Mandatory. |
| **MarketDeadlineDate** | **DateTimeOffset?** | Optional | Issuer / agent deadline for holder instructions. Required for Voluntary participation;  optional for Mandatory (no holder-deadline concept). |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | Account-servicer deadline. Defaults to MarketDeadlineDate when omitted.  If set, must be on or before MarketDeadlineDate. |
| **EarlyResponseDeadline** | **DateTimeOffset?** | Optional | Early-participation deadline. Rare on BPUT; carried for cross-event consistency.  If set, must be on or before ResponseDeadlineDate. |
| **ExDate** | **DateTimeOffset?** | Optional | AMI-SeCo §4.6 does not list this for BPUT; carried for cross-event consistency.  If set, must be on or before MarketDeadlineDate. |
| **AnnouncementDate** | **DateTimeOffset?** | Optional | Public announcement date. If set, must be on or before ExDate. |
| **AccruedInterestPerUnit** | **decimal?** | Optional | Per-unit accrued interest. Optional — loader / post-processor derives from the bond&#39;s coupon  schedule and day-count when not supplied. EconomicallyComplete enforces non-null for  accrual-bearing instruments via InstrumentTypeAccruesInterest. |
| **ProrationRate** | **decimal** | Optional | Issuer-side aggregate proration cap (AMI-SeCo PROR). Default 1.0; range (0, 1]. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent. Default: `InstrumentEventTypeEnum.PutRedemptionEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PutRedemptionEvent(
    paymentDate: DateTimeOffset.Now,  // optional — Settlement date for the cash + security legs of the put redemption.
    offerPrice: 0.0d,  // required — Put price per unit of face value (AMI-SeCo OFFR). Per-100 PRCT semantics —  &#x60;OfferPrice &#x3D; 100.00&#x60; means par; &#x60;97.50&#x60; means 97.5% of par. Must be strictly positive.
    currency: "...",  // required — Settlement currency of the cash leg (ISO 4217 3-letter code).
    cashOfferElections: new List<CashOfferElection>(),  // required — List of possible CashOfferElections. Exactly one entry per event in both Mandatory and Voluntary paths.
    lapseElections: new List<LapseElection>(),  // required — List of possible LapseElections. Exactly one entry for Voluntary (NOAC default). Empty for Mandatory.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — Issuer / agent deadline for holder instructions. Required for Voluntary participation;  optional for Mandatory (no holder-deadline concept).
    responseDeadlineDate: DateTimeOffset.Now,  // optional — Account-servicer deadline. Defaults to MarketDeadlineDate when omitted.  If set, must be on or before MarketDeadlineDate.
    earlyResponseDeadline: DateTimeOffset.Now,  // optional — Early-participation deadline. Rare on BPUT; carried for cross-event consistency.  If set, must be on or before ResponseDeadlineDate.
    exDate: DateTimeOffset.Now,  // optional — AMI-SeCo §4.6 does not list this for BPUT; carried for cross-event consistency.  If set, must be on or before MarketDeadlineDate.
    announcementDate: DateTimeOffset.Now,  // optional — Public announcement date. If set, must be on or before ExDate.
    accruedInterestPerUnit: 0.0d,  // optional — Per-unit accrued interest. Optional — loader / post-processor derives from the bond&#39;s coupon  schedule and day-count when not supplied. EconomicallyComplete enforces non-null for  accrual-bearing instruments via InstrumentTypeAccruesInterest.
    prorationRate: 0.0d,  // optional — Issuer-side aggregate proration cap (AMI-SeCo PROR). Default 1.0; range (0, 1].
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PutRedemptionEvent>(json);
```


- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

