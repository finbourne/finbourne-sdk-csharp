# Finbourne.Sdk.Lusid.Model.CapitalCallEvent

A call of committed capital on a CapitalInterest: the fund draws down the amount from the investor's  unfunded commitment, moving it to funded capital.                The total amount may optionally be broken down into slots (investment, managementFee, otherFee,  partnershipExpense, organisationalCost, recall, equalisationInterest, latePaymentInterest). When any  slot amount is supplied the slot amounts must sum to the total and one transaction is booked per  populated slot; otherwise a single legacy drawdown transaction is booked for the total.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Optional | The date the capital call takes effect. |
| **Amount** | **decimal** | Required | The total amount of committed capital called. Must be positive. When slot amounts are  supplied they must sum to this total. |
| **InvestmentAmount** | **decimal?** | Optional | The part of the call that funds investments. Optional slot; must not be negative. |
| **ManagementFeeAmount** | **decimal?** | Optional | The part of the call that pays management fees. Optional slot; must not be negative. |
| **OtherFeeAmount** | **decimal?** | Optional | The part of the call that pays other fees. Optional slot; must not be negative. |
| **PartnershipExpenseAmount** | **decimal?** | Optional | The part of the call that pays partnership expenses. Optional slot; must not be negative. |
| **OrganisationalCostAmount** | **decimal?** | Optional | The part of the call that pays organisational costs. Optional slot; must not be negative. |
| **RecallAmount** | **decimal?** | Optional | The part of the call that re-draws previously distributed recallable capital. Optional slot; must not be negative. |
| **EqualisationInterestAmount** | **decimal?** | Optional | The part of the call that is equalisation interest. Optional slot; must not be negative. |
| **LatePaymentInterestAmount** | **decimal?** | Optional | The part of the call that is late payment interest. Optional slot; must not be negative. |
| **OutsideCommitmentSlots** | **List&lt;string&gt;** | Optional | The slots (names without the Amount suffix, e.g. \&quot;managementFee\&quot;) called outside the commitment,  so that they do not reduce the uncalled commitment. When omitted, defaults to equalisationInterest  and latePaymentInterest. |
| **DealId** | **string** | Optional | The identifier of the deal the call relates to, if any. |
| **AllocationEventId** | **string** | Optional | The identifier of the allocation event the call relates to, if any. |
| **NoticeDate** | **DateTimeOffset?** | Optional | The date the call notice was issued, if known. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent. Default: `InstrumentEventTypeEnum.CapitalCallEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CapitalCallEvent(
    date: DateTimeOffset.Now,  // optional — The date the capital call takes effect.
    amount: 0.0d,  // required — The total amount of committed capital called. Must be positive. When slot amounts are  supplied they must sum to this total.
    investmentAmount: 0.0d,  // optional — The part of the call that funds investments. Optional slot; must not be negative.
    managementFeeAmount: 0.0d,  // optional — The part of the call that pays management fees. Optional slot; must not be negative.
    otherFeeAmount: 0.0d,  // optional — The part of the call that pays other fees. Optional slot; must not be negative.
    partnershipExpenseAmount: 0.0d,  // optional — The part of the call that pays partnership expenses. Optional slot; must not be negative.
    organisationalCostAmount: 0.0d,  // optional — The part of the call that pays organisational costs. Optional slot; must not be negative.
    recallAmount: 0.0d,  // optional — The part of the call that re-draws previously distributed recallable capital. Optional slot; must not be negative.
    equalisationInterestAmount: 0.0d,  // optional — The part of the call that is equalisation interest. Optional slot; must not be negative.
    latePaymentInterestAmount: 0.0d,  // optional — The part of the call that is late payment interest. Optional slot; must not be negative.
    outsideCommitmentSlots: ,  // optional — The slots (names without the Amount suffix, e.g. \&quot;managementFee\&quot;) called outside the commitment,  so that they do not reduce the uncalled commitment. When omitted, defaults to equalisationInterest  and latePaymentInterest.
    dealId: "...",  // optional — The identifier of the deal the call relates to, if any.
    allocationEventId: "...",  // optional — The identifier of the allocation event the call relates to, if any.
    noticeDate: DateTimeOffset.Now,  // optional — The date the call notice was issued, if known.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CapitalCallEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

