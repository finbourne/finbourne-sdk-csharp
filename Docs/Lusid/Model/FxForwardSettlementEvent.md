# Finbourne.Sdk.Lusid.Model.FxForwardSettlementEvent

Settlement for FX Forward, including NDF and deliverable.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MaturityDate** | **DateTimeOffset** | Optional | Maturity date of the forward |
| **DomAmountPerUnit** | **decimal** | Required | Amount per unit in the DomCcy (domestic currency) |
| **DomCcy** | **string** | Required | The domestic currency of the forward |
| **FgnAmountPerUnit** | **decimal** | Required | Amount per unit in the FgnCcy (foreign currency) |
| **FgnCcy** | **string** | Required | The foreign currency of the forward. |
| **IsNdf** | **bool** | Required | Is this settlement corresponding to a deliverable forward, or an NDF |
| **FixingDate** | **DateTimeOffset?** | Optional | Optional.  Required if the event is an NDF (i.e. if IsNdf &#x3D; true).  Date of the FxRate fixings. |
| **SettlementCcy** | **string** | Optional | Optional.  Required if the event is an NDF (i.e. if IsNdf &#x3D; true).  May be set to either DomCcy or FgnCcy, or a third currency. |
| **CashFlowPerUnit** | **decimal?** | Optional | Optional.  Required if the event is an NDF (i.e. if IsNdf &#x3D; true).  CashFlow per unit.  Paid in the SettlementCcy. |
| **DomesticToForeignRate** | **decimal?** | Optional | Domestic currency to foreign currency FX rate.  Not required, only used to override quotes. |
| **DomesticToSettlementRate** | **decimal?** | Optional | Domestic currency to settlement currency FX rate  Not required, only used to override quotes. |
| **ForeignToSettlementRate** | **decimal?** | Optional | Foreign currency to settlement currency FX rate  Not required, only used to override quotes. *(read-only)* |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.FxForwardSettlementEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FxForwardSettlementEvent(
    maturityDate: DateTimeOffset.Now,  // optional — Maturity date of the forward
    domAmountPerUnit: 0.0d,  // required — Amount per unit in the DomCcy (domestic currency)
    domCcy: "...",  // required — The domestic currency of the forward
    fgnAmountPerUnit: 0.0d,  // required — Amount per unit in the FgnCcy (foreign currency)
    fgnCcy: "...",  // required — The foreign currency of the forward.
    isNdf: true,  // required — Is this settlement corresponding to a deliverable forward, or an NDF
    fixingDate: DateTimeOffset.Now,  // optional — Optional.  Required if the event is an NDF (i.e. if IsNdf &#x3D; true).  Date of the FxRate fixings.
    settlementCcy: "...",  // optional — Optional.  Required if the event is an NDF (i.e. if IsNdf &#x3D; true).  May be set to either DomCcy or FgnCcy, or a third currency.
    cashFlowPerUnit: 0.0d,  // optional — Optional.  Required if the event is an NDF (i.e. if IsNdf &#x3D; true).  CashFlow per unit.  Paid in the SettlementCcy.
    domesticToForeignRate: 0.0d,  // optional — Domestic currency to foreign currency FX rate.  Not required, only used to override quotes.
    domesticToSettlementRate: 0.0d,  // optional — Domestic currency to settlement currency FX rate  Not required, only used to override quotes.
    foreignToSettlementRate: 0.0d,  // optional — Foreign currency to settlement currency FX rate  Not required, only used to override quotes.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FxForwardSettlementEvent>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

