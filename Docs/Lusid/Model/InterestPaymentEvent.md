# Finbourne.Sdk.Lusid.Model.InterestPaymentEvent

Interest Payment event (INTR). A cash distribution of interest from a debt issuer to its noteholders,  carrying a per-unit absolute interest rate on each CashElection. Supports Mandatory  (single declared election) and MandatoryWithChoices (one election per offered currency) participation.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecordDate** | **DateTimeOffset** | Optional | The record-date cut-off determining entitlement. Required. Map from the vendor RecordDate (NOT the  ExDate sentinel). |
| **PaymentDate** | **DateTimeOffset** | Optional | The date the interest is paid to noteholders. Required. Also the effective date of the event. |
| **ResponseDeadline** | **DateTimeOffset?** | Optional | The holder-instruction deadline. Required for MandatoryWithChoices; must be null for Mandatory. |
| **MarketDeadline** | **DateTimeOffset?** | Optional | The market-organisation deadline. Required for MandatoryWithChoices; must be null for Mandatory. |
| **AnnouncementDate** | **DateTimeOffset?** | Optional | The date the event was announced by the issuer. Optional. |
| **CashElections** | [List&lt;CashElection&gt;](CashElection.md) | Required | The cash elections for this event. For Mandatory participation a single declared election is supplied  with IsDeclared, IsDefault and IsChosen all true; for MandatoryWithChoices one entry per offered  currency is supplied, with exactly one declared, one default and one chosen. Every election carries a  per-unit absolute (signed) DividendRate and an ExchangeRate of 1. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent. Default: `InstrumentEventTypeEnum.InterestPaymentEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InterestPaymentEvent(
    recordDate: DateTimeOffset.Now,  // optional — The record-date cut-off determining entitlement. Required. Map from the vendor RecordDate (NOT the  ExDate sentinel).
    paymentDate: DateTimeOffset.Now,  // optional — The date the interest is paid to noteholders. Required. Also the effective date of the event.
    responseDeadline: DateTimeOffset.Now,  // optional — The holder-instruction deadline. Required for MandatoryWithChoices; must be null for Mandatory.
    marketDeadline: DateTimeOffset.Now,  // optional — The market-organisation deadline. Required for MandatoryWithChoices; must be null for Mandatory.
    announcementDate: DateTimeOffset.Now,  // optional — The date the event was announced by the issuer. Optional.
    cashElections: new List<CashElection>(),  // required — The cash elections for this event. For Mandatory participation a single declared election is supplied  with IsDeclared, IsDefault and IsChosen all true; for MandatoryWithChoices one entry per offered  currency is supplied, with exactly one declared, one default and one chosen. Every election carries a  per-unit absolute (signed) DividendRate and an ExchangeRate of 1.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InterestPaymentEvent>(json);
```


- [CashElection](CashElection.md) — used in `CashElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

