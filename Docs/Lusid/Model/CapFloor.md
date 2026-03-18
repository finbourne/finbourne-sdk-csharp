# Finbourne.Sdk.Lusid.Model.CapFloor

LUSID representation of Cap, Floor, or Collar.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CapFloorType** | **string** | Required | Determine if it&#39;s CAP, FLOOR, or COLLAR.    Supported string (enumeration) values are: [Cap, Floor, Collar]. |
| **CapStrike** | **decimal?** | Optional | Strike rate of the Cap. |
| **FloorStrike** | **decimal?** | Optional | Strike rate of the Floor. |
| **IncludeFirstCaplet** | **bool** | Required | Include first caplet flag. |
| **UnderlyingFloatingLeg** | [FloatingLeg](FloatingLeg.md) | Required | *No description available.* |
| **AdditionalPayments** | [List&lt;AdditionalPayment&gt;](AdditionalPayment.md) | Optional | Optional additional payments at a given date e.g. to level off an uneven equity swap.  The dates must be distinct and either all payments are Pay or all payments are Receive. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.CapFloor` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CapFloor(
    capFloorType: "...",  // required — Determine if it&#39;s CAP, FLOOR, or COLLAR.    Supported string (enumeration) values are: [Cap, Floor, Collar].
    capStrike: 0.0d,  // optional — Strike rate of the Cap.
    floorStrike: 0.0d,  // optional — Strike rate of the Floor.
    includeFirstCaplet: true,  // required — Include first caplet flag.
    underlyingFloatingLeg: new FloatingLeg(...),  // required
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
var instance = JsonConvert.DeserializeObject<CapFloor>(json);
```


- [FloatingLeg](FloatingLeg.md)
- [AdditionalPayment](AdditionalPayment.md) — used in `AdditionalPayments`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

