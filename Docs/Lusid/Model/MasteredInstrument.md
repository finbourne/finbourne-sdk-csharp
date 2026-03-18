# Finbourne.Sdk.Lusid.Model.MasteredInstrument

LUSID representation of a reference to another instrument that has already been upserted (Mastered)
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Identifiers** | **Dictionary&lt;string, string&gt;** | Required | Dictionary of identifiers of the mastered instrument |
| **MasteredDomCcy** | **string** | Optional | DomCcy of the Instrument that Mastered Instrument points to - read only field *(read-only)* |
| **MasteredInstrumentType** | **string** | Optional | Type of the Instrument that Mastered Instrument points to - read only field *(read-only)* |
| **MasteredLusidInstrumentId** | **string** | Optional | Luid of the Instrument that Mastered Instrument points to - read only field *(read-only)* |
| **MasteredName** | **string** | Optional | Name of the Instrument that Mastered Instrument points to - read only field *(read-only)* |
| **MasteredScope** | **string** | Optional | Scope of the Instrument that Mastered Instrument points to - read only field *(read-only)* |
| **MasteredAssetClass** | **string** | Optional | Asset class of the underlying mastered instrument - read only field    Supported string (enumeration) values are: [InterestRates, FX, Inflation, Equities, Credit, Commodities, Money].  Defaults to \&quot;Unknown\&quot; if not set. *(read-only)* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.MasteredInstrument` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MasteredInstrument(
    identifiers: ,  // required — Dictionary of identifiers of the mastered instrument
    masteredDomCcy: "...",  // optional — DomCcy of the Instrument that Mastered Instrument points to - read only field
    masteredInstrumentType: "...",  // optional — Type of the Instrument that Mastered Instrument points to - read only field
    masteredLusidInstrumentId: "...",  // optional — Luid of the Instrument that Mastered Instrument points to - read only field
    masteredName: "...",  // optional — Name of the Instrument that Mastered Instrument points to - read only field
    masteredScope: "...",  // optional — Scope of the Instrument that Mastered Instrument points to - read only field
    masteredAssetClass: "...",  // optional — Asset class of the underlying mastered instrument - read only field    Supported string (enumeration) values are: [InterestRates, FX, Inflation, Equities, Credit, Commodities, Money].  Defaults to \&quot;Unknown\&quot; if not set.
    instrumentType: "..."  // required — The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MasteredInstrument>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

