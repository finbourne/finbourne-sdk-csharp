# Finbourne.Sdk.Lusid.Model.PartialDefeasanceEvent

Partial Defeasance event (PDEF). A mandatory notification that a bond issuer has escrow-funded  (defeased) a portion of an outstanding issue. No cash flows to holders at this event; the position  is marked pre-refunded and its effective maturity is updated to the future call date carried in  ActualPayDate. The actual cash and position retirement arrive later via a separate  mandatory call event. Supports a Partial Pre-Refunding variant (PPRE).
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RefundedFraction** | **decimal** | Required | The issue-level fraction allocated to the refunded (pre-refunded / escrowed) portion. Strictly  in the half-open interval (0, 1]; the non-refunded fraction is the derived complement. This is a  required field. |
| **EffectiveDate** | **DateTimeOffset** | Optional | The date the defeasance status takes effect on the position. This is a required field. |
| **ActualPayDate** | **DateTimeOffset** | Optional | The future call date when the bond will actually be retired, used to update the position&#39;s  effective maturity in analytics. Must be on or after EffectiveDate. This is a  required field. |
| **RefundedInstrument** | [NewInstrument](NewInstrument.md) | Optional | *No description available.* |
| **NewSecuritiesIndicator** | **string** | Optional | Optional audit field preserving the wire-side codeword used for the refunded portion.  Supported string (enumeration) values are: [REFU, DEFE]. Both encodings carry identical semantics. Available values: REFU, DEFE. |
| **AdditionalBusinessProcess** | **string** | Optional | Optional variant indicator. Supported string (enumeration) values are: [PPRE]. Absence (null)  encodes the default Partial Defeasance variant. Available values: PPRE. |
| **LotteryDate** | **DateTimeOffset?** | Optional | Optional. The wire&#39;s lottery date; null when the wire carried a sentinel value. |
| **PublicationDate** | **DateTimeOffset?** | Optional | Optional informational date identifying when the defeasance was publicly noticed. |
| **RecordDate** | **DateTimeOffset?** | Optional | Optional. The wire&#39;s record date; typically null for a notification event with no distribution. |
| **AnnouncementDate** | **DateTimeOffset?** | Optional | Optional informational announcement date; null when not provided. |
| **InstrumentEventType** | **string** | Required | The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent. Default: `InstrumentEventTypeEnum.PartialDefeasanceEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartialDefeasanceEvent(
    refundedFraction: 0.0d,  // required — The issue-level fraction allocated to the refunded (pre-refunded / escrowed) portion. Strictly  in the half-open interval (0, 1]; the non-refunded fraction is the derived complement. This is a  required field.
    effectiveDate: DateTimeOffset.Now,  // optional — The date the defeasance status takes effect on the position. This is a required field.
    actualPayDate: DateTimeOffset.Now,  // optional — The future call date when the bond will actually be retired, used to update the position&#39;s  effective maturity in analytics. Must be on or after EffectiveDate. This is a  required field.
    refundedInstrument: new NewInstrument(...),  // optional
    newSecuritiesIndicator: "...",  // optional — Optional audit field preserving the wire-side codeword used for the refunded portion.  Supported string (enumeration) values are: [REFU, DEFE]. Both encodings carry identical semantics. Available values: REFU, DEFE.
    additionalBusinessProcess: "...",  // optional — Optional variant indicator. Supported string (enumeration) values are: [PPRE]. Absence (null)  encodes the default Partial Defeasance variant. Available values: PPRE.
    lotteryDate: DateTimeOffset.Now,  // optional — Optional. The wire&#39;s lottery date; null when the wire carried a sentinel value.
    publicationDate: DateTimeOffset.Now,  // optional — Optional informational date identifying when the defeasance was publicly noticed.
    recordDate: DateTimeOffset.Now,  // optional — Optional. The wire&#39;s record date; typically null for a notification event with no distribution.
    announcementDate: DateTimeOffset.Now,  // optional — Optional informational announcement date; null when not provided.
    instrumentEventType: "..."  // required — The Type of Event. Available values: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent, ConsentEvent, DrawingEvent, CapitalGainsDistributionEvent, ExchangeOfferEvent, DutchAuctionEvent, WorthlessEvent, PutRedemptionEvent, LoanFacilityDelayedCompensationPaymentEvent, InterestPaymentEvent, PriorityIssueEvent, ClassActionEvent, BankruptcyEvent, LiquidationPaymentEvent, PartialDefeasanceEvent, SecurityWriteOffEvent.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartialDefeasanceEvent>(json);
```


- [NewInstrument](NewInstrument.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

