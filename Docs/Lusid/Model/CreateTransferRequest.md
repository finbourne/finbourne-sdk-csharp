# Finbourne.Sdk.Lusid.Model.CreateTransferRequest

A request to create a transfer: the paired transaction legs that move a position, and the Transfer entity  recording them.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TransferId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioIdOut** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **PortfolioIdIn** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstrumentIdentifierOut** | **string** | Required | The LUSID instrument id of the instrument moving out. A position in this instrument must exist in the outgoing portfolio on the outgoing trade date. |
| **InstrumentIdentifierIn** | **string** | Required | The LUSID instrument id of the instrument moving in. Equal to InstrumentIdentifierOut for a transfer between portfolios. |
| **PricingMethod** | **string** | Required | How the legs are priced. &#39;AtCost&#39; uses the cost per unit of the outgoing holding; &#39;AtPrice&#39; uses the supplied TransactionPriceOut, which is then required. Available values: AtCost, AtPrice. |
| **TaxLotStructure** | **string** | Optional | What happens to the tax lots of the outgoing position. Only &#39;Consolidate&#39; is currently supported; &#39;Preserve&#39; is rejected. Defaults to &#39;Consolidate&#39;. Available values: Consolidate, Preserve. |
| **UnitsOut** | **decimal** | Required | The number of units to move out. Must be greater than zero. |
| **UnitsIn** | **decimal** | Required | The number of units to move in. Must be greater than zero. |
| **AmountOut** | **decimal?** | Optional | The total consideration of the outgoing leg. Recorded, not applied. |
| **WeightOut** | **decimal?** | Optional | The weighting factor of the outgoing leg. Recorded, not applied. |
| **TradeDateOut** | **DateTimeOffset** | Required | The trade date of the outgoing leg. Must not be later than TradeDateIn. |
| **TradeDateIn** | **DateTimeOffset** | Required | The trade date of the incoming leg. |
| **SettlementDateOut** | **DateTimeOffset** | Required | The settlement date of the outgoing leg. Must not be later than SettlementDateIn. |
| **SettlementDateIn** | **DateTimeOffset?** | Optional | The settlement date of the incoming leg. Defaults to SettlementDateOut when not supplied. |
| **ExchangeRateOut** | **decimal?** | Optional | The FX rate to apply to the outgoing leg. |
| **ExchangeRateIn** | **decimal?** | Optional | The FX rate to apply to the incoming leg. |
| **TransactionPriceOut** | **decimal?** | Optional | The unit price of the outgoing leg. Required when PricingMethod is &#39;AtPrice&#39;, and ignored when it is &#39;AtCost&#39;. |
| **TransactionPriceIn** | **decimal?** | Optional | The unit price of the incoming leg. Ignored for a transfer, which carries the outgoing price across; defaults to the outgoing price for a switch. |
| **CounterpartyIdOut** | **string** | Optional | The counterparty identifier of the outgoing leg. |
| **CounterpartyIdIn** | **string** | Optional | The counterparty identifier of the incoming leg. Defaults to CounterpartyIdOut. |
| **CustodianAccountIdOut** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **CustodianAccountIdIn** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Source** | **string** | Required | The transaction source the generated legs are booked against. |
| **AccountingMethod** | **string** | Optional | An accounting method to record against the transfer. Available values: AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency. |
| **PropertiesOut** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Transaction Properties to set on the outgoing transaction leg, and on the incoming transaction leg when PropertiesIn is absent. Supplying an empty collection for PropertiesIn leaves the incoming leg with no properties. |
| **PropertiesIn** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Transaction Properties to set on the incoming transaction leg, replacing rather than adding to PropertiesOut. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Properties to set on the transfer itself, in the Transfer domain. These are separate from PropertiesOut and PropertiesIn, which are Transaction domain and land on the legs. |
| **TransactionToPortfolioRateOut** | **decimal?** | Optional | The rate from the outgoing leg&#39;s trade currency to the outgoing portfolio&#39;s base currency, applied whenever supplied. |
| **TransactionToPortfolioRateIn** | **decimal?** | Optional | The rate from the incoming leg&#39;s trade currency to the incoming portfolio&#39;s base currency. Required when the two portfolios have different base currencies, and applied whenever supplied. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateTransferRequest(
    transferId: new ResourceId(...),  // required
    portfolioIdOut: new ResourceId(...),  // required
    portfolioIdIn: new ResourceId(...),  // required
    instrumentIdentifierOut: "...",  // required — The LUSID instrument id of the instrument moving out. A position in this instrument must exist in the outgoing portfolio on the outgoing trade date.
    instrumentIdentifierIn: "...",  // required — The LUSID instrument id of the instrument moving in. Equal to InstrumentIdentifierOut for a transfer between portfolios.
    pricingMethod: "...",  // required — How the legs are priced. &#39;AtCost&#39; uses the cost per unit of the outgoing holding; &#39;AtPrice&#39; uses the supplied TransactionPriceOut, which is then required. Available values: AtCost, AtPrice.
    taxLotStructure: "...",  // optional — What happens to the tax lots of the outgoing position. Only &#39;Consolidate&#39; is currently supported; &#39;Preserve&#39; is rejected. Defaults to &#39;Consolidate&#39;. Available values: Consolidate, Preserve.
    unitsOut: 0.0d,  // required — The number of units to move out. Must be greater than zero.
    unitsIn: 0.0d,  // required — The number of units to move in. Must be greater than zero.
    amountOut: 0.0d,  // optional — The total consideration of the outgoing leg. Recorded, not applied.
    weightOut: 0.0d,  // optional — The weighting factor of the outgoing leg. Recorded, not applied.
    tradeDateOut: DateTimeOffset.Now,  // required — The trade date of the outgoing leg. Must not be later than TradeDateIn.
    tradeDateIn: DateTimeOffset.Now,  // required — The trade date of the incoming leg.
    settlementDateOut: DateTimeOffset.Now,  // required — The settlement date of the outgoing leg. Must not be later than SettlementDateIn.
    settlementDateIn: DateTimeOffset.Now,  // optional — The settlement date of the incoming leg. Defaults to SettlementDateOut when not supplied.
    exchangeRateOut: 0.0d,  // optional — The FX rate to apply to the outgoing leg.
    exchangeRateIn: 0.0d,  // optional — The FX rate to apply to the incoming leg.
    transactionPriceOut: 0.0d,  // optional — The unit price of the outgoing leg. Required when PricingMethod is &#39;AtPrice&#39;, and ignored when it is &#39;AtCost&#39;.
    transactionPriceIn: 0.0d,  // optional — The unit price of the incoming leg. Ignored for a transfer, which carries the outgoing price across; defaults to the outgoing price for a switch.
    counterpartyIdOut: "...",  // optional — The counterparty identifier of the outgoing leg.
    counterpartyIdIn: "...",  // optional — The counterparty identifier of the incoming leg. Defaults to CounterpartyIdOut.
    custodianAccountIdOut: new ResourceId(...),  // optional
    custodianAccountIdIn: new ResourceId(...),  // optional
    source: "...",  // required — The transaction source the generated legs are booked against.
    accountingMethod: "...",  // optional — An accounting method to record against the transfer. Available values: AverageCost, FirstInFirstOut, LastInFirstOut, HighestCostFirst, LowestCostFirst, ProRateByUnits, ProRateByCost, ProRateByCostPortfolioCurrency, IntraDayThenFirstInFirstOut, LongTermHighestCostFirst, LongTermHighestCostFirstPortfolioCurrency, HighestCostFirstPortfolioCurrency, LowestCostFirstPortfolioCurrency, MaximumLossMinimumGain, MaximumLossMinimumGainPortfolioCurrency.
    propertiesOut: new PerpetualProperty(...),  // optional — Transaction Properties to set on the outgoing transaction leg, and on the incoming transaction leg when PropertiesIn is absent. Supplying an empty collection for PropertiesIn leaves the incoming leg with no properties.
    propertiesIn: new PerpetualProperty(...),  // optional — Transaction Properties to set on the incoming transaction leg, replacing rather than adding to PropertiesOut.
    properties: new PerpetualProperty(...),  // optional — Properties to set on the transfer itself, in the Transfer domain. These are separate from PropertiesOut and PropertiesIn, which are Transaction domain and land on the legs.
    transactionToPortfolioRateOut: 0.0d,  // optional — The rate from the outgoing leg&#39;s trade currency to the outgoing portfolio&#39;s base currency, applied whenever supplied.
    transactionToPortfolioRateIn: 0.0d  // optional — The rate from the incoming leg&#39;s trade currency to the incoming portfolio&#39;s base currency. Required when the two portfolios have different base currencies, and applied whenever supplied.
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
- [PerpetualProperty](PerpetualProperty.md) — used in `PropertiesOut`
- [PerpetualProperty](PerpetualProperty.md) — used in `PropertiesIn`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

