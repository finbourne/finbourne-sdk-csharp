# Finbourne.Sdk.Lusid.Model.ConversionEvent

Conversion Event (CONV) - Conversion of securities (generally convertible bonds or preferred shares) into  another form of securities (usually common shares) at a pre-stated price/ratio.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecordDate** | **DateTimeOffset** | Optional | Required.  Date at which positions are struck at the end of the day to  note which parties will receive the relevant amount of  entitlement, due to be distributed on the PaymentDate. |
| **PaymentDate** | **DateTimeOffset** | Optional | Required. Date on which the movement is due to take place (cash and/or securities). |
| **NewInstrument** | [NewInstrument](NewInstrument.md) | Required | *No description available.* |
| **ResponseDeadlineDate** | **DateTimeOffset?** | Optional | Date/time that the account servicer has set as the deadline to respond,  with instructions, to an outstanding event. Not required. |
| **MarketDeadlineDate** | **DateTimeOffset?** | Optional | Date/time which the issuer or issuer&#39;s agent has set as the deadline to respond,  with an instruction, to an outstanding offer or privilege. Not required. |
| **PeriodOfAction** | [EventDateRange](EventDateRange.md) | Optional | *No description available.* |
| **FractionalUnitsCashPrice** | **decimal?** | Optional | The cash price paid in lieu of fractionalUnits. Not required.  If provided, must have FractionalUnitsCashCurrency too. |
| **FractionalUnitsCashCurrency** | **string** | Optional | Optional. Used in calculating cash-in-lieu of fractional shares. Not required.  If provided, must have FractionalUnitsCashPrice too. |
| **SecurityOfferElections** | [List&lt;SecurityOfferElection&gt;](SecurityOfferElection.md) | Optional | List of possible security offers for this conversion event. There must be at most one election of this type.    If the ParticipationType is Mandatory:     This list must have exactly one election that is chosen and default.  CashAndSecurityOfferElections and CashOfferElections &lt;b&gt; must be null or empty&lt;/b&gt;.     If the ParticipationType is Voluntary:     This list can be empty,  so long as CashAndSecurityOfferElections or CashOfferElections  has at least one election. None of these elections have to be chosen or default. |
| **CashAndSecurityOfferElections** | [List&lt;CashAndSecurityOfferElection&gt;](CashAndSecurityOfferElection.md) | Optional | List of possible cash and security offers for this conversion event. There must be at most one election of this type.    If the ParticipationType is Mandatory:    This list &lt;b&gt; must be null or empty&lt;/b&gt;.    If the ParticipationType is Voluntary:    This list can be empty,  so long as SecurityOfferElections or CashOfferElections  has at least one election. None of these elections have to be chosen or default. |
| **CashOfferElections** | [List&lt;CashOfferElection&gt;](CashOfferElection.md) | Optional | List of possible cash offers for this conversion event. There must be at most one election of this type.    If the ParticipationType is Mandatory:    This list &lt;b&gt; must be null or empty&lt;/b&gt;.    If the ParticipationType is Voluntary:    This list can be empty,  so long as SecurityOfferElections or CashAndSecurityOfferElections  has at least one election. None of these elections have to be chosen or default. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.ConversionEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConversionEvent(
    recordDate: DateTimeOffset.Now,  // optional — Required.  Date at which positions are struck at the end of the day to  note which parties will receive the relevant amount of  entitlement, due to be distributed on the PaymentDate.
    paymentDate: DateTimeOffset.Now,  // optional — Required. Date on which the movement is due to take place (cash and/or securities).
    newInstrument: new NewInstrument(...),  // required
    responseDeadlineDate: DateTimeOffset.Now,  // optional — Date/time that the account servicer has set as the deadline to respond,  with instructions, to an outstanding event. Not required.
    marketDeadlineDate: DateTimeOffset.Now,  // optional — Date/time which the issuer or issuer&#39;s agent has set as the deadline to respond,  with an instruction, to an outstanding offer or privilege. Not required.
    periodOfAction: new EventDateRange(...),  // optional
    fractionalUnitsCashPrice: 0.0d,  // optional — The cash price paid in lieu of fractionalUnits. Not required.  If provided, must have FractionalUnitsCashCurrency too.
    fractionalUnitsCashCurrency: "...",  // optional — Optional. Used in calculating cash-in-lieu of fractional shares. Not required.  If provided, must have FractionalUnitsCashPrice too.
    securityOfferElections: new List<SecurityOfferElection>(),  // optional — List of possible security offers for this conversion event. There must be at most one election of this type.    If the ParticipationType is Mandatory:     This list must have exactly one election that is chosen and default.  CashAndSecurityOfferElections and CashOfferElections &lt;b&gt; must be null or empty&lt;/b&gt;.     If the ParticipationType is Voluntary:     This list can be empty,  so long as CashAndSecurityOfferElections or CashOfferElections  has at least one election. None of these elections have to be chosen or default.
    cashAndSecurityOfferElections: new List<CashAndSecurityOfferElection>(),  // optional — List of possible cash and security offers for this conversion event. There must be at most one election of this type.    If the ParticipationType is Mandatory:    This list &lt;b&gt; must be null or empty&lt;/b&gt;.    If the ParticipationType is Voluntary:    This list can be empty,  so long as SecurityOfferElections or CashOfferElections  has at least one election. None of these elections have to be chosen or default.
    cashOfferElections: new List<CashOfferElection>(),  // optional — List of possible cash offers for this conversion event. There must be at most one election of this type.    If the ParticipationType is Mandatory:    This list &lt;b&gt; must be null or empty&lt;/b&gt;.    If the ParticipationType is Voluntary:    This list can be empty,  so long as SecurityOfferElections or CashAndSecurityOfferElections  has at least one election. None of these elections have to be chosen or default.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConversionEvent>(json);
```


- [NewInstrument](NewInstrument.md)
- [EventDateRange](EventDateRange.md)
- [SecurityOfferElection](SecurityOfferElection.md) — used in `SecurityOfferElections`
- [CashAndSecurityOfferElection](CashAndSecurityOfferElection.md) — used in `CashAndSecurityOfferElections`
- [CashOfferElection](CashOfferElection.md) — used in `CashOfferElections`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

