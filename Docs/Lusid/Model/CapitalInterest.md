# Finbourne.Sdk.Lusid.Model.CapitalInterest

LUSID representation of a CapitalInterest.  A CapitalInterest represents an investor's interest in a single commitment line to a  private-markets fund: one instrument per (fund, investor, commitment line). Units act as  a liveness flag (1 while the line is open, 0 once closed) and the economics are carried  by cost, fair value and the running capital balances rather than by quantity.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **QuantityBasis** | **string** | Required | How the quantity of the holding is interpreted. Under the &#39;Anchored&#39; basis, units act as a  liveness flag: 1 while the commitment line is open and 0 once it is closed. Only &#39;Anchored&#39;  is currently supported.                Supported string (enumeration) values are: [Anchored, Unitless]. Available values: Anchored, Unitless. |
| **CommitmentCurrency** | **string** | Required | The currency the commitment is denominated in. May differ from both the fund currency  and the portfolio base currency. |
| **FundEntityId** | **string** | Required | The identifier of the fund entity the commitment is made to. |
| **InvestorEntityId** | **string** | Required | The identifier of the investor entity holding the commitment. |
| **CommitmentLineId** | **string** | Required | The identifier of the commitment line, unique for a given fund and investor. |
| **OriginalCommitment** | **decimal** | Required | The committed amount at inception, in the commitment currency. May be zero for evergreen  funds. This is the original value only; subsequent amendments are carried by the running  capital balances, not by the instrument. |
| **CommitmentDate** | **DateTimeOffset** | Required | The date the commitment closed. |
| **Vintage** | **int?** | Optional | The vintage year of the commitment. Defaults to the year of the commitment date. |
| **CapitalInterestAssetClass** | **string** | Optional | The private-markets asset class of the fund the commitment is made to,  for example private equity, venture capital or infrastructure.                Supported string (enumeration) values are: [PrivateEquity, VentureCapital, PrivateCredit, RealAssets, Infrastructure, FundOfFunds, Secondary, CoInvestment, DirectEquity, ShareholderLoan, Other]. Available values: PrivateEquity, VentureCapital, PrivateCredit, RealAssets, Infrastructure, FundOfFunds, Secondary, CoInvestment, DirectEquity, ShareholderLoan, Other. |
| **ReliefPolicy** | **string** | Optional | How distributions from the commitment line are relieved against the cost of the holding.  Defaults to &#39;InstructedCharacter&#39;.                Supported string (enumeration) values are: [InstructedCharacter, CostRecovery, ProportionalToFairValue, ProportionalToPercentageInterest, NoRelief]. Available values: InstructedCharacter, CostRecovery, ProportionalToFairValue, ProportionalToPercentageInterest, NoRelief. |
| **ReliefRevisionMode** | **string** | Optional | How revisions to previously applied distribution relief are handled.  Defaults to &#39;ProspectiveTrueUp&#39;.                Supported string (enumeration) values are: [ProspectiveTrueUp, Restate, Final]. Available values: ProspectiveTrueUp, Restate, Final. |
| **FairValueSourcePrecedence** | **List&lt;string&gt;** | Optional | The order of precedence of the sources a fair value for the interest can be taken from.  Defaults to the reported NAV rolled forward for subsequent capital activity, then cost.                Supported string (enumeration) values for each entry are: [ReportedNav, RollForward, Independent, Cost]. |
| **TerminationDate** | **DateTimeOffset?** | Optional | The expected end of the fund&#39;s life, if known. This is expected rather than contractual  and does not act as a maturity date for the instrument. |
| **InstrumentType** | **string** | Required | Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest. Default: `InstrumentTypeEnum.CapitalInterest` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CapitalInterest(
    quantityBasis: "...",  // required — How the quantity of the holding is interpreted. Under the &#39;Anchored&#39; basis, units act as a  liveness flag: 1 while the commitment line is open and 0 once it is closed. Only &#39;Anchored&#39;  is currently supported.                Supported string (enumeration) values are: [Anchored, Unitless]. Available values: Anchored, Unitless.
    commitmentCurrency: "...",  // required — The currency the commitment is denominated in. May differ from both the fund currency  and the portfolio base currency.
    fundEntityId: "...",  // required — The identifier of the fund entity the commitment is made to.
    investorEntityId: "...",  // required — The identifier of the investor entity holding the commitment.
    commitmentLineId: "...",  // required — The identifier of the commitment line, unique for a given fund and investor.
    originalCommitment: 0.0d,  // required — The committed amount at inception, in the commitment currency. May be zero for evergreen  funds. This is the original value only; subsequent amendments are carried by the running  capital balances, not by the instrument.
    commitmentDate: DateTimeOffset.Now,  // required — The date the commitment closed.
    vintage: 0,  // optional — The vintage year of the commitment. Defaults to the year of the commitment date.
    capitalInterestAssetClass: "...",  // optional — The private-markets asset class of the fund the commitment is made to,  for example private equity, venture capital or infrastructure.                Supported string (enumeration) values are: [PrivateEquity, VentureCapital, PrivateCredit, RealAssets, Infrastructure, FundOfFunds, Secondary, CoInvestment, DirectEquity, ShareholderLoan, Other]. Available values: PrivateEquity, VentureCapital, PrivateCredit, RealAssets, Infrastructure, FundOfFunds, Secondary, CoInvestment, DirectEquity, ShareholderLoan, Other.
    reliefPolicy: "...",  // optional — How distributions from the commitment line are relieved against the cost of the holding.  Defaults to &#39;InstructedCharacter&#39;.                Supported string (enumeration) values are: [InstructedCharacter, CostRecovery, ProportionalToFairValue, ProportionalToPercentageInterest, NoRelief]. Available values: InstructedCharacter, CostRecovery, ProportionalToFairValue, ProportionalToPercentageInterest, NoRelief.
    reliefRevisionMode: "...",  // optional — How revisions to previously applied distribution relief are handled.  Defaults to &#39;ProspectiveTrueUp&#39;.                Supported string (enumeration) values are: [ProspectiveTrueUp, Restate, Final]. Available values: ProspectiveTrueUp, Restate, Final.
    fairValueSourcePrecedence: ,  // optional — The order of precedence of the sources a fair value for the interest can be taken from.  Defaults to the reported NAV rolled forward for subsequent capital activity, then cost.                Supported string (enumeration) values for each entry are: [ReportedNav, RollForward, Independent, Cost].
    terminationDate: DateTimeOffset.Now,  // optional — The expected end of the fund&#39;s life, if known. This is expected rather than contractual  and does not act as a maturity date for the instrument.
    instrumentType: "..."  // required — Available values: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo, ToBeAnnounced, VolatilitySwap, ToBeAnnouncedOption, CommodityForward, BondOption, CdsOption, CommodityCalendarSwap, BondForward, PreferredShare, CapitalInterest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CapitalInterest>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

