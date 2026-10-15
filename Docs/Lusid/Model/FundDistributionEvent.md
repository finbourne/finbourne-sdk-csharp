# Finbourne.Sdk.Lusid.Model.FundDistributionEvent

A distribution from the fund to the holder of a CapitalInterest. A recallable distribution restores  unfunded capital (the fund may call it again); a non-recallable distribution permanently returns capital.                The total amount may optionally be broken down into slots by character (returnOfCapital, realisedGain,  dividend, interest, otherIncome, carryPaid, withholding, returnOfExcess). When any slot amount is supplied  the slot amounts must sum to the total, one transaction is booked per populated slot, and the recallable  portion of each of the five capital/income characters is given by its matching Recallable amount.  Without slots a single legacy distribution transaction is booked for the total, recallable according  to isRecallable.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Optional | The date the distribution takes effect. |
| **Amount** | **decimal** | Required | The total amount distributed. Must be positive. When slot amounts are supplied they must sum to this total. |
| **IsRecallable** | **bool** | Optional | Legacy flag, used only when no slot amount is supplied: true when the fund may recall the whole  distributed amount, so the distribution restores unfunded capital rather than permanently returning  it. Defaults to false. Must not be combined with slot amounts. |
| **ReturnOfCapitalAmount** | **decimal?** | Optional | The part of the distribution that returns capital. Optional slot; must not be negative. |
| **RealisedGainAmount** | **decimal?** | Optional | The part of the distribution that is realised gain. Optional slot; must not be negative. |
| **DividendAmount** | **decimal?** | Optional | The part of the distribution that is dividend income. Optional slot; must not be negative. |
| **InterestAmount** | **decimal?** | Optional | The part of the distribution that is interest income. Optional slot; must not be negative. |
| **OtherIncomeAmount** | **decimal?** | Optional | The part of the distribution that is other income. Optional slot; must not be negative. |
| **ReturnOfCapitalRecallableAmount** | **decimal?** | Optional | The recallable portion of returnOfCapitalAmount. Optional; must not exceed returnOfCapitalAmount. |
| **RealisedGainRecallableAmount** | **decimal?** | Optional | The recallable portion of realisedGainAmount. Optional; must not exceed realisedGainAmount. |
| **DividendRecallableAmount** | **decimal?** | Optional | The recallable portion of dividendAmount. Optional; must not exceed dividendAmount. |
| **InterestRecallableAmount** | **decimal?** | Optional | The recallable portion of interestAmount. Optional; must not exceed interestAmount. |
| **OtherIncomeRecallableAmount** | **decimal?** | Optional | The recallable portion of otherIncomeAmount. Optional; must not exceed otherIncomeAmount. |
| **CarryPaidAmount** | **decimal?** | Optional | The part of the distribution that is carried interest paid to the general partner. Optional slot; must not be negative. |
| **WithholdingAmount** | **decimal?** | Optional | The part of the distribution withheld for tax (a deemed distribution). Optional slot; must not be negative. |
| **ReturnOfExcessAmount** | **decimal?** | Optional | The part of the distribution that returns capital called in excess. Optional slot; must not be negative. |
| **RecallableUntil** | **DateTimeOffset?** | Optional | The date until which the recallable portions may be recalled, if limited. Must not precede the distribution date. |
| **DealId** | **string** | Optional | The identifier of the deal the distribution relates to, if any. |
| **AllocationEventId** | **string** | Optional | The identifier of the allocation event the distribution relates to, if any. |
| **WaterfallTier** | **string** | Optional | The waterfall tier the distribution was paid under, if any. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent, InstalmentCallEvent. Default: `InstrumentEventTypeEnum.FundDistributionEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundDistributionEvent(
    date: DateTimeOffset.Now,  // optional — The date the distribution takes effect.
    amount: 0.0d,  // required — The total amount distributed. Must be positive. When slot amounts are supplied they must sum to this total.
    isRecallable: true,  // optional — Legacy flag, used only when no slot amount is supplied: true when the fund may recall the whole  distributed amount, so the distribution restores unfunded capital rather than permanently returning  it. Defaults to false. Must not be combined with slot amounts.
    returnOfCapitalAmount: 0.0d,  // optional — The part of the distribution that returns capital. Optional slot; must not be negative.
    realisedGainAmount: 0.0d,  // optional — The part of the distribution that is realised gain. Optional slot; must not be negative.
    dividendAmount: 0.0d,  // optional — The part of the distribution that is dividend income. Optional slot; must not be negative.
    interestAmount: 0.0d,  // optional — The part of the distribution that is interest income. Optional slot; must not be negative.
    otherIncomeAmount: 0.0d,  // optional — The part of the distribution that is other income. Optional slot; must not be negative.
    returnOfCapitalRecallableAmount: 0.0d,  // optional — The recallable portion of returnOfCapitalAmount. Optional; must not exceed returnOfCapitalAmount.
    realisedGainRecallableAmount: 0.0d,  // optional — The recallable portion of realisedGainAmount. Optional; must not exceed realisedGainAmount.
    dividendRecallableAmount: 0.0d,  // optional — The recallable portion of dividendAmount. Optional; must not exceed dividendAmount.
    interestRecallableAmount: 0.0d,  // optional — The recallable portion of interestAmount. Optional; must not exceed interestAmount.
    otherIncomeRecallableAmount: 0.0d,  // optional — The recallable portion of otherIncomeAmount. Optional; must not exceed otherIncomeAmount.
    carryPaidAmount: 0.0d,  // optional — The part of the distribution that is carried interest paid to the general partner. Optional slot; must not be negative.
    withholdingAmount: 0.0d,  // optional — The part of the distribution withheld for tax (a deemed distribution). Optional slot; must not be negative.
    returnOfExcessAmount: 0.0d,  // optional — The part of the distribution that returns capital called in excess. Optional slot; must not be negative.
    recallableUntil: DateTimeOffset.Now,  // optional — The date until which the recallable portions may be recalled, if limited. Must not precede the distribution date.
    dealId: "...",  // optional — The identifier of the deal the distribution relates to, if any.
    allocationEventId: "...",  // optional — The identifier of the allocation event the distribution relates to, if any.
    waterfallTier: "...",  // optional — The waterfall tier the distribution was paid under, if any.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent, InstalmentCallEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundDistributionEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

