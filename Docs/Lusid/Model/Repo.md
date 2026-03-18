# Finbourne.Sdk.Lusid.Model.Repo

LUSID representation of a sale and repurchase agreement, supporting haircut, margin or repo rate methods.
> **Inherits from:** [LusidInstrument](LusidInstrument.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | The start date of the instrument. This is normally synonymous with the trade-date. |
| **MaturityDate** | **DateTimeOffset** | Required | The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it. |
| **DomCcy** | **string** | Required | The domestic currency of the instrument. |
| **AccrualBasis** | **string** | Required | For calculation of interest, the accrual basis to be used.  For more information on day counts, see [knowledge base article KA-01798](https://support.lusid.com/knowledgebase/article/KA-01798)                Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM]. |
| **Collateral** | [List&lt;LusidInstrument&gt;](LusidInstrument.md) | Optional | The actual collateral in the Repo.  This property is for informational purposes only, Lusid pricing is not affected. |
| **CollateralValue** | **decimal?** | Optional | The full market value of the collateral in domestic currency, before any margin or haircut is applied. |
| **Haircut** | **decimal?** | Optional | The haircut (or margin percentage) applied to the collateral, this should be a number between 0 and 1, i.e. for a 5% haircut this should be 0.05.  This is defined as (CollateralValue - PurchasePrice) / CollateralValue.  If this property is specified, so too must CollateralValue.  While this property is optional, one, and only one, of PurchasePrice, Margin and Haircut must be specified. |
| **Margin** | **decimal?** | Optional | The initial margin (or margin ratio) applied to the collateral, this should be a number greater than or equal to 1.0,  i.e. for a 102% margin this should be 1.02. A value of 1.0 means no margin (100%).  This is defined as CollateralValue / PurchasePrice.  If this property is specified, so too must CollateralValue.  While this property is optional, one, and only one, of PurchasePrice, Margin and Haircut must be specified. |
| **PurchasePrice** | **decimal?** | Optional | The price the collateral is initially purchased for, this property can be used to explicitly set the purchase price and not require  collateral value and a margin or haircut.  While this property is optional, one, and only one, of PurchasePrice, Margin and Haircut must be specified. |
| **RepoRate** | **decimal?** | Optional | The rate at which interest is to be accrue and be paid upon redemption of the collateral at maturity.  This field is used to calculate the Repurchase price.  While this property is optional, one, and only one, of the RepoRate and RepurchasePrice must be specified. |
| **RepurchasePrice** | **decimal?** | Optional | The price at which the collateral is repurchased, this field is optional and can be explicitly set here or will be calculated  from the PurchasePrice and RepoRate.  One, and only one, of the RepoRate and RepurchasePrice must be specified. |
| **TimeZoneConventions** | [TimeZoneConventions](TimeZoneConventions.md) | Optional | *No description available.* |
| **InstrumentType** | **string** | Required | The available values are: QuotedSecurity, InterestRateSwap, FxForward, Future, ExoticInstrument, FxOption, CreditDefaultSwap, InterestRateSwaption, Bond, EquityOption, FixedLeg, FloatingLeg, BespokeCashFlowsLeg, Unknown, TermDeposit, ContractForDifference, EquitySwap, CashPerpetual, CapFloor, CashSettled, CdsIndex, Basket, FundingLeg, FxSwap, ForwardRateAgreement, SimpleInstrument, Repo, Equity, ExchangeTradedOption, ReferenceInstrument, ComplexBond, InflationLinkedBond, InflationSwap, SimpleCashFlowLoan, TotalReturnSwap, InflationLeg, FundShareClass, FlexibleLoan, UnsettledCash, Cash, MasteredInstrument, LoanFacility, FlexibleDeposit, FlexibleRepo Default: `InstrumentTypeEnum.Repo` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Repo(
    startDate: DateTimeOffset.Now,  // required — The start date of the instrument. This is normally synonymous with the trade-date.
    maturityDate: DateTimeOffset.Now,  // required — The final maturity date of the instrument. This means the last date on which the instruments makes a payment of any amount.  For the avoidance of doubt, that is not necessarily prior to its last sensitivity date for the purposes of risk; e.g. instruments such as  Constant Maturity Swaps (CMS) often have sensitivities to rates that may well be observed or set prior to the maturity date, but refer to a termination date beyond it.
    domCcy: "...",  // required — The domestic currency of the instrument.
    accrualBasis: "...",  // required — For calculation of interest, the accrual basis to be used.  For more information on day counts, see [knowledge base article KA-01798](https://support.lusid.com/knowledgebase/article/KA-01798)                Supported string (enumeration) values are: [Actual360, Act360, MoneyMarket, Actual365, Act365, Thirty360, ThirtyU360, Bond, ThirtyE360, EuroBond, ActualActual, ActAct, ActActIsda, ActActIsma, ActActIcma, OneOne, Act364, Act365F, Act365L, Act365_25, Act252, Bus252, NL360, NL365, ActActAFB, Act365Cad, ThirtyActIsda, Thirty365Isda, ThirtyEActIsda, ThirtyE360Isda, ThirtyE365Isda, ThirtyU360EOM].
    collateral: new List<LusidInstrument>(),  // optional — The actual collateral in the Repo.  This property is for informational purposes only, Lusid pricing is not affected.
    collateralValue: 0.0d,  // optional — The full market value of the collateral in domestic currency, before any margin or haircut is applied.
    haircut: 0.0d,  // optional — The haircut (or margin percentage) applied to the collateral, this should be a number between 0 and 1, i.e. for a 5% haircut this should be 0.05.  This is defined as (CollateralValue - PurchasePrice) / CollateralValue.  If this property is specified, so too must CollateralValue.  While this property is optional, one, and only one, of PurchasePrice, Margin and Haircut must be specified.
    margin: 0.0d,  // optional — The initial margin (or margin ratio) applied to the collateral, this should be a number greater than or equal to 1.0,  i.e. for a 102% margin this should be 1.02. A value of 1.0 means no margin (100%).  This is defined as CollateralValue / PurchasePrice.  If this property is specified, so too must CollateralValue.  While this property is optional, one, and only one, of PurchasePrice, Margin and Haircut must be specified.
    purchasePrice: 0.0d,  // optional — The price the collateral is initially purchased for, this property can be used to explicitly set the purchase price and not require  collateral value and a margin or haircut.  While this property is optional, one, and only one, of PurchasePrice, Margin and Haircut must be specified.
    repoRate: 0.0d,  // optional — The rate at which interest is to be accrue and be paid upon redemption of the collateral at maturity.  This field is used to calculate the Repurchase price.  While this property is optional, one, and only one, of the RepoRate and RepurchasePrice must be specified.
    repurchasePrice: 0.0d,  // optional — The price at which the collateral is repurchased, this field is optional and can be explicitly set here or will be calculated  from the PurchasePrice and RepoRate.  One, and only one, of the RepoRate and RepurchasePrice must be specified.
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
var instance = JsonConvert.DeserializeObject<Repo>(json);
```


- [LusidInstrument](LusidInstrument.md) — used in `Collateral`
- [TimeZoneConventions](TimeZoneConventions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

