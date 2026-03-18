# Finbourne.Sdk.Lusid.Model.Portfolio

A portfolio of a particular type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Type** | **string** | Required | The type of the portfolio. The available values are: Transaction, Reference, DerivedTransaction, SimplePosition |
| **DisplayName** | **string** | Required | The name of the portfolio. |
| **Description** | **string** | Optional | The long form description of the portfolio. |
| **Created** | **DateTimeOffset** | Required | The effective datetime at which the portfolio was created. No transactions or constituents can be added to the portfolio before this date. |
| **ParentPortfolioId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **IsDerived** | **bool** | Optional | Whether or not this is a derived portfolio. |
| **BaseCurrency** | **string** | Optional | The base currency of the portfolio. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The requested portfolio properties. These will be from the &#39;Portfolio&#39; domain. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Optional | A set of relationships associated to the portfolio. |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | The instrument scope resolution strategy of this portfolio. |
| **AccountingMethod** | **string** | Optional | . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency |
| **AmortisationMethod** | **string** | Optional | The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate |
| **TransactionTypeScope** | **string** | Optional | The scope of the transaction types. |
| **CashGainLossCalculationDate** | **string** | Optional | The scope of the transaction types. |
| **InstrumentEventConfiguration** | [InstrumentEventConfiguration](InstrumentEventConfiguration.md) | Optional | *No description available.* |
| **AmortisationRuleSetId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TaxRuleSetScope** | **string** | Optional | The scope of the tax rule sets for this portfolio. |
| **SettlementConfiguration** | [PortfolioSettlementConfiguration](PortfolioSettlementConfiguration.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Portfolio(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    id: new ResourceId(...),  // required
    type: "...",  // required — The type of the portfolio. The available values are: Transaction, Reference, DerivedTransaction, SimplePosition
    displayName: "...",  // required — The name of the portfolio.
    description: "...",  // optional — The long form description of the portfolio.
    created: DateTimeOffset.Now,  // required — The effective datetime at which the portfolio was created. No transactions or constituents can be added to the portfolio before this date.
    parentPortfolioId: new ResourceId(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    stagedModifications: new StagedModificationsInfo(...),  // optional
    isDerived: true,  // optional — Whether or not this is a derived portfolio.
    baseCurrency: "...",  // optional — The base currency of the portfolio.
    properties: new Property(...),  // optional — The requested portfolio properties. These will be from the &#39;Portfolio&#39; domain.
    relationships: new List<Relationship>(),  // optional — A set of relationships associated to the portfolio.
    instrumentScopes: ,  // optional — The instrument scope resolution strategy of this portfolio.
    accountingMethod: "...",  // optional — . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency
    amortisationMethod: "...",  // optional — The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate
    transactionTypeScope: "...",  // optional — The scope of the transaction types.
    cashGainLossCalculationDate: "...",  // optional — The scope of the transaction types.
    instrumentEventConfiguration: new InstrumentEventConfiguration(...),  // optional
    amortisationRuleSetId: new ResourceId(...),  // optional
    taxRuleSetScope: "...",  // optional — The scope of the tax rule sets for this portfolio.
    settlementConfiguration: new PortfolioSettlementConfiguration(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Portfolio>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Property](Property.md) — used in `Properties`
- [Relationship](Relationship.md) — used in `Relationships`
- [InstrumentEventConfiguration](InstrumentEventConfiguration.md)
- [ResourceId](ResourceId.md)
- [PortfolioSettlementConfiguration](PortfolioSettlementConfiguration.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

