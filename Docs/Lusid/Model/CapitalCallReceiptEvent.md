# Finbourne.Sdk.Lusid.Model.CapitalCallReceiptEvent

The investor's payment against a capital call on a CapitalInterest. Booked separately from the call  because it arrives on a later date and may come in instalments; each populated slot books its own  receipt transaction so an unpaid fee never short-pays the deal.                The total amount may optionally be broken down into the same slots as the call (investment,  managementFee, otherFee, partnershipExpense, organisationalCost, recall, equalisationInterest,  latePaymentInterest). When any slot amount is supplied the slot amounts must sum to the total and  one transaction is booked per populated slot; otherwise a single receipt transaction is booked for  the total.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Optional | The date the receipt is paid. |
| **Amount** | **decimal** | Required | The total amount paid against the call. Must be positive. When slot amounts are supplied they  must sum to this total. |
| **CallEventId** | **string** | Required | The identifier of the capital call event this receipt pays. |
| **InvestmentAmount** | **decimal?** | Optional | The part of the receipt that pays the investment slot of the call. Optional slot; must not be negative. |
| **ManagementFeeAmount** | **decimal?** | Optional | The part of the receipt that pays the management fee slot of the call. Optional slot; must not be negative. |
| **OtherFeeAmount** | **decimal?** | Optional | The part of the receipt that pays the other fee slot of the call. Optional slot; must not be negative. |
| **PartnershipExpenseAmount** | **decimal?** | Optional | The part of the receipt that pays the partnership expense slot of the call. Optional slot; must not be negative. |
| **OrganisationalCostAmount** | **decimal?** | Optional | The part of the receipt that pays the organisational cost slot of the call. Optional slot; must not be negative. |
| **RecallAmount** | **decimal?** | Optional | The part of the receipt that pays the recall slot of the call. Optional slot; must not be negative. |
| **EqualisationInterestAmount** | **decimal?** | Optional | The part of the receipt that pays the equalisation interest slot of the call. Optional slot; must not be negative. |
| **LatePaymentInterestAmount** | **decimal?** | Optional | The part of the receipt that pays the late payment interest slot of the call. Optional slot; must not be negative. |
| **OutsideCommitmentSlots** | **List&lt;string&gt;** | Optional | The slots (names without the Amount suffix, e.g. \&quot;managementFee\&quot;) that were called outside the  commitment, so that paying them does not move paid-in capital. When omitted, defaults to  equalisationInterest and latePaymentInterest. |
| **DealId** | **string** | Optional | The identifier of the deal the receipt relates to, if any. |
| **AllocationEventId** | **string** | Optional | The identifier of the allocation event the receipt relates to, if any. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent, InstalmentCallEvent, DepositInterestCapitalisationEvent. Default: `InstrumentEventTypeEnum.CapitalCallReceiptEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CapitalCallReceiptEvent(
    date: DateTimeOffset.Now,  // optional — The date the receipt is paid.
    amount: 0.0d,  // required — The total amount paid against the call. Must be positive. When slot amounts are supplied they  must sum to this total.
    callEventId: "...",  // required — The identifier of the capital call event this receipt pays.
    investmentAmount: 0.0d,  // optional — The part of the receipt that pays the investment slot of the call. Optional slot; must not be negative.
    managementFeeAmount: 0.0d,  // optional — The part of the receipt that pays the management fee slot of the call. Optional slot; must not be negative.
    otherFeeAmount: 0.0d,  // optional — The part of the receipt that pays the other fee slot of the call. Optional slot; must not be negative.
    partnershipExpenseAmount: 0.0d,  // optional — The part of the receipt that pays the partnership expense slot of the call. Optional slot; must not be negative.
    organisationalCostAmount: 0.0d,  // optional — The part of the receipt that pays the organisational cost slot of the call. Optional slot; must not be negative.
    recallAmount: 0.0d,  // optional — The part of the receipt that pays the recall slot of the call. Optional slot; must not be negative.
    equalisationInterestAmount: 0.0d,  // optional — The part of the receipt that pays the equalisation interest slot of the call. Optional slot; must not be negative.
    latePaymentInterestAmount: 0.0d,  // optional — The part of the receipt that pays the late payment interest slot of the call. Optional slot; must not be negative.
    outsideCommitmentSlots: ,  // optional — The slots (names without the Amount suffix, e.g. \&quot;managementFee\&quot;) that were called outside the  commitment, so that paying them does not move paid-in capital. When omitted, defaults to  equalisationInterest and latePaymentInterest.
    dealId: "...",  // optional — The identifier of the deal the receipt relates to, if any.
    allocationEventId: "...",  // optional — The identifier of the allocation event the receipt relates to, if any.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent, InstalmentCallEvent, DepositInterestCapitalisationEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CapitalCallReceiptEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

