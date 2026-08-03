# Finbourne.Sdk.Lusid.Model.ToBeAnnounced

LUSID representation of a TBA (To Be Announced) forward contract for generic agency mortgage-backed securities.  Valued as Quantity x Price via EOD quote lookup; carries no coupon cashflows, accrual or factor.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The trade inception date of the TBA. |
| **MaturityDate** | **DateTimeOffset** | Required | The contractual settlement date of the TBA (e.g. the agency&#39;s announced settlement date for the month). |
| **DomCcy** | **string** | Required | The domestic currency of the TBA. |
| **Agency** | **string** | Optional | The issuing agency of the underlying generic collateral, e.g. \&quot;FNMA\&quot;, \&quot;FHLMC\&quot;, \&quot;GNMA\&quot;.  Note this property does not impact valuation. From a LUSID analytics perspective, it is purely informational. |
| **Coupon** | **decimal?** | Optional | The stated coupon rate of the underlying generic collateral, e.g. 3.0, 4.5.  Note this property does not impact valuation - there are no coupon cash flows on the TBA itself.  From a LUSID analytics perspective, it is purely informational. |
| **Tenor** | **string** | Optional | The tenor of the underlying generic collateral, e.g. \&quot;30Y\&quot;, \&quot;15Y\&quot;.  Note this property does not impact valuation. From a LUSID analytics perspective, it is purely informational. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption. Default: `InstrumentTypeEnum.ToBeAnnounced` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ToBeAnnounced(
    startDate: DateTimeOffset.Now,  // required — The trade inception date of the TBA.
    maturityDate: DateTimeOffset.Now,  // required — The contractual settlement date of the TBA (e.g. the agency&#39;s announced settlement date for the month).
    domCcy: "...",  // required — The domestic currency of the TBA.
    agency: "...",  // optional — The issuing agency of the underlying generic collateral, e.g. \&quot;FNMA\&quot;, \&quot;FHLMC\&quot;, \&quot;GNMA\&quot;.  Note this property does not impact valuation. From a LUSID analytics perspective, it is purely informational.
    coupon: 0.0d,  // optional — The stated coupon rate of the underlying generic collateral, e.g. 3.0, 4.5.  Note this property does not impact valuation - there are no coupon cash flows on the TBA itself.  From a LUSID analytics perspective, it is purely informational.
    tenor: "...",  // optional — The tenor of the underlying generic collateral, e.g. \&quot;30Y\&quot;, \&quot;15Y\&quot;.  Note this property does not impact valuation. From a LUSID analytics perspective, it is purely informational.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    tradingConventions: new TradingConventions(...),  // optional
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ToBeAnnounced>(json);
```


- [TimeZoneConventions](TimeZoneConventions.md)
- [TradingConventions](TradingConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

