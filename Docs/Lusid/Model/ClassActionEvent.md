# Finbourne.Sdk.Lusid.Model.ClassActionEvent

Class Action Event (CLSA) — a voluntary corporate action under which security holders  receive cash compensation from a court-approved settlement fund following litigation  against an issuer.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Optional | Date on which the settlement distribution is paid to the holder. |
| **FilingDeadline** | **DateTimeOffset** | Optional | Court-set deadline for submitting a proof of claim. |
| **ClassPeriodStart** | **DateTimeOffset** | Optional | Lower bound of the eligibility window (inclusive). |
| **ClassPeriodEnd** | **DateTimeOffset** | Optional | Upper bound of the eligibility window (inclusive). |
| **ExDate** | **DateTimeOffset?** | Optional | Date from which the security trades without the settlement right.  Null for most class actions where no ex date is defined. |
| **RecordDate** | **DateTimeOffset?** | Optional | Date at which positions are struck for notification scope. Informational only. |
| **AnnouncementDate** | **DateTimeOffset?** | Optional | Settlement public-announcement or court-approval date. |
| **CaseReference** | **string** | Optional | Lawsuit or settlement-fund identifier (court case number, fund name). Audit-only. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | Cash offer elections for this event. Exactly one entry carrying the per-share  settlement amount as CashOfferPrice and settlement currency as CashOfferCurrency. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | Lapse elections for this event. Exactly one entry (NOAC) with IsDefault &#x3D; true. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent. Default: `InstrumentEventTypeEnum.ClassActionEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ClassActionEvent(
    paymentDate: DateTimeOffset.Now,  // optional — Date on which the settlement distribution is paid to the holder.
    filingDeadline: DateTimeOffset.Now,  // optional — Court-set deadline for submitting a proof of claim.
    classPeriodStart: DateTimeOffset.Now,  // optional — Lower bound of the eligibility window (inclusive).
    classPeriodEnd: DateTimeOffset.Now,  // optional — Upper bound of the eligibility window (inclusive).
    exDate: DateTimeOffset.Now,  // optional — Date from which the security trades without the settlement right.  Null for most class actions where no ex date is defined.
    recordDate: DateTimeOffset.Now,  // optional — Date at which positions are struck for notification scope. Informational only.
    announcementDate: DateTimeOffset.Now,  // optional — Settlement public-announcement or court-approval date.
    caseReference: "...",  // optional — Lawsuit or settlement-fund identifier (court case number, fund name). Audit-only.
    cashOfferElections: new List<CashOfferElection>(),  // optional — Cash offer elections for this event. Exactly one entry carrying the per-share  settlement amount as CashOfferPrice and settlement currency as CashOfferCurrency.
    lapseElections: new List<LapseElection>(),  // optional — Lapse elections for this event. Exactly one entry (NOAC) with IsDefault &#x3D; true.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ClassActionEvent>(json);
```


- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

