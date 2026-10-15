# Finbourne.Sdk.Lusid.Model.InstalmentCallEvent

Instalment Call Event (PPMT) — the issuer calls the next instalment due on a partly-paid equity line.  The holder pays the call price per unit and the holding moves from the partly-paid line to the  line carrying the higher paid-up amount. Under MandatoryWithChoices the holder may instead lapse,  in which case nothing moves and the partly-paid line survives.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PaymentDate** | **DateTimeOffset** | Optional | The date on which the call cash and the replacement units settle. |
| **RecordDate** | **DateTimeOffset?** | Optional | The date on which entitlement is struck. Optional; when absent, entitlement strikes on the payment date. |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | The deadline by which the holder must instruct. Required when the participation type is  MandatoryWithChoices; must be null when it is Mandatory. |
| **MarketDeadlineDate** | **DateTimeOffset?** | Optional | The deadline by which the custodian must forward instructions to the market. Required when the  participation type is MandatoryWithChoices; must be null when it is Mandatory. |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **UnitsRatio** | [UnitsRatio](UnitsRatio.md) | Required | *No description available.* |
| **CallPricePerUnit** | **decimal** | Required | The amount of money payable per eligible unit on this instalment, in the call currency.  This is money per unit, not a percentage of the issue price: a 40 per cent call on a 2.50 issue  price is supplied as 1.00. |
| **CallCurrency** | **string** | Required | The currency in which the call settles. Must match the currency of the new instrument. |
| **OptionExerciseElections** | [List&lt;OptionExerciseElection&gt;](OptionExerciseElection.md) | Optional | The election to pay the call and receive the new instrument. Exactly one is required.  Under Mandatory participation it must be both default and chosen. |
| **LapseElections** | [List&lt;LapseElection&gt;](LapseElection.md) | Optional | The election to decline the call, leaving the partly-paid line unchanged. Exactly one is required  under MandatoryWithChoices participation; none may be supplied under Mandatory participation. |
| **FractionalUnitsRoundingConvention** | **string** | Optional | The convention used to round the fractional units entitlement. Defaults to Floor.  Supported values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, BankerRounding. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding. |
| **FractionalUnitsDecimalPlaces** | **int?** | Optional | The number of decimal places to round to. Not used by any of the supported rounding conventions. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent, InstalmentCallEvent. Default: `InstrumentEventTypeEnum.InstalmentCallEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstalmentCallEvent(
    paymentDate: DateTimeOffset.Now,  // optional — The date on which the call cash and the replacement units settle.
    recordDate: DateTimeOffset.Now,  // optional — The date on which entitlement is struck. Optional; when absent, entitlement strikes on the payment date.
    responseDeadlineDate: DateTimeOffset.Now,  // optional — The deadline by which the holder must instruct. Required when the participation type is  MandatoryWithChoices; must be null when it is Mandatory.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — The deadline by which the custodian must forward instructions to the market. Required when the  participation type is MandatoryWithChoices; must be null when it is Mandatory.
    newInstrument: new NewInstrument(...),  // required
    unitsRatio: new UnitsRatio(...),  // required
    callPricePerUnit: 0.0d,  // required — The amount of money payable per eligible unit on this instalment, in the call currency.  This is money per unit, not a percentage of the issue price: a 40 per cent call on a 2.50 issue  price is supplied as 1.00.
    callCurrency: "...",  // required — The currency in which the call settles. Must match the currency of the new instrument.
    optionExerciseElections: new List<OptionExerciseElection>(),  // optional — The election to pay the call and receive the new instrument. Exactly one is required.  Under Mandatory participation it must be both default and chosen.
    lapseElections: new List<LapseElection>(),  // optional — The election to decline the call, leaving the partly-paid line unchanged. Exactly one is required  under MandatoryWithChoices participation; none may be supplied under Mandatory participation.
    fractionalUnitsRoundingConvention: "...",  // optional — The convention used to round the fractional units entitlement. Defaults to Floor.  Supported values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, BankerRounding. Available values: Floor, Ceiling, RoundHalfUp, RoundHalfDown, RoundToDecimalPlaces, BuyUp, BankerRounding.
    fractionalUnitsDecimalPlaces: 0,  // optional — The number of decimal places to round to. Not used by any of the supported rounding conventions.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent, WarrantsExerciseEvent, PariPassuEvent, ChangeEvent, PikBondCouponEvent, PikBondCashCouponEvent, PikBondInterestCapitalisationEvent, PikBondPrincipalEvent, DelistingEvent, PikBondInterestEvent, CommodityForwardCashSettlementEvent, PaymentInKindEvent, CommodityForwardPhysicalSettlementEvent, CancelSwapEvent, BondOptionTerminationEvent, TerminationEvent, CommodityCalendarSwapCashFlowEvent, DepositSweepEvent, BondForwardCashSettlementEvent, BondForwardTerminationEvent, AmendCommitmentEvent, CapitalCallEvent, FundDistributionEvent, NavReportEvent, DividendSuspensionEvent, LoanInterestCapitalisationEvent, TotalReturnSwapCashFlowEvent, GlobalLoanFacilityReinitialisationEvent, InvestorLoanFacilityReinitialisationEvent, CapitalCallReceiptEvent, RecallableCapitalExpiryEvent, CapitalInterestTransferEvent, FacilityDrawEvent, FacilityRepaymentEvent, FacilityInterestEvent, FacilityCommitmentFeeEvent, InstalmentCallEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstalmentCallEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [UnitsRatio](UnitsRatio.md)
- [OptionExerciseElection](OptionExerciseElection.md) — used in `OptionExerciseElections`
- [LapseElection](LapseElection.md) — used in `LapseElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

