# Finbourne.Sdk.Lusid.Model.TotalReturnSwapCashFlowEvent

A scheduled exchange of a TotalReturnSwap: a funding-leg coupon or notional exchange, an asset income or  principal passed through on the asset leg, or a price-return reset of the asset leg. Component says  which. The amount is per unit of the swap as its cash flows are booked, signed negative when paid; it is  absent until the market data determining it has been published.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExDate** | **DateTimeOffset** | Optional | The date the holding must be held on to be entitled to the flow. Required. |
| **PaymentDate** | **DateTimeOffset** | Optional | The date the flow pays. Required. |
| **Currency** | **string** | Required | The currency the flow pays in. Required. |
| **Component** | **string** | Required | Which exchange of the swap the flow settles. Required.                Supported string (enumeration) values are: [FundingPayment, FundingNotional, AssetIncome, AssetPrincipal, PriceReturn]. |
| **FlowType** | **string** | Required | The type of the underlying cash flow the event settles. A component can gather several flow types  paying on one date (an asset-backed bond&#39;s coupon, interest deferral and interest shortfall are all  asset income), so the flow type is what tells them apart. Required.                Supported string (enumeration) values are: [Coupon, Notional, Premium, Principal, Protection, Cash, Dividend, Interest, PrincipalWriteOff, InterestDeferred, InterestShortfall, MarkToMarket, InterestInKind]. |
| **LegIdentifier** | **string** | Required | The leg the flow belongs to. Required.                Supported string (enumeration) values are: [AssetLeg, FundingLeg]. |
| **PayReceive** | **string** | Required | Whether the flow is paid or received from the holder&#39;s perspective. The amount is already signed  accordingly; this attributes an undetermined flow to its side. Required.                Supported string (enumeration) values are: [Pay, Receive]. |
| **CashFlowPerUnit** | **decimal?** | Optional | The signed amount per unit of the swap held on the ex date, negative when paid. Optional — absent  until determinable: a price-return reset needs its reset quotes, a floating funding payment its fixing. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent. Default: `InstrumentEventTypeEnum.TotalReturnSwapCashFlowEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TotalReturnSwapCashFlowEvent(
    exDate: DateTimeOffset.Now,  // optional — The date the holding must be held on to be entitled to the flow. Required.
    paymentDate: DateTimeOffset.Now,  // optional — The date the flow pays. Required.
    currency: "...",  // required — The currency the flow pays in. Required.
    component: "...",  // required — Which exchange of the swap the flow settles. Required.                Supported string (enumeration) values are: [FundingPayment, FundingNotional, AssetIncome, AssetPrincipal, PriceReturn].
    flowType: "...",  // required — The type of the underlying cash flow the event settles. A component can gather several flow types  paying on one date (an asset-backed bond&#39;s coupon, interest deferral and interest shortfall are all  asset income), so the flow type is what tells them apart. Required.                Supported string (enumeration) values are: [Coupon, Notional, Premium, Principal, Protection, Cash, Dividend, Interest, PrincipalWriteOff, InterestDeferred, InterestShortfall, MarkToMarket, InterestInKind].
    legIdentifier: "...",  // required — The leg the flow belongs to. Required.                Supported string (enumeration) values are: [AssetLeg, FundingLeg].
    payReceive: "...",  // required — Whether the flow is paid or received from the holder&#39;s perspective. The amount is already signed  accordingly; this attributes an undetermined flow to its side. Required.                Supported string (enumeration) values are: [Pay, Receive].
    cashFlowPerUnit: 0.0d,  // optional — The signed amount per unit of the swap held on the ex date, negative when paid. Optional — absent  until determinable: a price-return reset needs its reset quotes, a floating funding payment its fixing.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TotalReturnSwapCashFlowEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

