# Finbourne.Sdk.Lusid.Model.ConsentEvent

Consent Event (CONS) — a voluntary corporate action where an issuer seeks approval  from security holders to amend the terms of an outstanding instrument.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ConsentType** | **string** | Required | The type of consent solicitation.                Supported string (enumeration) values are: [ChangeInTerms, DueAndPayable]. Available values: ChangeInTerms, DueAndPayable. |
| **RecordDate** | **DateTimeOffset** | Optional | The entitlement determination date. |
| **ResponseDeadline** | **DateTimeOffset** | Optional | The last date to submit instructions. |
| **MarketDeadline** | **DateTimeOffset** | Optional | The issuer-set outer deadline. Must be greater than or equal to ResponseDeadline. |
| **EarlyResponseDeadline** | **DateTimeOffset?** | Optional | Deadline for early consent. Required when a CONY-early CashOfferElection is offered.  Must be earlier than ResponseDeadline. |
| **PaymentDate** | **DateTimeOffset?** | Optional | Date on which the consent fee is paid. Required when any CashOfferElection is offered. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | List of possible cash offer elections for this event. Each tier (CONY-standard, CONY-early)  is modelled as a separate entry; the election carries the per-unit fee rate and currency. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | List of possible lapse elections for this event (NOAC, CONN, ABST). |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent. Default: `InstrumentEventTypeEnum.ConsentEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConsentEvent(
    consentType: "...",  // required — The type of consent solicitation.                Supported string (enumeration) values are: [ChangeInTerms, DueAndPayable]. Available values: ChangeInTerms, DueAndPayable.
    recordDate: DateTimeOffset.Now,  // optional — The entitlement determination date.
    responseDeadline: DateTimeOffset.Now,  // optional — The last date to submit instructions.
    marketDeadline: DateTimeOffset.Now,  // optional — The issuer-set outer deadline. Must be greater than or equal to ResponseDeadline.
    earlyResponseDeadline: DateTimeOffset.Now,  // optional — Deadline for early consent. Required when a CONY-early CashOfferElection is offered.  Must be earlier than ResponseDeadline.
    paymentDate: DateTimeOffset.Now,  // optional — Date on which the consent fee is paid. Required when any CashOfferElection is offered.
    cashOfferElections: new List<CashOfferElection>(),  // optional — List of possible cash offer elections for this event. Each tier (CONY-standard, CONY-early)  is modelled as a separate entry; the election carries the per-unit fee rate and currency.
    lapseElections: new List<LapseElection>(),  // optional — List of possible lapse elections for this event (NOAC, CONN, ABST).
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConsentEvent>(json);
```


- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

