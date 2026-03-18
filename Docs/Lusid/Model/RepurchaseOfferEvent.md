# Finbourne.Sdk.Lusid.Model.RepurchaseOfferEvent

Representation of a repurchase offer corporate action.  Represents an offer by the issuer to repurchase its own shares from a shareholder at a given price.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Optional | Payment date of the event. |
| **MarketDeadlineDate** | **DateTimeOffset** | Optional | Date set by the issuer or by an agent of the issuer as the latest date to respond to the offer. Must be before or equal to the PaymentDate. |
| **RepurchaseQuantity** | **decimal** | Required | Quantity of the security to be repurchased. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Required | List of possible CashOfferElections for this event. Only 1 should be provided. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Required | List of possible LapseElections for this event. Only 1 should be provided.  Allows the user to opt out of the offer. |
| **TenderOfferElections** | [List&lt;TenderOfferElection&gt;](TenderOfferElection.md) | Required | List of possible TenderOfferElections for this event. Only 1 should be provided. |
| **ProrationRate** | **decimal** | Optional | The fraction used to calculate a proportional adjustment for RepurchaseQuantity when a full period is not used.  Defaults to 1 if not set. Must be greater than 0 and less than or equal to 1. Default: `1D` |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | Date set by the account servicer as the latest date to respond to the offer.  Optional. If set, must be before or equal to MarketDeadlineDate.  Defaults to MarketDeadlineDate if not set. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.RepurchaseOfferEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RepurchaseOfferEvent(
    paymentDate: DateTimeOffset.Now,  // optional — Payment date of the event.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — Date set by the issuer or by an agent of the issuer as the latest date to respond to the offer. Must be before or equal to the PaymentDate.
    repurchaseQuantity: 0.0d,  // required — Quantity of the security to be repurchased.
    cashOfferElections: new List<CashOfferElection>(),  // required — List of possible CashOfferElections for this event. Only 1 should be provided.
    lapseElections: new List<LapseElection>(),  // required — List of possible LapseElections for this event. Only 1 should be provided.  Allows the user to opt out of the offer.
    tenderOfferElections: new List<TenderOfferElection>(),  // required — List of possible TenderOfferElections for this event. Only 1 should be provided.
    prorationRate: 0.0d,  // optional — The fraction used to calculate a proportional adjustment for RepurchaseQuantity when a full period is not used.  Defaults to 1 if not set. Must be greater than 0 and less than or equal to 1.
    responseDeadlineDate: DateTimeOffset.Now,  // optional — Date set by the account servicer as the latest date to respond to the offer.  Optional. If set, must be before or equal to MarketDeadlineDate.  Defaults to MarketDeadlineDate if not set.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RepurchaseOfferEvent>(json);
```


- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`
- [TenderOfferElection](TenderOfferElection.md) — used in `TenderOfferElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

