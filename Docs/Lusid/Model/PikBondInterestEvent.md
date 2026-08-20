# Finbourne.Sdk.Lusid.Model.PikBondInterestEvent

Definition of a PIK Bond Interest Event  This is an event that describes the paid-in-kind portion of a coupon period on a  Payment-in-Kind ComplexBond that is settled by delivering units of another instrument, rather  than in cash or by capitalising the amount into the bond's current face. The interest amount is  converted to units of the deliverable at the delivery price and added to the deliverable's  holding as a new tax lot; the paying bond's own units and current face are unchanged.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ExDate** | **DateTimeOffset** | Optional | The ex date (entitlement date) of the interest |
| **PaymentDate** | **DateTimeOffset** | Optional | The date on which the securities are delivered |
| **Currency** | **string** | Required | The currency in which the interest amount is expressed |
| **CouponPerUnit** | **decimal?** | Optional | The interest amount, in cash terms, per unit of the held bond&#39;s current face |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **DeliveryPrice** | **decimal?** | Optional | The clean price the deliverable is delivered at, as a percentage of its nominal per unit  following bond market convention: 100 is par and 98.5 is a one-and-a-half point discount.  This is not a cash amount per unit. Null is par. It governs how many units the interest  amount buys, not how much face each of those units carries. |
| **DeliveredContractSize** | **decimal?** | Optional | The deliverable&#39;s nominal per unit - its contract size. Null is 1. |
| **DeliveredCurrentFacePerUnit** | **decimal?** | Optional | The current face each delivered unit carries. Null falls back to DeliveredContractSize;  supply it for a seasoned note whose face has already amortised away from its contract size.  When both are absent the delivered lot carries no current face, which is how a deliverable  that is not current-face-based, such as an equity, is expressed. |
| **DeliveredAccruedPerUnit** | **decimal?** | Optional | Interest accrued on the deliverable per delivered unit, settled alongside the clean price  when a seasoned note is delivered mid-period. Null is a fresh issue with nothing accrued. |
| **FractionalUnitsRoundingConvention** | **string** | Optional | The convention used to round the units entitlement. Defaults to Floor.                Supported string (enumeration) values are: [Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BankerRounding]. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding. |
| **FractionalUnitsDecimalPlaces** | **int?** | Optional | The number of decimal places to round to when FractionalUnitsRoundingConvention is RoundToDecimalPlaces. |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | The cash price paid in lieu of the units that could not be delivered. Supplying it, together  with FractionalUnitsCashCurrency, is what settles the undelivered fraction in cash; leave  both absent and the fraction is simply not paid. |
| **FractionalUnitsCashCurrency** | **string** | Optional | The currency of the cash paid in lieu of the undelivered fraction. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent. Default: `InstrumentEventTypeEnum.PikBondInterestEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PikBondInterestEvent(
    exDate: DateTimeOffset.Now,  // optional — The ex date (entitlement date) of the interest
    paymentDate: DateTimeOffset.Now,  // optional — The date on which the securities are delivered
    currency: "...",  // required — The currency in which the interest amount is expressed
    couponPerUnit: 0.0d,  // optional — The interest amount, in cash terms, per unit of the held bond&#39;s current face
    newInstrument: new NewInstrument(...),  // required
    deliveryPrice: 0.0d,  // optional — The clean price the deliverable is delivered at, as a percentage of its nominal per unit  following bond market convention: 100 is par and 98.5 is a one-and-a-half point discount.  This is not a cash amount per unit. Null is par. It governs how many units the interest  amount buys, not how much face each of those units carries.
    deliveredContractSize: 0.0d,  // optional — The deliverable&#39;s nominal per unit - its contract size. Null is 1.
    deliveredCurrentFacePerUnit: 0.0d,  // optional — The current face each delivered unit carries. Null falls back to DeliveredContractSize;  supply it for a seasoned note whose face has already amortised away from its contract size.  When both are absent the delivered lot carries no current face, which is how a deliverable  that is not current-face-based, such as an equity, is expressed.
    deliveredAccruedPerUnit: 0.0d,  // optional — Interest accrued on the deliverable per delivered unit, settled alongside the clean price  when a seasoned note is delivered mid-period. Null is a fresh issue with nothing accrued.
    fractionalUnitsRoundingConvention: "...",  // optional — The convention used to round the units entitlement. Defaults to Floor.                Supported string (enumeration) values are: [Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BankerRounding]. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding.
    fractionalUnitsDecimalPlaces: 0,  // optional — The number of decimal places to round to when FractionalUnitsRoundingConvention is RoundToDecimalPlaces.
    fractionalUnitsCashPrice: 0.0d,  // optional — The cash price paid in lieu of the units that could not be delivered. Supplying it, together  with FractionalUnitsCashCurrency, is what settles the undelivered fraction in cash; leave  both absent and the fraction is simply not paid.
    fractionalUnitsCashCurrency: "...",  // optional — The currency of the cash paid in lieu of the undelivered fraction.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PikBondInterestEvent>(json);
```


- [NewInstrument](NewInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

