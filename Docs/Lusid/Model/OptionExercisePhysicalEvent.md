# Finbourne.Sdk.Lusid.Model.OptionExercisePhysicalEvent

Event for physical option exercises.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExerciseDate** | **DateTimeOffset?** | Optional | The exercise date of the option. |
| **DeliveryDate** | **DateTimeOffset?** | Optional | The delivery date of the option. |
| **ExerciseType** | **string** | Required | The optionality type of the underlying option e.g. American, European.    Supported string (enumeration) values are: [European, Bermudan, American]. |
| **MaturityDate** | **DateTimeOffset** | Optional | The maturity date of the option. |
| **Moneyness** | **string** | Optional | The moneyness of the option e.g. InTheMoney, OutOfTheMoney.    Supported string (enumeration) values are: [InTheMoney, OutOfTheMoney, AtTheMoney]. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **OptionExerciseElections** | [List&lt;OptionExerciseElection&gt;](OptionExerciseElection.md) | Optional | Option exercise election for this OptionExercisePhysicalEvent. |
| **OptionType** | **string** | Required | Type of optionality that is present e.g. call, put.    Supported string (enumeration) values are: [Call, Put]. |
| **StartDate** | **DateTimeOffset** | Optional | The trade date of the option. |
| **StrikeCurrency** | **string** | Required | The strike currency of the equity option. |
| **StrikePerUnit** | **decimal** | Required | The strike of the equity option times the number of shares to exchange if exercised. |
| **UnderlyingValuePerUnit** | **decimal?** | Optional | The underlying price times the number of shares to exchange if exercised. |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Required | *No description available.* |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.OptionExercisePhysicalEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OptionExercisePhysicalEvent(
    exerciseDate: DateTimeOffset.Now,  // optional — The exercise date of the option.
    deliveryDate: DateTimeOffset.Now,  // optional — The delivery date of the option.
    exerciseType: "...",  // required — The optionality type of the underlying option e.g. American, European.    Supported string (enumeration) values are: [European, Bermudan, American].
    maturityDate: DateTimeOffset.Now,  // optional — The maturity date of the option.
    moneyness: "...",  // optional — The moneyness of the option e.g. InTheMoney, OutOfTheMoney.    Supported string (enumeration) values are: [InTheMoney, OutOfTheMoney, AtTheMoney].
    newInstrument: new NewInstrument(...),  // required
    optionExerciseElections: new List<OptionExerciseElection>(),  // optional — Option exercise election for this OptionExercisePhysicalEvent.
    optionType: "...",  // required — Type of optionality that is present e.g. call, put.    Supported string (enumeration) values are: [Call, Put].
    startDate: DateTimeOffset.Now,  // optional — The trade date of the option.
    strikeCurrency: "...",  // required — The strike currency of the equity option.
    strikePerUnit: 0.0d,  // required — The strike of the equity option times the number of shares to exchange if exercised.
    underlyingValuePerUnit: 0.0d,  // optional — The underlying price times the number of shares to exchange if exercised.
    unitsRatio: new UnitsRatio(...),  // required
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OptionExercisePhysicalEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [OptionExerciseElection](OptionExerciseElection.md) — used in `OptionExerciseElections`
- [UnitsRatio](UnitsRatio.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

