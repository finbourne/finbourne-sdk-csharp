# Finbourne.Sdk.Lusid.Model.ContractForDifference

LUSID representation of a Contract for Difference.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the CFD. |
| **MaturityDate** | **DateTimeOffset** | Optional | The maturity date for the CFD. If CFDType is Futures, this should be set to be the maturity date of the underlying  future. If CFDType is Cash, this should not be set. |
| **Code** | **string** | Optional | The code of the underlying. |
| **ContractSize** | **decimal** | Optional | The size of the CFD contract, this should represent the total number of stocks that the CFD represents.   This field is optional, if not set it will default to 1. |
| **PayCcy** | **string** | Required | The currency that this CFD pays out, this can be different to the UnderlyingCcy. |
| **ReferenceRate** | **decimal** | Optional | The reference rate of the CFD, this can be set to 0 but not negative values.  This field is optional, if not set it will default to 0. |
| **Type** | **string** | Required | The type of CFD.    Supported string (enumeration) values are: [Cash, Futures]. |
| **UnderlyingCcy** | **string** | Optional | The currency of the underlying |
| **UnderlyingIdentifier** | **string** | Optional | External market codes and identifiers for the CFD, e.g. RIC.    Supported string (enumeration) values are: [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode]. |
| **LotSize** | **int** | Optional | CFD LotSize, the minimum number of shares that can be bought or sold at once.  Optional, if set must be non-negative, if not set defaults to 1. |
| **Underlying** | [LusidInstrument](LusidInstrument.md) | Optional | *No description available.* |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.ContractForDifference` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ContractForDifference(
    startDate: DateTimeOffset.Now,  // required — The start date of the CFD.
    maturityDate: DateTimeOffset.Now,  // optional — The maturity date for the CFD. If CFDType is Futures, this should be set to be the maturity date of the underlying  future. If CFDType is Cash, this should not be set.
    code: "...",  // optional — The code of the underlying.
    contractSize: 0.0d,  // optional — The size of the CFD contract, this should represent the total number of stocks that the CFD represents.   This field is optional, if not set it will default to 1.
    payCcy: "...",  // required — The currency that this CFD pays out, this can be different to the UnderlyingCcy.
    referenceRate: 0.0d,  // optional — The reference rate of the CFD, this can be set to 0 but not negative values.  This field is optional, if not set it will default to 0.
    type: "...",  // required — The type of CFD.    Supported string (enumeration) values are: [Cash, Futures].
    underlyingCcy: "...",  // optional — The currency of the underlying
    underlyingIdentifier: "...",  // optional — External market codes and identifiers for the CFD, e.g. RIC.    Supported string (enumeration) values are: [LusidInstrumentId, Isin, Sedol, Cusip, ClientInternal, Figi, RIC, QuotePermId, REDCode, BBGId, ICECode].
    lotSize: 0,  // optional — CFD LotSize, the minimum number of shares that can be bought or sold at once.  Optional, if set must be non-negative, if not set defaults to 1.
    underlying: new LusidInstrument(...),  // optional
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
var instance = JsonConvert.DeserializeObject<ContractForDifference>(json);
```


- [LusidInstrument](LusidInstrument.md)
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

