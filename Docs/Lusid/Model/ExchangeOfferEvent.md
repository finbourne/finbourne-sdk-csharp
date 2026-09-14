# Finbourne.Sdk.Lusid.Model.ExchangeOfferEvent

> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveDate** | **DateTimeOffset** | Optional | *No description available.* |
| **SettlementDate** | **DateTimeOffset** | Optional | *No description available.* |
| **EventSource** | **string** | Required | *No description available.* |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Optional | *No description available.* |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | *No description available.* |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | *No description available.* |
| **MixedLotConstituentsElections** | [List&lt;MixedLotConstituentsElection&gt;](MixedLotConstituentsElection.md) | Optional | *No description available.* |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | *No description available.* |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible CashAndSecurityOfferElections for this exchange offer event. |
| **ConsentAndExchangeElections** | [List&lt;ConsentAndExchangeElection&gt;](ConsentAndExchangeElection.md) | Optional | List of possible consent-and-exchange elections for this event (CTEN-style consent paired with the exchange). |
| **AbstainElections** | [List&lt;AbstainElection&gt;](AbstainElection.md) | Optional | List of possible abstain elections for this event (ABST) — decline to vote on the consent. |
| **UnknownProceedsElections** | [List&lt;UnknownProceedsElection&gt;](UnknownProceedsElection.md) | Optional | List of possible unknown-proceeds elections for this event (UNKNOWN) — the outturn is not yet known. |
| **MinPieceSize** | **decimal?** | Optional | *No description available.* |
| **MinIncrement** | **decimal?** | Optional | *No description available.* |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | *No description available.* |
| **FractionalUnitsCashCurrency** | **string** | Optional | *No description available.* |
| **FractionalUnitsRoundingConvention** | **string** | Optional | The convention used to round the fractional units entitlement. Defaults to Floor. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding. |
| **FractionalUnitsDecimalPlaces** | **int?** | Optional | The number of decimal places to round to when FractionalUnitsRoundingConvention is RoundToDecimalPlaces. |
| **InstructionReference** | **string** | Optional | *No description available.* |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent. Default: `InstrumentEventTypeEnum.ExchangeOfferEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExchangeOfferEvent(
    effectiveDate: DateTimeOffset.Now,  // optional
    settlementDate: DateTimeOffset.Now,  // optional
    eventSource: "...",  // required
    newInstrument: new NewInstrument(...),  // optional
    cashOfferElections: new List<CashOfferElection>(),  // optional
    securityOfferElections: new List<SecurityOfferElection>(),  // optional
    mixedLotConstituentsElections: new List<MixedLotConstituentsElection>(),  // optional
    lapseElections: new List<LapseElection>(),  // optional
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible CashAndSecurityOfferElections for this exchange offer event.
    consentAndExchangeElections: new List<ConsentAndExchangeElection>(),  // optional — List of possible consent-and-exchange elections for this event (CTEN-style consent paired with the exchange).
    abstainElections: new List<AbstainElection>(),  // optional — List of possible abstain elections for this event (ABST) — decline to vote on the consent.
    unknownProceedsElections: new List<UnknownProceedsElection>(),  // optional — List of possible unknown-proceeds elections for this event (UNKNOWN) — the outturn is not yet known.
    minPieceSize: 0.0d,  // optional
    minIncrement: 0.0d,  // optional
    fractionalUnitsCashPrice: 0.0d,  // optional
    fractionalUnitsCashCurrency: "...",  // optional
    fractionalUnitsRoundingConvention: "...",  // optional — The convention used to round the fractional units entitlement. Defaults to Floor. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding.
    fractionalUnitsDecimalPlaces: 0,  // optional — The number of decimal places to round to when FractionalUnitsRoundingConvention is RoundToDecimalPlaces.
    instructionReference: "...",  // optional
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent.
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
- [CashOfferElection](CashOfferElection.md)
- [SecurityOfferElection](SecurityOfferElection.md)
- [MixedLotConstituentsElection](MixedLotConstituentsElection.md)
- [LapseElection](LapseElection.md)
- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [ConsentAndExchangeElection](ConsentAndExchangeElection.md) — used in `ConsentAndExchangeElections`
- [AbstainElection](AbstainElection.md) — used in `AbstainElections`
- [UnknownProceedsElection](UnknownProceedsElection.md) — used in `UnknownProceedsElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

