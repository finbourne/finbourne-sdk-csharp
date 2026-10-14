# Finbourne.Sdk.Lusid.Model.ConsentEvent

A consent solicitation (CONS) or a bondholder meeting's fee (BMET): voluntary when holders respond to it, mandatory when it pays a fee to every eligible holder without an instruction.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ConsentType** | **string** | Optional | The type of consent solicitation. Optional; omitting it records Unknown.                Supported string (enumeration) values are: [ChangeInTerms, DueAndPayable, Unknown]. Available values: ChangeInTerms, DueAndPayable, Unknown. |
| **RecordDate** | **DateTimeOffset** | Optional | The entitlement determination date. |
| **ResponseDeadline** | **DateTimeOffset** | Optional | The last date to submit instructions. |
| **MarketDeadline** | **DateTimeOffset** | Optional | The issuer-set outer deadline. Must be greater than or equal to ResponseDeadline. |
| **EarlyResponseDeadline** | **DateTimeOffset?** | Optional | Deadline for instructions that qualify for an early fee. Optional. When set, must be earlier than ResponseDeadline. Must be null on a Mandatory event. |
| **PaymentDate** | **DateTimeOffset?** | Optional | Date on which the fee is paid. Required when a CashOfferElection or a fee-bearing ConsentGrantedElection is offered; otherwise must be null. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | Options that pay a cash fee to the holder who chooses them, whatever the vote: for example a fee for voting against, for a split vote or for an ineligible-holder confirmation. Keys are free-form and unique across all election lists. The price is quoted per 1,000 of face for bonds (the current notional at the record date: amortised face for a ComplexBond, inflation-adjusted face for an InflationLinkedBond) and per unit for equities and simple instruments. On a Mandatory event, exactly one, both default and chosen. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | List of possible lapse elections for this event (NOAC). |
| **ConsentGrantedElections** | [List&lt;ConsentGrantedElection&gt;](ConsentGrantedElection.md) | Optional | List of possible consent-granted elections for this event (CONY), each optionally carrying a consent fee. |
| **ConsentDeniedElections** | [List&lt;ConsentDeniedElection&gt;](ConsentDeniedElection.md) | Optional | List of possible consent-denied elections for this event (CONN). |
| **AbstainElections** | [List&lt;AbstainElection&gt;](AbstainElection.md) | Optional | List of possible abstain elections for this event (ABST). |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent. Default: `InstrumentEventTypeEnum.ConsentEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConsentEvent(
    consentType: "...",  // optional — The type of consent solicitation. Optional; omitting it records Unknown.                Supported string (enumeration) values are: [ChangeInTerms, DueAndPayable, Unknown]. Available values: ChangeInTerms, DueAndPayable, Unknown.
    recordDate: DateTimeOffset.Now,  // optional — The entitlement determination date.
    responseDeadline: DateTimeOffset.Now,  // optional — The last date to submit instructions.
    marketDeadline: DateTimeOffset.Now,  // optional — The issuer-set outer deadline. Must be greater than or equal to ResponseDeadline.
    earlyResponseDeadline: DateTimeOffset.Now,  // optional — Deadline for instructions that qualify for an early fee. Optional. When set, must be earlier than ResponseDeadline. Must be null on a Mandatory event.
    paymentDate: DateTimeOffset.Now,  // optional — Date on which the fee is paid. Required when a CashOfferElection or a fee-bearing ConsentGrantedElection is offered; otherwise must be null.
    cashOfferElections: new List<CashOfferElection>(),  // optional — Options that pay a cash fee to the holder who chooses them, whatever the vote: for example a fee for voting against, for a split vote or for an ineligible-holder confirmation. Keys are free-form and unique across all election lists. The price is quoted per 1,000 of face for bonds (the current notional at the record date: amortised face for a ComplexBond, inflation-adjusted face for an InflationLinkedBond) and per unit for equities and simple instruments. On a Mandatory event, exactly one, both default and chosen.
    lapseElections: new List<LapseElection>(),  // optional — List of possible lapse elections for this event (NOAC).
    consentGrantedElections: new List<ConsentGrantedElection>(),  // optional — List of possible consent-granted elections for this event (CONY), each optionally carrying a consent fee.
    consentDeniedElections: new List<ConsentDeniedElection>(),  // optional — List of possible consent-denied elections for this event (CONN).
    abstainElections: new List<AbstainElection>(),  // optional — List of possible abstain elections for this event (ABST).
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent.
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
- [ConsentGrantedElection](ConsentGrantedElection.md) — used in `ConsentGrantedElections`
- [ConsentDeniedElection](ConsentDeniedElection.md) — used in `ConsentDeniedElections`
- [AbstainElection](AbstainElection.md) — used in `AbstainElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

