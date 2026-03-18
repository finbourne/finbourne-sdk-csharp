# Finbourne.Sdk.Lusid.Model.FlexibleRepo

Lusid representation of a repurchase agreement, where one party sells some collateral and agrees to re-buy it at a later date for some given price.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset?** | Optional | The maturity date of the instrument. This is the date at which the repurchase will occur for a TermRepo.  Optional for OpenRepo, but if not provided, defaults to the StartDate plus a long period (e.g. 2099-12-31). |
| **BuyerOrSeller** | **string** | Required | Is the user the Buyer or the Seller of this repo?  Every repo agreement has two sides, a buyer and a seller.  The Buyer pays the PurchasePrice to the Seller in exchange for legal ownership of the collateral.  At Maturity, the Buyer then receives the RepurchasePrice in exchange for returning legal ownership of the collateral.  Controls the direction of purchase and repurchase cashflows, as well as the recipient of cashflows from the collateral.    Supported string (enumeration) values are: [Buyer, Seller]. |
| **RepoCcy** | **string** | Required | Currency of the purchase and repurchase prices. May differ from the currencies on any collateral. |
| **RepoType** | **string** | Required | The type of the repurchase agreement, Open or Term.  If Term, the repurchase automatically takes place at Maturity.  If Open, the agreement is rolled by the given tenor, and an interest cashflow is paid out with each roll,  unless manually triggered by a FlexibleRepoFullClosureEvent.    Supported string (enumeration) values are: [OpenRepo, TermRepo]. |
| **AccrualBasis** | **string** | Optional | For calculation of interest, the accrual day count to be used.  Required if no RepoRateSchedules are provided.  If both RepoRateSchedules and AccrualBasis are provided,  then AccrualBasis will take precedence.    Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM]. |
| **Collateral** | [Collateral](Collateral.md) | Optional | *No description available.* |
| **Haircut** | **decimal?** | Optional | Haircut on the value of the collateral, used to calculate PurchasePrice if not provided directly.  Haircut or Margin should be specified if PurchasePrice is not specified. |
| **Margin** | **decimal?** | Optional | Initial margin on the value of the collateral, used to calculate PurchasePrice if not provided directly.  Haircut or Margin should be specified if PurchasePrice is not specified. |
| **OpenRepoRollingPeriod** | **string** | Optional | Required if the RepoType is Open.  The tenor representing the mandatory roll period if the FlexibleRepo is not manually matured.  If a user matures the FlexibleRepo via an instrument event, then the repurchase will delay until the end of this rolling period.  Generally this is set to 1D (one day), i.e. the repurchase will occur on the same day as the instrument event,  though any valid tenor is accepted with TenorUnit set to Day, Week, Month, or Year.  Note that TenorUnit T is not accepted here. |
| **PurchasePrice** | **decimal?** | Optional | The initial purchase price of the collateral.  If provided directly in this field, then Collateral.CollateralValue,  Haircut, and Margin should not be provided. |
| **RepoRateSchedules** | [List&lt;Schedule&gt;](Schedule.md) | Optional | Schedules used to calculate the repurchase price and any interest payments on the FlexibleRepo.  Only one schedule may be provided, and must be of type FixedSchedule or FloatSchedule.  If RepoType is OpenRepo, a FixedSchedule or FloatSchedule must be provided to calculate the expected Repo Rate,  and RepurchasePrice must be omitted.  If RepoType is TermRepo, only one of RepurchasePrice and RepoRateSchedules should be provided.  If a RepoRateSchedule is provided on a TermRepo, the PaymentFrequency in the FlowConventions should be 1T.  StubType must be set to None, and no ExDividend configuration should be provided. |
| **RepurchasePrice** | **decimal?** | Optional | The repurchase price of the repo, if known.  Only one of RepurchasePrice and RepoRateSchedules should be provided.  In the case of an OpenRepo, RepurchasePrice should not be provided,  and RepoRateSchedules should be provided instead in order to calculate the RepoRate. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **TradingConventions** | [TradingConventions](TradingConventions.md) | Optional | *No description available.* |
| **IsCollateralTransferActivated** | **bool** | Optional | Indicates whether the FlexibleRepoCollateralTransfer event is activated.  Determines the behavior of manufactured coupons and related boolean parameters.  Defaults to false.  When true:  - Generates the FlexibleRepoCollateralTransfer event  - Processes collateral transfer transactions into holding changes  - Generates manufactured payments when due to be paid                When false:  - Does not generate the event  - Generates manufactured payments when due to be received |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.FlexibleRepo` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FlexibleRepo(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // optional — The maturity date of the instrument. This is the date at which the repurchase will occur for a TermRepo.  Optional for OpenRepo, but if not provided, defaults to the StartDate plus a long period (e.g. 2099-12-31).
    buyerOrSeller: "...",  // required — Is the user the Buyer or the Seller of this repo?  Every repo agreement has two sides, a buyer and a seller.  The Buyer pays the PurchasePrice to the Seller in exchange for legal ownership of the collateral.  At Maturity, the Buyer then receives the RepurchasePrice in exchange for returning legal ownership of the collateral.  Controls the direction of purchase and repurchase cashflows, as well as the recipient of cashflows from the collateral.    Supported string (enumeration) values are: [Buyer, Seller].
    repoCcy: "...",  // required — Currency of the purchase and repurchase prices. May differ from the currencies on any collateral.
    repoType: "...",  // required — The type of the repurchase agreement, Open or Term.  If Term, the repurchase automatically takes place at Maturity.  If Open, the agreement is rolled by the given tenor, and an interest cashflow is paid out with each roll,  unless manually triggered by a FlexibleRepoFullClosureEvent.    Supported string (enumeration) values are: [OpenRepo, TermRepo].
    accrualBasis: "...",  // optional — For calculation of interest, the accrual day count to be used.  Required if no RepoRateSchedules are provided.  If both RepoRateSchedules and AccrualBasis are provided,  then AccrualBasis will take precedence.    Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM].
    collateral: new Collateral(...),  // optional
    haircut: 0.0d,  // optional — Haircut on the value of the collateral, used to calculate PurchasePrice if not provided directly.  Haircut or Margin should be specified if PurchasePrice is not specified.
    margin: 0.0d,  // optional — Initial margin on the value of the collateral, used to calculate PurchasePrice if not provided directly.  Haircut or Margin should be specified if PurchasePrice is not specified.
    openRepoRollingPeriod: "...",  // optional — Required if the RepoType is Open.  The tenor representing the mandatory roll period if the FlexibleRepo is not manually matured.  If a user matures the FlexibleRepo via an instrument event, then the repurchase will delay until the end of this rolling period.  Generally this is set to 1D (one day), i.e. the repurchase will occur on the same day as the instrument event,  though any valid tenor is accepted with TenorUnit set to Day, Week, Month, or Year.  Note that TenorUnit T is not accepted here.
    purchasePrice: 0.0d,  // optional — The initial purchase price of the collateral.  If provided directly in this field, then Collateral.CollateralValue,  Haircut, and Margin should not be provided.
    repoRateSchedules: new List<Schedule>(),  // optional — Schedules used to calculate the repurchase price and any interest payments on the FlexibleRepo.  Only one schedule may be provided, and must be of type FixedSchedule or FloatSchedule.  If RepoType is OpenRepo, a FixedSchedule or FloatSchedule must be provided to calculate the expected Repo Rate,  and RepurchasePrice must be omitted.  If RepoType is TermRepo, only one of RepurchasePrice and RepoRateSchedules should be provided.  If a RepoRateSchedule is provided on a TermRepo, the PaymentFrequency in the FlowConventions should be 1T.  StubType must be set to None, and no ExDividend configuration should be provided.
    repurchasePrice: 0.0d,  // optional — The repurchase price of the repo, if known.  Only one of RepurchasePrice and RepoRateSchedules should be provided.  In the case of an OpenRepo, RepurchasePrice should not be provided,  and RepoRateSchedules should be provided instead in order to calculate the RepoRate.
    timeZoneConventions: new TimeZoneConventions(...),  // optional
    tradingConventions: new TradingConventions(...),  // optional
    isCollateralTransferActivated: true,  // optional — Indicates whether the FlexibleRepoCollateralTransfer event is activated.  Determines the behavior of manufactured coupons and related boolean parameters.  Defaults to false.  When true:  - Generates the FlexibleRepoCollateralTransfer event  - Processes collateral transfer transactions into holding changes  - Generates manufactured payments when due to be paid                When false:  - Does not generate the event  - Generates manufactured payments when due to be received
    instrumentType: "..."  // required — The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FlexibleRepo>(json);
```


- [Collateral](Collateral.md)
- [Schedule](Schedule.md) — used in `RepoRateSchedules`
- [TimeZoneConventions](TimeZoneConventions.md)
- [TradingConventions](TradingConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

