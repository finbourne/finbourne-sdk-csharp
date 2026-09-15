# Finbourne.Sdk.Lusid.Model.CreateTransferRequest

A request to create a transfer: the paired transaction legs that move a position, and the Transfer entity  recording them.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstrumentIdentifierOut** | **string** | Required | *No description available.* |
| **InstrumentIdentifierIn** | **string** | Required | *No description available.* |
| **PricingMethod** | **string** | Required | Available values: AtCost, AtPrice. |
| **TaxLotStructure** | **string** | Optional | Available values: Consolidate, Preserve. |
| **UnitsOut** | **decimal** | Required | *No description available.* |
| **UnitsIn** | **decimal** | Required | *No description available.* |
| **AmountOut** | **decimal?** | Optional | *No description available.* |
| **WeightOut** | **decimal?** | Optional | *No description available.* |
| **TradeDateOut** | **DateTimeOffset** | Required | *No description available.* |
| **TradeDateIn** | **DateTimeOffset** | Required | *No description available.* |
| **SettlementDateOut** | **DateTimeOffset** | Required | *No description available.* |
| **SettlementDateIn** | **DateTimeOffset?** | Optional | *No description available.* |
| **ExchangeRateOut** | **decimal?** | Optional | *No description available.* |
| **ExchangeRateIn** | **decimal?** | Optional | *No description available.* |
| **TransactionPriceOut** | **decimal?** | Optional | *No description available.* |
| **TransactionPriceIn** | **decimal?** | Optional | *No description available.* |
| **CounterpartyIdOut** | **string** | Optional | *No description available.* |
| **CounterpartyIdIn** | **string** | Optional | *No description available.* |
| **CustodianAccountIdOut** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CustodianAccountIdIn** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Source** | **string** | Required | *No description available.* |
| **AccountingMethod** | **string** | Optional | Available values: AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency. |
| **PropertiesOut** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |
| **PropertiesIn** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateTransferRequest(
    transferId: new ResourceId(...),  // required
    portfolioIdOut: new ResourceId(...),  // required
    portfolioIdIn: new ResourceId(...),  // required
    instrumentIdentifierOut: "...",  // required
    instrumentIdentifierIn: "...",  // required
    pricingMethod: "...",  // required — Available values: AtCost, AtPrice.
    taxLotStructure: "...",  // optional — Available values: Consolidate, Preserve.
    unitsOut: 0.0d,  // required
    unitsIn: 0.0d,  // required
    amountOut: 0.0d,  // optional
    weightOut: 0.0d,  // optional
    tradeDateOut: DateTimeOffset.Now,  // required
    tradeDateIn: DateTimeOffset.Now,  // required
    settlementDateOut: DateTimeOffset.Now,  // required
    settlementDateIn: DateTimeOffset.Now,  // optional
    exchangeRateOut: 0.0d,  // optional
    exchangeRateIn: 0.0d,  // optional
    transactionPriceOut: 0.0d,  // optional
    transactionPriceIn: 0.0d,  // optional
    counterpartyIdOut: "...",  // optional
    counterpartyIdIn: "...",  // optional
    custodianAccountIdOut: new ResourceId(...),  // optional
    custodianAccountIdIn: new ResourceId(...),  // optional
    source: "...",  // required
    accountingMethod: "...",  // optional — Available values: AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency.
    propertiesOut: new PerpetualProperty(...),  // optional
    propertiesIn: new PerpetualProperty(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateTransferRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [PerpetualProperty](PerpetualProperty.md)
- [PerpetualProperty](PerpetualProperty.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

