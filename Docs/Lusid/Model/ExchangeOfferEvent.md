# Finbourne.Sdk.Lusid.Model.ExchangeOfferEvent

Exchange Offer Event (EXOF).
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveDate** | **DateTimeOffset** | Optional | *No description available.* |
| **SettlementDate** | **DateTimeOffset** | Optional | *No description available.* |
| **EventSource** | **string** | Required | *No description available.* |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Optional | *No description available.* |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | List of possible CashOfferElections for this exchange offer event (CASH).    - The event requires at least one election of any type.    - If ParticipationType is Mandatory, CashOfferElection is not permitted.    - If ParticipationType is MandatoryWithChoices or Voluntary, at most one CashOfferElection may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | List of possible SecurityOfferElections for this exchange offer event (SECU).    - The event requires at least one election of any type.    - Any number of SecurityOfferElections may be supplied.    - A NewInstrument is required on the event when this list is non-empty.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two. |
| **MixedLotConstituentsElections** | [List&lt;MixedLotConstituentsElection&gt;](MixedLotConstituentsElection.md) | Optional | List of possible MixedLotConstituentsElections for this exchange offer event.    - The event requires at least one election of any type.    - Any number of MixedLotConstituentsElections may be supplied, up to a limit of 100 entries.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | List of possible LapseElections for this exchange offer event (NOAC).    - The event requires at least one election of any type.    - If ParticipationType is Mandatory, LapseElection is not permitted.    - If ParticipationType is MandatoryWithChoices, any number of LapseElections may be supplied, but none of them may be the default.    - If ParticipationType is Voluntary, at most one LapseElection may be supplied. |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible CashAndSecurityOfferElections for this exchange offer event (CASE).    - The event requires at least one election of any type.    - Any number of CashAndSecurityOfferElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two. |
| **ConsentAndExchangeElections** | [List&lt;ConsentAndExchangeElection&gt;](ConsentAndExchangeElection.md) | Optional | List of possible ConsentAndExchangeElections for this exchange offer event (CEXC).    - The event requires at least one election of any type.    - Any number of ConsentAndExchangeElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two. |
| **AbstainElections** | [List&lt;AbstainElection&gt;](AbstainElection.md) | Optional | List of possible AbstainElections for this exchange offer event (ABST).    - The event requires at least one election of any type.    - Any number of AbstainElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two. |
| **UnknownProceedsElections** | [List&lt;UnknownProceedsElection&gt;](UnknownProceedsElection.md) | Optional | List of possible UnknownProceedsElections for this exchange offer event (UNKNOWN).    - The event requires at least one election of any type.    - Any number of UnknownProceedsElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two. |
| **MinPieceSize** | **decimal?** | Optional | *No description available.* |
| **MinIncrement** | **decimal?** | Optional | *No description available.* |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | *No description available.* |
| **FractionalUnitsCashCurrency** | **string** | Optional | *No description available.* |
| **FractionalUnitsRoundingConvention** | **string** | Optional | The convention used to round the fractional units entitlement. Defaults to Floor. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding. |
| **FractionalUnitsDecimalPlaces** | **int?** | Optional | The number of decimal places to round to when FractionalUnitsRoundingConvention is RoundToDecimalPlaces. |
| **InstructionReference** | **string** | Optional | *No description available.* |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent. Default: `InstrumentEventTypeEnum.ExchangeOfferEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExchangeOfferEvent(
    effectiveDate: DateTimeOffset.Now,  // optional
    settlementDate: DateTimeOffset.Now,  // optional
    eventSource: "...",  // required
    newInstrument: new NewInstrument(...),  // optional
    cashOfferElections: new List<CashOfferElection>(),  // optional — List of possible CashOfferElections for this exchange offer event (CASH).    - The event requires at least one election of any type.    - If ParticipationType is Mandatory, CashOfferElection is not permitted.    - If ParticipationType is MandatoryWithChoices or Voluntary, at most one CashOfferElection may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — List of possible SecurityOfferElections for this exchange offer event (SECU).    - The event requires at least one election of any type.    - Any number of SecurityOfferElections may be supplied.    - A NewInstrument is required on the event when this list is non-empty.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two.
    mixedLotConstituentsElections: new List<MixedLotConstituentsElection>(),  // optional — List of possible MixedLotConstituentsElections for this exchange offer event.    - The event requires at least one election of any type.    - Any number of MixedLotConstituentsElections may be supplied, up to a limit of 100 entries.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two.
    lapseElections: new List<LapseElection>(),  // optional — List of possible LapseElections for this exchange offer event (NOAC).    - The event requires at least one election of any type.    - If ParticipationType is Mandatory, LapseElection is not permitted.    - If ParticipationType is MandatoryWithChoices, any number of LapseElections may be supplied, but none of them may be the default.    - If ParticipationType is Voluntary, at most one LapseElection may be supplied.
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible CashAndSecurityOfferElections for this exchange offer event (CASE).    - The event requires at least one election of any type.    - Any number of CashAndSecurityOfferElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two.
    consentAndExchangeElections: new List<ConsentAndExchangeElection>(),  // optional — List of possible ConsentAndExchangeElections for this exchange offer event (CEXC).    - The event requires at least one election of any type.    - Any number of ConsentAndExchangeElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two.
    abstainElections: new List<AbstainElection>(),  // optional — List of possible AbstainElections for this exchange offer event (ABST).    - The event requires at least one election of any type.    - Any number of AbstainElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two.
    unknownProceedsElections: new List<UnknownProceedsElection>(),  // optional — List of possible UnknownProceedsElections for this exchange offer event (UNKNOWN).    - The event requires at least one election of any type.    - Any number of UnknownProceedsElections may be supplied.    - Exactly one election on the event must be the default, and at most one may be chosen.    - If ParticipationType is Mandatory, the event must carry exactly one election in total; if MandatoryWithChoices, at least two.
    minPieceSize: 0.0d,  // optional
    minIncrement: 0.0d,  // optional
    fractionalUnitsCashPrice: 0.0d,  // optional
    fractionalUnitsCashCurrency: "...",  // optional
    fractionalUnitsRoundingConvention: "...",  // optional — The convention used to round the fractional units entitlement. Defaults to Floor. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding.
    fractionalUnitsDecimalPlaces: 0,  // optional — The number of decimal places to round to when FractionalUnitsRoundingConvention is RoundToDecimalPlaces.
    instructionReference: "...",  // optional
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExchangeOfferEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [MixedLotConstituentsElection](MixedLotConstituentsElection.md) — used in `MixedLotConstituentsElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`
- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [ConsentAndExchangeElection](ConsentAndExchangeElection.md) — used in `ConsentAndExchangeElections`
- [AbstainElection](AbstainElection.md) — used in `AbstainElections`
- [UnknownProceedsElection](UnknownProceedsElection.md) — used in `UnknownProceedsElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

