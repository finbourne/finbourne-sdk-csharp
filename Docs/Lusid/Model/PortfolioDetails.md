# Finbourne.Sdk.Lusid.Model.PortfolioDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **OriginPortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **BaseCurrency** | **string** | Required | The base currency of the transaction portfolio. |
| **CorporateActionSourceId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **SubHoldingKeys** | **List&lt;string&gt;** | Optional | *No description available.* |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | The resolution strategy used to resolve instruments of transactions/holdings upserted to the transaction portfolio. |
| **AccountingMethod** | **string** | Optional | . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency |
| **AmortisationMethod** | **string** | Optional | The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate |
| **TransactionTypeScope** | **string** | Optional | The scope of the transaction types. |
| **CashGainLossCalculationDate** | **string** | Optional | The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. Defaults to SettlementDate. |
| **InstrumentEventConfiguration** | [InstrumentEventConfiguration](InstrumentEventConfiguration.md) | Optional | *No description available.* |
| **AmortisationRuleSetId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **TaxRuleSetScope** | **string** | Optional | The scope of the tax rule sets for this portfolio. |
| **SettlementConfiguration** | [PortfolioSettlementConfiguration](PortfolioSettlementConfiguration.md) | Optional | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioDetails(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    originPortfolioId: new ResourceId(...),  // required
    varVersion: new ModelVersion(...),  // required
    baseCurrency: "...",  // required — The base currency of the transaction portfolio.
    corporateActionSourceId: new ResourceId(...),  // optional
    subHoldingKeys: ,  // optional
    instrumentScopes: ,  // optional — The resolution strategy used to resolve instruments of transactions/holdings upserted to the transaction portfolio.
    accountingMethod: "...",  // optional — . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency
    amortisationMethod: "...",  // optional — The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate
    transactionTypeScope: "...",  // optional — The scope of the transaction types.
    cashGainLossCalculationDate: "...",  // optional — The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. Defaults to SettlementDate.
    instrumentEventConfiguration: new InstrumentEventConfiguration(...),  // optional
    amortisationRuleSetId: new ResourceId(...),  // optional
    taxRuleSetScope: "...",  // optional — The scope of the tax rule sets for this portfolio.
    settlementConfiguration: new PortfolioSettlementConfiguration(...),  // optional
    stagedModifications: new StagedModificationsInfo(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioDetails>(json);
```

- [ResourceId](ResourceId.md)
- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)
- [InstrumentEventConfiguration](InstrumentEventConfiguration.md)
- [ResourceId](ResourceId.md)
- [PortfolioSettlementConfiguration](PortfolioSettlementConfiguration.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

