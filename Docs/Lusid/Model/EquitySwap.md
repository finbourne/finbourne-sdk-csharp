# Finbourne.Sdk.Lusid.Model.EquitySwap

LUSID representation of an Equity Swap.                This instrument has multiple legs, to see how legs are used in LUSID see [knowledge base article KA-02252](https://support.lusid.com/knowledgebase/article/KA-02252).                | Leg Index | Leg Identifier | Description |  | - -- -- -- -- | - -- -- -- -- -- -- - | - -- -- -- -- -- |  | 1 | EquityLeg | Cash flows relating to the performance of the underlying equity. |  | 2 | FundingLeg | The funding leg of the swap. |  | 3 | EquityDividendLeg | Cash flows relating to dividend payments on the underlying equity (optional). |  | 4 | AdditionalPayments | Cash flows relating to any additional payments (optional). |
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the EquitySwap. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **Code** | **string** | Required | The code of the underlying. |
| **EquityFlowConventions** | [FlowConventions](FlowConventions.md) | Required | *No description available.* |
| **FundingLeg** | [InstrumentLeg](InstrumentLeg.md) | Required | *No description available.* |
| **IncludeDividends** | **bool** | Required | Dividend inclusion flag, if true dividends are included in the equity leg (total return). |
| **InitialPrice** | **decimal** | Required | The initial equity price of the Equity Swap. |
| **NotionalReset** | **bool** | Required | Notional reset flag, if true the notional of the funding leg is reset at the start of every  coupon to match the value of the equity leg (equity price at start of coupon times quantity). |
| **Quantity** | **decimal** | Required | The quantity or number of shares in the Equity Swap. |
| **UnderlyingIdentifier** | **string** | Required | External market codes and identifiers for the EquitySwap, e.g. RIC.    Supported string (enumeration) values are: [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode]. |
| **EquitySwapDividendPaymentTiming** | **string** | Optional | Determines how the payment of dividends is handled for the equity swap.  Defaults to paying at the next Equity coupon date.                Supported string (enumeration) values are: [PayAtNextEquityCouponDate, PayAtMaturityOfSwap, PayAtNextFundingLegCouponDate, PayAtPaymentDateOfDividendEvent]. |
| **AdditionalPayments** | [List&lt;AdditionalPayment&gt;](AdditionalPayment.md) | Optional | Optional additional payments at a given date e.g. to level off an uneven equity swap.  The dates must be distinct and either all payments are Pay or all payments are Receive. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.EquitySwap` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EquitySwap(
    startDate: DateTimeOffset.Now,  // required — The start date of the EquitySwap.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    code: "...",  // required — The code of the underlying.
    equityFlowConventions: new FlowConventions(...),  // required
    fundingLeg: new InstrumentLeg(...),  // required
    includeDividends: true,  // required — Dividend inclusion flag, if true dividends are included in the equity leg (total return).
    initialPrice: 0.0d,  // required — The initial equity price of the Equity Swap.
    notionalReset: true,  // required — Notional reset flag, if true the notional of the funding leg is reset at the start of every  coupon to match the value of the equity leg (equity price at start of coupon times quantity).
    quantity: 0.0d,  // required — The quantity or number of shares in the Equity Swap.
    underlyingIdentifier: "...",  // required — External market codes and identifiers for the EquitySwap, e.g. RIC.    Supported string (enumeration) values are: [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].
    equitySwapDividendPaymentTiming: "...",  // optional — Determines how the payment of dividends is handled for the equity swap.  Defaults to paying at the next Equity coupon date.                Supported string (enumeration) values are: [PayAtNextEquityCouponDate, PayAtMaturityOfSwap, PayAtNextFundingLegCouponDate, PayAtPaymentDateOfDividendEvent].
    additionalPayments: new List<AdditionalPayment>(),  // optional — Optional additional payments at a given date e.g. to level off an uneven equity swap.  The dates must be distinct and either all payments are Pay or all payments are Receive.
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
var instance = JsonConvert.DeserializeObject<EquitySwap>(json);
```


- [FlowConventions](FlowConventions.md)
- [InstrumentLeg](InstrumentLeg.md)
- [AdditionalPayment](AdditionalPayment.md) — used in `AdditionalPayments`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

