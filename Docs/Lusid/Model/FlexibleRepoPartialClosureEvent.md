# Finbourne.Sdk.Lusid.Model.FlexibleRepoPartialClosureEvent

Event representing the partial closure of a repurchase   agreement. Each event reduces the outstanding notional   and generates a corresponding receive-leg cashflow. The   final maturity cashflow is adjusted accordingly.  If multiple events are created, their effects compound.   Once the total repaid amount reaches the original purchase   price, no further receive-leg cashflows are generated. Any   event exceeding the remaining notional is marked with a   diagnostic to indicate it is invalid due to excessive repayment.  For example, for a repo with a 5% rate, 1% haircut and   collateral value of 100 (purchase price = 99), a partial   closure of cash amount 10 followed by one of 100 results in   only the first event producing a cashflow. The second,   exceeding the remaining balance, is ignored and flagged   with a diagnostic. The remaining balance is settled at   maturity of the repurchase agreement.  Specific to a FlexibleRepo instrument.
> **Inherits from:** [InstrumentEvent](InstrumentEvent.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntitlementDate** | **DateTimeOffset** | Optional | Required property.  The date on which the counterparties become entitled   to exchange cash as part of a partial closure of the   repurchase agreement. The date must be before or on   the settlement date, and on or before the maturity   date of the repo.  This is a required field, unless otherwise supplied via \&quot;EventDateStamps\&quot; in  the instrument event upsert request. |
| **SettlementDate** | **DateTimeOffset** | Optional | Required property.  The date on which the exchange of cash is settled.   The date must be on or after the entitlement date,  and on or before the maturity date of the repo.  This is a required field, unless otherwise supplied via \&quot;EventDateStamps\&quot; in  the instrument event upsert request. |
| **Amount** | **decimal** | Required | The amount of cash to be exchanged as part of a partial closure of the repurchase agreement.  Either the absolute cash amount or a percentage of the remaining amount,  depending on the AmountType. |
| **AmountType** | **string** | Required | AmountType of the cash amount to be exchanged as part of a partial closure of the repurchase agreement.  Either percentage or absolute cash amount.    Supported string (enumeration) values are: [Percentage, Units]. |
| **PartialClosureConstituents** | [List&lt;PartialClosureConstituent&gt;](PartialClosureConstituent.md) | Required | List of the collateral instruments involved in this partial closure, along with how they are affected. |
| **InstrumentEventType** | **string** | Required | The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent Default: `InstrumentEventTypeEnum.FlexibleRepoPartialClosureEvent` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FlexibleRepoPartialClosureEvent(
    entitlementDate: DateTimeOffset.Now,  // optional — Required property.  The date on which the counterparties become entitled   to exchange cash as part of a partial closure of the   repurchase agreement. The date must be before or on   the settlement date, and on or before the maturity   date of the repo.  This is a required field, unless otherwise supplied via \&quot;EventDateStamps\&quot; in  the instrument event upsert request.
    settlementDate: DateTimeOffset.Now,  // optional — Required property.  The date on which the exchange of cash is settled.   The date must be on or after the entitlement date,  and on or before the maturity date of the repo.  This is a required field, unless otherwise supplied via \&quot;EventDateStamps\&quot; in  the instrument event upsert request.
    amount: 0.0d,  // required — The amount of cash to be exchanged as part of a partial closure of the repurchase agreement.  Either the absolute cash amount or a percentage of the remaining amount,  depending on the AmountType.
    amountType: "...",  // required — AmountType of the cash amount to be exchanged as part of a partial closure of the repurchase agreement.  Either percentage or absolute cash amount.    Supported string (enumeration) values are: [Percentage, Units].
    partialClosureConstituents: new List<PartialClosureConstituent>(),  // required — List of the collateral instruments involved in this partial closure, along with how they are affected.
    instrumentEventType: "..."  // required — The Type of Event. The available values are: TransitionEvent, InformationalEvent, OpenEvent, CloseEvent, StockSplitEvent, BondDefaultEvent, CashDividendEvent, AmortisationEvent, CashFlowEvent, ExerciseEvent, ResetEvent, TriggerEvent, RawVendorEvent, InformationalErrorEvent, BondCouponEvent, DividendReinvestmentEvent, AccumulationEvent, BondPrincipalEvent, DividendOptionEvent, MaturityEvent, FxForwardSettlementEvent, ExpiryEvent, ScripDividendEvent, StockDividendEvent, ReverseStockSplitEvent, CapitalDistributionEvent, SpinOffEvent, MergerEvent, FutureExpiryEvent, SwapCashFlowEvent, SwapPrincipalEvent, CreditPremiumCashFlowEvent, CdsCreditEvent, CdxCreditEvent, MbsCouponEvent, MbsPrincipalEvent, BonusIssueEvent, MbsPrincipalWriteOffEvent, MbsInterestDeferralEvent, MbsInterestShortfallEvent, TenderEvent, CallOnIntermediateSecuritiesEvent, IntermediateSecuritiesDistributionEvent, OptionExercisePhysicalEvent, OptionExerciseCashEvent, ProtectionPayoutCashFlowEvent, TermDepositInterestEvent, TermDepositPrincipalEvent, EarlyRedemptionEvent, FutureMarkToMarketEvent, AdjustGlobalCommitmentEvent, ContractInitialisationEvent, DrawdownEvent, LoanInterestRepaymentEvent, UpdateDepositAmountEvent, LoanPrincipalRepaymentEvent, DepositInterestPaymentEvent, DepositCloseEvent, LoanFacilityContractRolloverEvent, RepurchaseOfferEvent, RepoPartialClosureEvent, RepoCashFlowEvent, FlexibleRepoInterestPaymentEvent, FlexibleRepoCashFlowEvent, FlexibleRepoCollateralEvent, ConversionEvent, FlexibleRepoPartialClosureEvent, FlexibleRepoFullClosureEvent, CapletFloorletCashFlowEvent, EarlyCloseOutEvent, DepositRollEvent
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FlexibleRepoPartialClosureEvent>(json);
```


- [PartialClosureConstituent](PartialClosureConstituent.md) — used in `PartialClosureConstituents`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

