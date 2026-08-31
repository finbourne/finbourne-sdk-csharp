# Finbourne.Sdk.Lusid.Model.CommodityCalendarSwapCashFlowEvent

Cash settlement of one calendar-average period of a CommodityCalendarSwap. One event fires per period  end date defined by the swap's schedule, including the final period; PeriodNumber identifies which.  The cash flow per unit is the pre-netted settlement price (the calendar average of the observed  commodity price minus the strike) supplied externally via the quote store — LUSID computes neither the  average nor the netting. A negative value is valid and means the period settled out of the money.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PeriodEndDate** | **DateTimeOffset** | Optional | The end date of the settling period, derived from the swap&#39;s schedule. The period settles against  the calendar average of the observed commodity price up to this date. Required, and the effective  date of the event. |
| **PaymentDate** | **DateTimeOffset** | Optional | The settlement date of the period, already adjusted for the schedule&#39;s business day convention,  payment calendars and coupon lag. Required. This is when the cash moves; the event itself is  effective at PeriodEndDate. |
| **Currency** | **string** | Required | The currency the period settles in, taken from the schedule&#39;s payment currency. Required. |
| **PeriodNumber** | **int** | Required | The sequential number of the settling period, with the first period being 1 and the final period  being the total number of periods in the schedule. Required. |
| **QuantityPerPeriod** | **decimal** | Required | The notional commodity quantity referenced by the period, and the number of units by which the  holding is reduced when the period settles. Required. |
| **ExDate** | **DateTimeOffset** | Optional | The ex-dividend date of the cash flow. Always equal to PeriodEndDate, since entitlement is  determined by the holding on the period end date. Required. |
| **CashFlowPerUnit** | **decimal?** | Optional | The pre-netted settlement amount per unit for the period (the calendar average of the observed  commodity price minus the strike), supplied externally via the quote store. Optional — absent until  the settlement price has been resolved. Negative when the period settled out of the money. |
| **CashFlowAmount** | **decimal?** | Optional | The settlement amount for the period, calculated as CashFlowPerUnit multiplied by  QuantityPerPeriod. Optional — absent until the settlement price has been resolved. Carries the  sign of CashFlowPerUnit. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent. Default: `InstrumentEventTypeEnum.CommodityCalendarSwapCashFlowEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CommodityCalendarSwapCashFlowEvent(
    periodEndDate: DateTimeOffset.Now,  // optional — The end date of the settling period, derived from the swap&#39;s schedule. The period settles against  the calendar average of the observed commodity price up to this date. Required, and the effective  date of the event.
    paymentDate: DateTimeOffset.Now,  // optional — The settlement date of the period, already adjusted for the schedule&#39;s business day convention,  payment calendars and coupon lag. Required. This is when the cash moves; the event itself is  effective at PeriodEndDate.
    currency: "...",  // required — The currency the period settles in, taken from the schedule&#39;s payment currency. Required.
    periodNumber: 0,  // required — The sequential number of the settling period, with the first period being 1 and the final period  being the total number of periods in the schedule. Required.
    quantityPerPeriod: 0.0d,  // required — The notional commodity quantity referenced by the period, and the number of units by which the  holding is reduced when the period settles. Required.
    exDate: DateTimeOffset.Now,  // optional — The ex-dividend date of the cash flow. Always equal to PeriodEndDate, since entitlement is  determined by the holding on the period end date. Required.
    cashFlowPerUnit: 0.0d,  // optional — The pre-netted settlement amount per unit for the period (the calendar average of the observed  commodity price minus the strike), supplied externally via the quote store. Optional — absent until  the settlement price has been resolved. Negative when the period settled out of the money.
    cashFlowAmount: 0.0d,  // optional — The settlement amount for the period, calculated as CashFlowPerUnit multiplied by  QuantityPerPeriod. Optional — absent until the settlement price has been resolved. Carries the  sign of CashFlowPerUnit.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CommodityCalendarSwapCashFlowEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

