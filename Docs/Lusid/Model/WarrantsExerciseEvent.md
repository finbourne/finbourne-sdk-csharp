# Finbourne.Sdk.Lusid.Model.WarrantsExerciseEvent

Warrants Exercise (EXWA) — the holder's election to exercise an outstanding warrant, paying the  strike and receiving the underlying security, or to let it lapse at zero proceeds. Elective  (Voluntary / MandatoryWithChoices) on EquityOption (EquityOptionType = Warrant) and SimpleInstrument.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Optional | The DvP settlement date on which the strike is paid and the underlying is delivered.  Must be on or after PeriodOfActionEnd. |
| **PeriodOfActionStart** | **DateTimeOffset** | Optional | Start of the exercise window. |
| **PeriodOfActionEnd** | **DateTimeOffset** | Optional | End of the exercise window. |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | Holder response deadline. Required when participation is MandatoryWithChoices. |
| **MarketDeadlineDate** | **DateTimeOffset?** | Optional | Market deadline. Required when participation is MandatoryWithChoices. |
| **EarlyResponseDeadline** | **DateTimeOffset?** | Optional | Early response deadline. Optional; populated by some vendor wires. |
| **StrikePerUnit** | **decimal?** | Optional | Cash payable per warrant on exercise. Null-allowed on upsert if the warrant instrument resolves  a non-null EquityOption.Strike (instrument-level fallback applied later). If supplied, must be  strictly positive and accompanied by a StrikeCurrency. |
| **StrikeCurrency** | **string** | Optional | Currency of the strike (ISO 4217 3-letter code). Required if StrikePerUnit is non-null. |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Optional | *No description available.* |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Optional | *No description available.* |
| **FractionDisposition** | **string** | Optional | Handling of fractional underlying units. Defaults to round-down (RDDN) in the holdings engine when null.                Supported string (enumeration) values are: [RDDN, CINL]. Available values: RDDN, CINL. |
| **OptionExerciseElections** | [List&lt;OptionExerciseElection&gt;](OptionExerciseElection.md) | Optional | Option exercise elections for this event. At least one entry. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | Lapse elections for this event. Required when participation is MandatoryWithChoices or when the  issuer publishes a no-action default. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent. Default: `InstrumentEventTypeEnum.WarrantsExerciseEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WarrantsExerciseEvent(
    paymentDate: DateTimeOffset.Now,  // optional — The DvP settlement date on which the strike is paid and the underlying is delivered.  Must be on or after PeriodOfActionEnd.
    periodOfActionStart: DateTimeOffset.Now,  // optional — Start of the exercise window.
    periodOfActionEnd: DateTimeOffset.Now,  // optional — End of the exercise window.
    responseDeadlineDate: DateTimeOffset.Now,  // optional — Holder response deadline. Required when participation is MandatoryWithChoices.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — Market deadline. Required when participation is MandatoryWithChoices.
    earlyResponseDeadline: DateTimeOffset.Now,  // optional — Early response deadline. Optional; populated by some vendor wires.
    strikePerUnit: 0.0d,  // optional — Cash payable per warrant on exercise. Null-allowed on upsert if the warrant instrument resolves  a non-null EquityOption.Strike (instrument-level fallback applied later). If supplied, must be  strictly positive and accompanied by a StrikeCurrency.
    strikeCurrency: "...",  // optional — Currency of the strike (ISO 4217 3-letter code). Required if StrikePerUnit is non-null.
    unitsRatio: new UnitsRatio(...),  // optional
    newInstrument: new NewInstrument(...),  // optional
    fractionDisposition: "...",  // optional — Handling of fractional underlying units. Defaults to round-down (RDDN) in the holdings engine when null.                Supported string (enumeration) values are: [RDDN, CINL]. Available values: RDDN, CINL.
    optionExerciseElections: new List<OptionExerciseElection>(),  // optional — Option exercise elections for this event. At least one entry.
    lapseElections: new List<LapseElection>(),  // optional — Lapse elections for this event. Required when participation is MandatoryWithChoices or when the  issuer publishes a no-action default.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WarrantsExerciseEvent>(json);
```


- [UnitsRatio](UnitsRatio.md)
- [NewInstrument](NewInstrument.md)
- [OptionExerciseElection](OptionExerciseElection.md) — used in `OptionExerciseElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

