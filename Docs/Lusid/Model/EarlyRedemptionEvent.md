# Finbourne.Sdk.Lusid.Model.EarlyRedemptionEvent

Early redemption as a consequence of a bond being called or putted.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveDate** | **DateTimeOffset?** | Optional | Date of redemption.  For internally generated European callables, this is set to the exercise date.  For internally generated American callables, this is set to the start of the exercise period. |
| **Currency** | **string** | Required | Currency of the redemption. |
| **EarlyRedemptionElections** | [List&lt;EarlyRedemptionElection&gt;](EarlyRedemptionElection.md) | Required | EarlyRedemptionElection for the redemption.  Used to trigger the redemption. |
| **RedemptionPercentage** | **decimal** | Optional | Percentage of the original issue that is redeemed, where 0.5 implies 50%.  Defaults to 1 if not set.  Must be between 0 and 1. |
| **PricePerUnit** | **decimal?** | Optional | The price, or strike, that each unit is redeemed at. |
| **AccruedInterestPerUnit** | **decimal?** | Optional | Unpaid accrued interest also repaid as part of the redemption, per unit.  Optional field.  If left empty, will be resolved internally by calculating the accrued owed on the EffectiveDate.  This process may require additional market data. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.EarlyRedemptionEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EarlyRedemptionEvent(
    effectiveDate: DateTimeOffset.Now,  // optional — Date of redemption.  For internally generated European callables, this is set to the exercise date.  For internally generated American callables, this is set to the start of the exercise period.
    currency: "...",  // required — Currency of the redemption.
    earlyRedemptionElections: new List<EarlyRedemptionElection>(),  // required — EarlyRedemptionElection for the redemption.  Used to trigger the redemption.
    redemptionPercentage: 0.0d,  // optional — Percentage of the original issue that is redeemed, where 0.5 implies 50%.  Defaults to 1 if not set.  Must be between 0 and 1.
    pricePerUnit: 0.0d,  // optional — The price, or strike, that each unit is redeemed at.
    accruedInterestPerUnit: 0.0d,  // optional — Unpaid accrued interest also repaid as part of the redemption, per unit.  Optional field.  If left empty, will be resolved internally by calculating the accrued owed on the EffectiveDate.  This process may require additional market data.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EarlyRedemptionEvent>(json);
```


- [EarlyRedemptionElection](EarlyRedemptionElection.md) — used in `EarlyRedemptionElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

