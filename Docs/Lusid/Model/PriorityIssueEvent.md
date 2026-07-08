# Finbourne.Sdk.Lusid.Model.PriorityIssueEvent

Priority Issue Event (PRIO) — a voluntary corporate action in which an issuer offers existing  security holders preferential rights to subscribe for new securities at a defined subscription  price before the offer is opened to the wider market. Holders may subscribe up to a basic  entitlement (SECU) and, where offered, apply for additional securities beyond the basic  entitlement (OVER, subject to proration). No instruction (NOAC) results in no transaction.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnnouncementDate** | **DateTimeOffset?** | Optional | Date on which the priority issue was announced. Optional, informational. |
| **ExDate** | **DateTimeOffset?** | Optional | First business day on which the security trades without the entitlement. Optional.  When not supplied, transaction-template generation falls back to RecordDate |
| **RecordDate** | **DateTimeOffset** | Optional | The entitlement determination date — holders of record on this date are eligible to subscribe. |
| **ResponseDeadline** | **DateTimeOffset** | Optional | The account-servicer instruction deadline. Must be less than or equal to MarketDeadline. |
| **MarketDeadline** | **DateTimeOffset** | Optional | The issuer-agent deadline. |
| **PaymentDate** | **DateTimeOffset** | Optional | Date on which cash is debited and the new securities are credited. |
| **SecuritySettlementDate** | **DateTimeOffset?** | Optional | Date the security leg settles when it differs from the cash leg. Optional.  When not supplied, transaction-template generation falls back to PaymentDate |
| **SubscriptionPrice** | **decimal** | Optional | The subscription price per new unit. Applies to both SECU and OVER subscriptions.  Must be greater than zero. |
| **SubscriptionCurrency** | **string** | Optional | Currency of the SubscriptionPrice. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Optional | *No description available.* |
| **ProrationRate** | **decimal?** | Optional | The proration rate applied to OVER subscriptions when the offer is oversubscribed.  Treated as 1 (full allocation) when not supplied. Must be greater than 0 and less than  or equal to 1. SECU basic entitlement is never prorated. |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | Price per fractional unit used to compute cash-in-lieu for fractional entitlement remainders.  When not supplied, fractional residuals are discarded with no cash-in-lieu.  Forms an optional pair with FractionalUnitsCashCurrency — both must be supplied together. |
| **FractionalUnitsCashCurrency** | **string** | Optional | Currency of FractionalUnitsCashPrice. Required if and only if FractionalUnitsCashPrice is supplied. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | Security offer elections — exactly one entry keyed &#39;SECU&#39; (basic entitlement) and an optional  entry keyed &#39;OVER&#39; (over-subscription) when the issuer offers the over-subscription facility. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | Lapse elections — exactly one entry keyed &#39;NOAC&#39;, recording the holder&#39;s explicit no-action election. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent. Default: `InstrumentEventTypeEnum.PriorityIssueEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PriorityIssueEvent(
    announcementDate: DateTimeOffset.Now,  // optional — Date on which the priority issue was announced. Optional, informational.
    exDate: DateTimeOffset.Now,  // optional — First business day on which the security trades without the entitlement. Optional.  When not supplied, transaction-template generation falls back to RecordDate
    recordDate: DateTimeOffset.Now,  // optional — The entitlement determination date — holders of record on this date are eligible to subscribe.
    responseDeadline: DateTimeOffset.Now,  // optional — The account-servicer instruction deadline. Must be less than or equal to MarketDeadline.
    marketDeadline: DateTimeOffset.Now,  // optional — The issuer-agent deadline.
    paymentDate: DateTimeOffset.Now,  // optional — Date on which cash is debited and the new securities are credited.
    securitySettlementDate: DateTimeOffset.Now,  // optional — Date the security leg settles when it differs from the cash leg. Optional.  When not supplied, transaction-template generation falls back to PaymentDate
    subscriptionPrice: 0.0d,  // optional — The subscription price per new unit. Applies to both SECU and OVER subscriptions.  Must be greater than zero.
    subscriptionCurrency: "...",  // optional — Currency of the SubscriptionPrice.
    newInstrument: new NewInstrument(...),  // optional
    prorationRate: 0.0d,  // optional — The proration rate applied to OVER subscriptions when the offer is oversubscribed.  Treated as 1 (full allocation) when not supplied. Must be greater than 0 and less than  or equal to 1. SECU basic entitlement is never prorated.
    fractionalUnitsCashPrice: 0.0d,  // optional — Price per fractional unit used to compute cash-in-lieu for fractional entitlement remainders.  When not supplied, fractional residuals are discarded with no cash-in-lieu.  Forms an optional pair with FractionalUnitsCashCurrency — both must be supplied together.
    fractionalUnitsCashCurrency: "...",  // optional — Currency of FractionalUnitsCashPrice. Required if and only if FractionalUnitsCashPrice is supplied.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — Security offer elections — exactly one entry keyed &#39;SECU&#39; (basic entitlement) and an optional  entry keyed &#39;OVER&#39; (over-subscription) when the issuer offers the over-subscription facility.
    lapseElections: new List<LapseElection>(),  // optional — Lapse elections — exactly one entry keyed &#39;NOAC&#39;, recording the holder&#39;s explicit no-action election.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PriorityIssueEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

