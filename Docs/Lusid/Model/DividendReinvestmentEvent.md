# Finbourne.Sdk.Lusid.Model.DividendReinvestmentEvent

Event for dividend reinvestments.  Elections for cash or the associated security.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnnouncementDate** | **DateTimeOffset?** | Optional | Date on which the dividend was announced / declared. |
| **CashElections** | [List&lt;CashElection&gt;](CashElection.md) | Required | CashElection for this DividendReinvestmentEvent |
| **ExDate** | **DateTimeOffset** | Optional | The first business day on which the dividend is not owed to the buying party.  Typically this is T-1 from the RecordDate. |
| **PaymentDate** | **DateTimeOffset** | Optional | The date the company pays out dividends to shareholders. |
| **RecordDate** | **DateTimeOffset?** | Optional | Date you have to be the holder of record in order to participate in the tender. |
| **SecurityElections** | [List&lt;SecurityElection&gt;](SecurityElection.md) | Required | SecurityElection for this DividendReinvestmentEvent |
| **SecuritySettlementDate** | **DateTimeOffset?** | Optional | The settlement date of the additional units.  Equal to the PaymentDate if not provided. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.DividendReinvestmentEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DividendReinvestmentEvent(
    announcementDate: DateTimeOffset.Now,  // optional — Date on which the dividend was announced / declared.
    cashElections: new List<CashElection>(),  // required — CashElection for this DividendReinvestmentEvent
    exDate: DateTimeOffset.Now,  // optional — The first business day on which the dividend is not owed to the buying party.  Typically this is T-1 from the RecordDate.
    paymentDate: DateTimeOffset.Now,  // optional — The date the company pays out dividends to shareholders.
    recordDate: DateTimeOffset.Now,  // optional — Date you have to be the holder of record in order to participate in the tender.
    securityElections: new List<SecurityElection>(),  // required — SecurityElection for this DividendReinvestmentEvent
    securitySettlementDate: DateTimeOffset.Now,  // optional — The settlement date of the additional units.  Equal to the PaymentDate if not provided.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DividendReinvestmentEvent>(json);
```


- [CashElection](CashElection.md) — used in `CashElections`
- [SecurityElection](SecurityElection.md) — used in `SecurityElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

