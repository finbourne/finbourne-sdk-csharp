# Finbourne.Sdk.Lusid.Model.BondForwardCashSettlementEvent

Cash settlement of a BondForward at its settlement date:  the forward closes against a single net payment of the clean price difference, and no bond changes  hands. Unlike a commodity forward the underlying is a mastered, quoted instrument, so LUSID computes  the settlement amount from the underlying's quote rather than taking a pre-netted figure; a supplied  referencePrice wins and the quote is not consulted.  Accrued does not enter the payoff, by cancellation rather than entitlement: both sides of the  difference accrue to the same date, so the accrued is identical on each and drops out.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AgreedCleanPrice** | **decimal** | Required | The agreed price, percent of par, carried from the definition. |
| **ContractSize** | **decimal** | Required | Face amount per unit, carried from the definition. It scales the payoff, so it is rejected where it  differs from the instrument&#39;s own value. |
| **MaturityDate** | **DateTimeOffset** | Optional | The forward&#39;s contractual settlement date, on which the price difference fixes. |
| **ReferencePrice** | **decimal?** | Optional | The underlying&#39;s clean price, percent of par, at the settlement date. Null resolves from the  underlying&#39;s quote; a supplied value wins and the quote is not consulted. |
| **SettlementAmountPerUnit** | **decimal?** | Optional | Output only: the net settlement per unit, computed from the reference price, the agreed price and  the contract size. A supplied value is overwritten. Negative is valid and means the holder pays. |
| **SettlementCurrency** | **string** | Required | Currency the net amount settles in, being the forward&#39;s domestic currency. |
| **SettlementDate** | **DateTimeOffset?** | Optional | The date the net payment settles. Null means the maturity date; cash-settled forwards commonly pay  a day or two after the price fixes. Rejected where earlier than the maturity date. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent. Default: `InstrumentEventTypeEnum.BondForwardCashSettlementEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BondForwardCashSettlementEvent(
    agreedCleanPrice: 0.0d,  // required — The agreed price, percent of par, carried from the definition.
    contractSize: 0.0d,  // required — Face amount per unit, carried from the definition. It scales the payoff, so it is rejected where it  differs from the instrument&#39;s own value.
    maturityDate: DateTimeOffset.Now,  // optional — The forward&#39;s contractual settlement date, on which the price difference fixes.
    referencePrice: 0.0d,  // optional — The underlying&#39;s clean price, percent of par, at the settlement date. Null resolves from the  underlying&#39;s quote; a supplied value wins and the quote is not consulted.
    settlementAmountPerUnit: 0.0d,  // optional — Output only: the net settlement per unit, computed from the reference price, the agreed price and  the contract size. A supplied value is overwritten. Negative is valid and means the holder pays.
    settlementCurrency: "...",  // required — Currency the net amount settles in, being the forward&#39;s domestic currency.
    settlementDate: DateTimeOffset.Now,  // optional — The date the net payment settles. Null means the maturity date; cash-settled forwards commonly pay  a day or two after the price fixes. Rejected where earlier than the maturity date.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BondForwardCashSettlementEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

