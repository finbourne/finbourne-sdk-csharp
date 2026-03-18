# Finbourne.Sdk.Lusid.Model.CreditDefaultSwap

LUSID representation of a Credit Default Swap (CDS).                This instrument has multiple legs, to see how legs are used in LUSID see [knowledge base article KA-02252](https://support.lusid.com/knowledgebase/article/KA-02252).                | Leg Index | Leg Identifier | Description |  | - -- -- -- -- | - -- -- -- -- -- -- - | - -- -- -- -- -- |  | 1 | ProtectionLeg | Cash flows occurring in the case of default. |  | 2 | PremiumLeg | The premium payments made by the protection buyer. |  | 3 | AdditionalPayments | Cash flows relating to any additional payments (optional). |
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Ticker** | **string** | Optional | A ticker to uniquely specify the entity against which the CDS is written. Defaults to \&quot;DefaultCDSTicker\&quot;. Default: `"DefaultCDSTicker"` |
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **FlowConventions** | [CdsFlowConventions](CdsFlowConventions.md) | Optional | *No description available.* |
| **CouponRate** | **decimal** | Required | The coupon rate paid on each payment date of the premium leg as a fraction of 100 percent, e.g. \&quot;0.05\&quot; meaning 500 basis points or 5%.  For a standard corporate CDS (North American) this must be either 100bps or 500bps. |
| **ConventionName** | [FlowConventionName](FlowConventionName.md) | Optional | *No description available.* |
| **Notional** | **decimal?** | Optional | The notional protected by the Credit Default Swap |
| **ProtectionDetailSpecification** | [CdsProtectionDetailSpecification](CdsProtectionDetailSpecification.md) | Optional | *No description available.* |
| **AdditionalPayments** | [List&lt;AdditionalPayment&gt;](AdditionalPayment.md) | Optional | Optional additional payments at a given date e.g. to level off an uneven swap.  The dates must be distinct and either all payments are Pay or all payments are Receive. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.CreditDefaultSwap` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreditDefaultSwap(
    ticker: "...",  // optional — A ticker to uniquely specify the entity against which the CDS is written. Defaults to \&quot;DefaultCDSTicker\&quot;.
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    flowConventions: new CdsFlowConventions(...),  // optional
    couponRate: 0.0d,  // required — The coupon rate paid on each payment date of the premium leg as a fraction of 100 percent, e.g. \&quot;0.05\&quot; meaning 500 basis points or 5%.  For a standard corporate CDS (North American) this must be either 100bps or 500bps.
    conventionName: new FlowConventionName(...),  // optional
    notional: 0.0d,  // optional — The notional protected by the Credit Default Swap
    protectionDetailSpecification: new CdsProtectionDetailSpecification(...),  // optional
    additionalPayments: new List<AdditionalPayment>(),  // optional — Optional additional payments at a given date e.g. to level off an uneven swap.  The dates must be distinct and either all payments are Pay or all payments are Receive.
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
var instance = JsonConvert.DeserializeObject<CreditDefaultSwap>(json);
```


- [CdsFlowConventions](CdsFlowConventions.md)
- [FlowConventionName](FlowConventionName.md)
- [CdsProtectionDetailSpecification](CdsProtectionDetailSpecification.md)
- [AdditionalPayment](AdditionalPayment.md) — used in `AdditionalPayments`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

