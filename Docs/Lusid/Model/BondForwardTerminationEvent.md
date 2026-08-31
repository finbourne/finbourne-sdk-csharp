# Finbourne.Sdk.Lusid.Model.BondForwardTerminationEvent

Termination of a BondForward because its underlying bond  was redeemed early: the deliverable ceases to exist, so the forward terminates against the proceeds  the underlying was actually redeemed for.  The event is posted against the forward's own LusidInstrumentId by the feed or orchestration layer.  The corporate-action dependency graph is self-keyed by LUID and a MasteredInstrument reference links  price, not events, so the underlying's own EarlyRedemptionEvent does not propagate here and neither  the redemption price nor either accrued figure can be derived on the forward.  Unlike cash settlement, both accrued figures appear and neither cancels: the redemption accrues to the  redemption date and the forward's obligation accrued to its own settlement date, so the two differ.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AgreedCleanPrice** | **decimal** | Required | The agreed price, percent of par, carried from the definition; rejected where it differs from the  instrument&#39;s own value. |
| **ContractSize** | **decimal** | Required | Face amount per unit, carried from the definition; rejected where it differs from the instrument&#39;s  own value. |
| **RedemptionAccrued** | **decimal?** | Optional | Accrued paid on the underlying&#39;s redemption, percent of par, at full precision. Required, not  resolved: the forward cannot read the underlying&#39;s accrual. Nullable so that absence is detectable,  zero staying a legitimate supplied value (a bond trading flat); null is rejected. |
| **RedemptionPrice** | **decimal?** | Optional | The price the underlying was redeemed at, percent of par. Must be supplied: it comes from the  underlying&#39;s own redemption. Nullable so that absence is detectable; null is rejected, and zero is  legal (a write-off or liquidation may recover nothing). |
| **SettlementAccrued** | **decimal?** | Optional | Accrued the buyer would have paid at the forward&#39;s own maturity date - the invoice date it escaped,  not this event&#39;s settlement date. Nullable so that absence is detectable; null is rejected. |
| **SettlementAmountPerUnit** | **decimal?** | Optional | The net termination amount per unit. A supplied value wins; null is computed as  ((redemptionPrice + redemptionAccrued) - (agreedCleanPrice + settlementAccrued)) / 100 x contractSize,  which is undiscounted - where the confirmation nets on a discounted basis, supply the agreed figure.  Negative is valid and means the holder pays; it must not be floored. |
| **SettlementCurrency** | **string** | Required | Currency the net amount settles in. |
| **SettlementDate** | **DateTimeOffset** | Optional | The date the net termination amount settles. |
| **TerminationDate** | **DateTimeOffset** | Optional | The date the termination takes effect, being the effective date of the underlying&#39;s redemption.  Required, not defaulted: the forward cannot read the underlying&#39;s redemption. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent. Default: `InstrumentEventTypeEnum.BondForwardTerminationEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondForwardTerminationEvent(
    agreedCleanPrice: 0.0d,  // required — The agreed price, percent of par, carried from the definition; rejected where it differs from the  instrument&#39;s own value.
    contractSize: 0.0d,  // required — Face amount per unit, carried from the definition; rejected where it differs from the instrument&#39;s  own value.
    redemptionAccrued: 0.0d,  // optional — Accrued paid on the underlying&#39;s redemption, percent of par, at full precision. Required, not  resolved: the forward cannot read the underlying&#39;s accrual. Nullable so that absence is detectable,  zero staying a legitimate supplied value (a bond trading flat); null is rejected.
    redemptionPrice: 0.0d,  // optional — The price the underlying was redeemed at, percent of par. Must be supplied: it comes from the  underlying&#39;s own redemption. Nullable so that absence is detectable; null is rejected, and zero is  legal (a write-off or liquidation may recover nothing).
    settlementAccrued: 0.0d,  // optional — Accrued the buyer would have paid at the forward&#39;s own maturity date - the invoice date it escaped,  not this event&#39;s settlement date. Nullable so that absence is detectable; null is rejected.
    settlementAmountPerUnit: 0.0d,  // optional — The net termination amount per unit. A supplied value wins; null is computed as  ((redemptionPrice + redemptionAccrued) - (agreedCleanPrice + settlementAccrued)) / 100 x contractSize,  which is undiscounted - where the confirmation nets on a discounted basis, supply the agreed figure.  Negative is valid and means the holder pays; it must not be floored.
    settlementCurrency: "...",  // required — Currency the net amount settles in.
    settlementDate: DateTimeOffset.Now,  // optional — The date the net termination amount settles.
    terminationDate: DateTimeOffset.Now,  // optional — The date the termination takes effect, being the effective date of the underlying&#39;s redemption.  Required, not defaulted: the forward cannot read the underlying&#39;s redemption.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondForwardTerminationEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

