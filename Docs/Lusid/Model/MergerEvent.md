# Finbourne.Sdk.Lusid.Model.MergerEvent

Merger Event (MRGR).
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AnnouncementDate** | **DateTimeOffset?** | Optional | The date the merger is announced. |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible CashAndSecurityOfferElections for this merger event |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | List of possible CashOfferElections for this merger event |
| **ExDate** | **DateTimeOffset** | Optional | The first date on which the holder of record of the original shares has entitled ownership of the new shares. |
| **FractionalUnitsCashCurrency** | **string** | Optional | Optional. Used in calculating cash-in-lieu of fractional shares. |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | Optional. Used in calculating cash-in-lieu of fractional shares. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **PaymentDate** | **DateTimeOffset** | Optional | Date on which the merger takes place. |
| **RecordDate** | **DateTimeOffset?** | Optional | Optional. Date you have to be the holder of record of the original shares in order to receive the new shares. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | List of possible SecurityOfferElections for this merger event |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.MergerEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MergerEvent(
    announcementDate: DateTimeOffset.Now,  // optional — The date the merger is announced.
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible CashAndSecurityOfferElections for this merger event
    cashOfferElections: new List<CashOfferElection>(),  // optional — List of possible CashOfferElections for this merger event
    exDate: DateTimeOffset.Now,  // optional — The first date on which the holder of record of the original shares has entitled ownership of the new shares.
    fractionalUnitsCashCurrency: "...",  // optional — Optional. Used in calculating cash-in-lieu of fractional shares.
    fractionalUnitsCashPrice: 0.0d,  // optional — Optional. Used in calculating cash-in-lieu of fractional shares.
    newInstrument: new NewInstrument(...),  // required
    paymentDate: DateTimeOffset.Now,  // optional — Date on which the merger takes place.
    recordDate: DateTimeOffset.Now,  // optional — Optional. Date you have to be the holder of record of the original shares in order to receive the new shares.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — List of possible SecurityOfferElections for this merger event
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MergerEvent>(json);
```


- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`
- [NewInstrument](NewInstrument.md)
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

