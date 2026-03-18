# Finbourne.Sdk.Lusid.Model.CallOnIntermediateSecuritiesEvent

CallOnIntermediateSecuritiesEvent event (EXRI), representing an exercise on intermediate securities resulting from an intermediate securities distribution.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExpiryDate** | **DateTimeOffset** | Optional | The date on which the issue ends. |
| **PaymentDate** | **DateTimeOffset** | Optional | The payment date of the event. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Required | *No description available.* |
| **Price** | **decimal** | Required | The price at which new units are purchased. |
| **ExerciseCurrency** | **string** | Required | The currency of the exercise. |
| **OptionExerciseElections** | [List&lt;OptionExerciseElection&gt;](OptionExerciseElection.md) | Optional | Option exercise election for this event. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | Lapse election for this event. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.CallOnIntermediateSecuritiesEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CallOnIntermediateSecuritiesEvent(
    expiryDate: DateTimeOffset.Now,  // optional — The date on which the issue ends.
    paymentDate: DateTimeOffset.Now,  // optional — The payment date of the event.
    newInstrument: new NewInstrument(...),  // required
    unitsRatio: new UnitsRatio(...),  // required
    price: 0.0d,  // required — The price at which new units are purchased.
    exerciseCurrency: "...",  // required — The currency of the exercise.
    optionExerciseElections: new List<OptionExerciseElection>(),  // optional — Option exercise election for this event.
    lapseElections: new List<LapseElection>(),  // optional — Lapse election for this event.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CallOnIntermediateSecuritiesEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [UnitsRatio](UnitsRatio.md)
- [OptionExerciseElection](OptionExerciseElection.md) — used in `OptionExerciseElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

