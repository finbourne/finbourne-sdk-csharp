# Finbourne.Sdk.Lusid.Model.InflationSwap

LUSID representation of an Inflation Swap.  The implementation supports the following swap types:  * Zero Coupon inflation swap, with a single payment at maturity.  * LPI Swap (capped and floored)  * Year on Year inflation swap                This instrument has multiple legs, to see how legs are used in LUSID see [knowledge base article KA-02252](https://support.lusid.com/knowledgebase/article/KA-02252).                | Leg Index | Leg Identifier | Description |  | - -- -- -- -- | - -- -- -- -- -- -- - | - -- -- -- -- -- |  | 1 | InflationLeg | Cash flows with a rate relating to an underlying inflation index. |  | 2 | FixedLeg | Cash flows with a fixed rate. |  | 3 | AdditionalPayments | Cash flows relating to any additional payments (optional). |
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **InflationLeg** | [InflationLeg](InflationLeg.md) | Required | *No description available.* |
| **FixedLeg** | [FixedLeg](FixedLeg.md) | Required | *No description available.* |
| **AdditionalPayments** | [List&lt;AdditionalPayment&gt;](AdditionalPayment.md) | Optional | Optional additional payments at a given date e.g. to level off an uneven inflation swap.  The dates must be distinct and either all payments are Pay or all payments are Receive. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.InflationSwap` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationSwap(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    inflationLeg: new InflationLeg(...),  // required
    fixedLeg: new FixedLeg(...),  // required
    additionalPayments: new List<AdditionalPayment>(),  // optional — Optional additional payments at a given date e.g. to level off an uneven inflation swap.  The dates must be distinct and either all payments are Pay or all payments are Receive.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    instrumentType: "..."  // required — The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationSwap>(json);
```


- [InflationLeg](InflationLeg.md)
- [FixedLeg](FixedLeg.md)
- [AdditionalPayment](AdditionalPayment.md) — used in `AdditionalPayments`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

