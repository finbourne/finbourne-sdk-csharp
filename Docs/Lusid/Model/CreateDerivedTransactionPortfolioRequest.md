# Finbourne.Sdk.Lusid.Model.CreateDerivedTransactionPortfolioRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the derived transaction portfolio. |
| **Description** | **string** | Optional | A description for the derived transaction portfolio. |
| **Code** | **string** | Required | The code of the derived transaction portfolio. Together with the scope this uniquely identifies the derived transaction portfolio. |
| **ParentPortfolioId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Created** | **DateTimeOffset?** | Optional | This will be auto-populated to be the parent portfolio creation date. |
| **CorporateActionSourceId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AccountingMethod** | **string** | Optional | . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency |
| **SubHoldingKeys** | **List&lt;string&gt;** | Optional | A set of unique transaction properties to group the derived transaction portfolio&#39;s holdings by, perhaps for strategy tagging. Each property must be from the &#39;Transaction&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Transaction/strategies/quantsignal&#39;. See https://support.lusid.com/knowledgebase/article/KA-01879/en-us for more information. |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | The resolution strategy used to resolve instruments of transactions/holdings upserted to this derived portfolio. |
| **AmortisationMethod** | **string** | Optional | The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate |
| **TransactionTypeScope** | **string** | Optional | The scope of the transaction types. |
| **CashGainLossCalculationDate** | **string** | Optional | The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. Defaults to SettlementDate. |
| **AmortisationRuleSetId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InstrumentEventConfiguration** | [InstrumentEventConfiguration](InstrumentEventConfiguration.md) | Optional | *No description available.* |
| **SettlementConfiguration** | [PortfolioSettlementConfiguration](PortfolioSettlementConfiguration.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateDerivedTransactionPortfolioRequest(
    displayName: "...",  // required — The name of the derived transaction portfolio.
    description: "...",  // optional — A description for the derived transaction portfolio.
    code: "...",  // required — The code of the derived transaction portfolio. Together with the scope this uniquely identifies the derived transaction portfolio.
    parentPortfolioId: new ResourceId(...),  // required
    created: DateTimeOffset.Now,  // optional — This will be auto-populated to be the parent portfolio creation date.
    corporateActionSourceId: new ResourceId(...),  // optional
    accountingMethod: "...",  // optional — . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency
    subHoldingKeys: ,  // optional — A set of unique transaction properties to group the derived transaction portfolio&#39;s holdings by, perhaps for strategy tagging. Each property must be from the &#39;Transaction&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Transaction/strategies/quantsignal&#39;. See https://support.lusid.com/knowledgebase/article/KA-01879/en-us for more information.
    instrumentScopes: ,  // optional — The resolution strategy used to resolve instruments of transactions/holdings upserted to this derived portfolio.
    amortisationMethod: "...",  // optional — The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate
    transactionTypeScope: "...",  // optional — The scope of the transaction types.
    cashGainLossCalculationDate: "...",  // optional — The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. Defaults to SettlementDate.
    amortisationRuleSetId: new ResourceId(...),  // optional
    instrumentEventConfiguration: new InstrumentEventConfiguration(...),  // optional
    settlementConfiguration: new PortfolioSettlementConfiguration(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateDerivedTransactionPortfolioRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [InstrumentEventConfiguration](InstrumentEventConfiguration.md)
- [PortfolioSettlementConfiguration](PortfolioSettlementConfiguration.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

