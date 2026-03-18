# Finbourne.Sdk.Lusid.Model.TenderEvent

Tender Event (TEND).
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnnouncementDate** | **DateTimeOffset?** | Optional | The date the tender is announced. |
| **ExDate** | **DateTimeOffset** | Optional | The ex date (entitlement date) of the event. |
| **RecordDate** | **DateTimeOffset?** | Optional | Date you have to be the holder of record in order to participate in the tender. |
| **PaymentDate** | **DateTimeOffset** | Optional | The payment date of the event. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | The cash price paid in lieu of fractionalUnits. |
| **FractionalUnitsCashCurrency** | **string** | Optional | The currency of the cash paid in lieu of fractionalUnits. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | List of possible SecurityOfferElections for this event. |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible CashAndSecurityOfferElections for this event. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | List of possible CashOfferElections for this event. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.TenderEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TenderEvent(
    announcementDate: DateTimeOffset.Now,  // optional — The date the tender is announced.
    exDate: DateTimeOffset.Now,  // optional — The ex date (entitlement date) of the event.
    recordDate: DateTimeOffset.Now,  // optional — Date you have to be the holder of record in order to participate in the tender.
    paymentDate: DateTimeOffset.Now,  // optional — The payment date of the event.
    newInstrument: new NewInstrument(...),  // required
    fractionalUnitsCashPrice: 0.0d,  // optional — The cash price paid in lieu of fractionalUnits.
    fractionalUnitsCashCurrency: "...",  // optional — The currency of the cash paid in lieu of fractionalUnits.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — List of possible SecurityOfferElections for this event.
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible CashAndSecurityOfferElections for this event.
    cashOfferElections: new List<CashOfferElection>(),  // optional — List of possible CashOfferElections for this event.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TenderEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

