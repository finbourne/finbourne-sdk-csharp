# Finbourne.Sdk.Lusid.Model.CreateSimplePositionPortfolioRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the simple position portfolio. |
| **Description** | **string** | Optional | A description for the simple position portfolio. |
| **Code** | **string** | Required | The code of the simple position portfolio. Together with the scope this uniquely identifies the simple position portfolio. |
| **Created** | **DateTimeOffset?** | Optional | The effective datetime at which to create the simple position portfolio. No holdings can be set on the simple position portfolio before this date. Defaults to the current LUSID system datetime if not specified. |
| **BaseCurrency** | **string** | Required | The base currency of the simple position portfolio in ISO 4217 currency code format. |
| **CorporateActionSourceId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **AccountingMethod** | **string** | Optional | . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency |
| **SubHoldingKeys** | **List&lt;string&gt;** | Optional | A set of unique transaction properties to group the simple position portfolio&#39;s holdings by, perhaps for strategy tagging. Each property must be from the &#39;Transaction&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Transaction/strategies/quantsignal&#39;. See https://support.lusid.com/knowledgebase/article/KA-01879/en-us for more information. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of unique portfolio properties to add custom data to the simple position portfolio. Each property must be from the &#39;Portfolio&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. Note these properties must be pre-defined. |
| **InstrumentScopes** | **List&lt;string&gt;** | Optional | The resolution strategy used to resolve instruments of holdings upserted to this portfolio. |
| **AmortisationMethod** | **string** | Optional | The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate |
| **TransactionTypeScope** | **string** | Optional | The scope of the transaction types. |
| **CashGainLossCalculationDate** | **string** | Optional | The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. Defaults to SettlementDate. |
| **InstrumentEventConfiguration** | [InstrumentEventConfiguration](InstrumentEventConfiguration.md) | Optional | *No description available.* |
| **AmortisationRuleSetId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateSimplePositionPortfolioRequest(
    displayName: "...",  // required — The name of the simple position portfolio.
    description: "...",  // optional — A description for the simple position portfolio.
    code: "...",  // required — The code of the simple position portfolio. Together with the scope this uniquely identifies the simple position portfolio.
    created: DateTimeOffset.Now,  // optional — The effective datetime at which to create the simple position portfolio. No holdings can be set on the simple position portfolio before this date. Defaults to the current LUSID system datetime if not specified.
    baseCurrency: "...",  // required — The base currency of the simple position portfolio in ISO 4217 currency code format.
    corporateActionSourceId: new ResourceId(...),  // optional
    accountingMethod: "...",  // optional — . The available values are: Default, AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency
    subHoldingKeys: ,  // optional — A set of unique transaction properties to group the simple position portfolio&#39;s holdings by, perhaps for strategy tagging. Each property must be from the &#39;Transaction&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Transaction/strategies/quantsignal&#39;. See https://support.lusid.com/knowledgebase/article/KA-01879/en-us for more information.
    properties: new Property(...),  // optional — A set of unique portfolio properties to add custom data to the simple position portfolio. Each property must be from the &#39;Portfolio&#39; domain and identified by a key in the format {domain}/{scope}/{code}, for example &#39;Portfolio/Manager/Id&#39;. Note these properties must be pre-defined.
    instrumentScopes: ,  // optional — The resolution strategy used to resolve instruments of holdings upserted to this portfolio.
    amortisationMethod: "...",  // optional — The amortisation method used by the portfolio for the calculation. The available values are: NoAmortisation, StraightLine, EffectiveYield, StraightLineSettlementDate, EffectiveYieldSettlementDate
    transactionTypeScope: "...",  // optional — The scope of the transaction types.
    cashGainLossCalculationDate: "...",  // optional — The option when the Cash Gain Loss to be calulated, TransactionDate/SettlementDate. Defaults to SettlementDate.
    instrumentEventConfiguration: new InstrumentEventConfiguration(...),  // optional
    amortisationRuleSetId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateSimplePositionPortfolioRequest>(json);
```

- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [InstrumentEventConfiguration](InstrumentEventConfiguration.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

