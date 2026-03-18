# Finbourne.Sdk.Lusid.Model.InterestRateSwap

LUSID representation of an Interest Rate Swap, including:      * Vanilla (single currency fixed-float non-amortising)    * CrossCurrency (>1 currency is used by the swap legs)    * Basis (single currency, floating-floating legs of different tenors)    * Amortising (the swap has 1+ leg with amortised notional)                This instrument has multiple legs, to see how legs are used in LUSID see [knowledge base article KA-02252](https://support.lusid.com/knowledgebase/article/KA-02252).                | Leg Index | Leg Identifier | Description |  | - -- -- -- -- | - -- -- -- -- -- -- - | - -- -- -- -- -- |  | 1 | Pay/Receive | Cash flows representing the pay/receive leg. |  | 2 | Receive/Pay | Cash flows representing the receive/pay leg. |  | 3 | AdditionalPayments | Cash flows relating to any additional payments (optional). |
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **IsNonDeliverable** | **bool** | Optional | Is the contract an IRS of \&quot;Non-Deliverable\&quot; type, meaning a single payment in the settlement currency based on the difference between  the fixed and floating rates.  Defaults to false if not set. |
| **Legs** | [List&lt;InstrumentLeg&gt;](InstrumentLeg.md) | Required | The set of instrument legs that define the swap instrument, these should be FloatingLeg or FixedLeg. |
| **SettlementCcy** | **string** | Optional | Settlement currency if IRS is non-deliverable. |
| **AdditionalPayments** | [List&lt;AdditionalPayment&gt;](AdditionalPayment.md) | Optional | Optional additional payments at a given date e.g. to level off an uneven fixed-floating swap.  The dates must be distinct and either all payments are Pay or all payments are Receive. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.InterestRateSwap` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InterestRateSwap(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    isNonDeliverable: true,  // optional — Is the contract an IRS of \&quot;Non-Deliverable\&quot; type, meaning a single payment in the settlement currency based on the difference between  the fixed and floating rates.  Defaults to false if not set.
    legs: new List<InstrumentLeg>(),  // required — The set of instrument legs that define the swap instrument, these should be FloatingLeg or FixedLeg.
    settlementCcy: "...",  // optional — Settlement currency if IRS is non-deliverable.
    additionalPayments: new List<AdditionalPayment>(),  // optional — Optional additional payments at a given date e.g. to level off an uneven fixed-floating swap.  The dates must be distinct and either all payments are Pay or all payments are Receive.
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
var instance = JsonConvert.DeserializeObject<InterestRateSwap>(json);
```


- [InstrumentLeg](InstrumentLeg.md) — used in `Legs`
- [AdditionalPayment](AdditionalPayment.md) — used in `AdditionalPayments`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

