# Finbourne.Sdk.Lusid.Model.BonusIssueEvent

Representation of a Bonus Issue corporate action.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnnouncementDate** | **DateTimeOffset?** | Optional | The date the Bonus Issue is announced. |
| **ExDate** | **DateTimeOffset** | Optional | The ex-date of the Bonus Issue. |
| **RecordDate** | **DateTimeOffset?** | Optional | The record date of the Bonus Issue. |
| **PaymentDate** | **DateTimeOffset** | Optional | The date the Bonus Issue is executed. |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | Optional. Used in calculating cash-in-lieu of fractional shares. |
| **FractionalUnitsCashCurrency** | **string** | Optional | Optional. Used in calculating cash-in-lieu of fractional shares. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | Possible SecurityElections for this Bonus Issue event, if any. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | Possible CashOfferElections for this Bonus Issue event, if any. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | Possible LapseElections for this Bonus Issue event, if any. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.BonusIssueEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BonusIssueEvent(
    announcementDate: DateTimeOffset.Now,  // optional — The date the Bonus Issue is announced.
    exDate: DateTimeOffset.Now,  // optional — The ex-date of the Bonus Issue.
    recordDate: DateTimeOffset.Now,  // optional — The record date of the Bonus Issue.
    paymentDate: DateTimeOffset.Now,  // optional — The date the Bonus Issue is executed.
    fractionalUnitsCashPrice: 0.0d,  // optional — Optional. Used in calculating cash-in-lieu of fractional shares.
    fractionalUnitsCashCurrency: "...",  // optional — Optional. Used in calculating cash-in-lieu of fractional shares.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — Possible SecurityElections for this Bonus Issue event, if any.
    cashOfferElections: new List<CashOfferElection>(),  // optional — Possible CashOfferElections for this Bonus Issue event, if any.
    lapseElections: new List<LapseElection>(),  // optional — Possible LapseElections for this Bonus Issue event, if any.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BonusIssueEvent>(json);
```


- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

