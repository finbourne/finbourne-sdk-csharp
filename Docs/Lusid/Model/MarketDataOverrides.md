# Finbourne.Sdk.Lusid.Model.MarketDataOverrides

Class which holds market data overrides to be used in valuation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComplexMarketData** | [List&lt;EconomicDependencyWithComplexMarketData&gt;](EconomicDependencyWithComplexMarketData.md) | Optional | A list of EconomicDependency paired with quote data satisfying that economic dependency |
| **Quotes** | [List&lt;EconomicDependencyWithQuote&gt;](EconomicDependencyWithQuote.md) | Optional | A list of EconomicDependency paired with a ComplexMarketData satisfying that economic dependency |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MarketDataOverrides(
    complexMarketData: new List<EconomicDependencyWithComplexMarketData>(),  // optional — A list of EconomicDependency paired with quote data satisfying that economic dependency
    quotes: new List<EconomicDependencyWithQuote>()  // optional — A list of EconomicDependency paired with a ComplexMarketData satisfying that economic dependency
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MarketDataOverrides>(json);
```


## Related Models

- [EconomicDependencyWithComplexMarketData](EconomicDependencyWithComplexMarketData.md) — used in `ComplexMarketData`
- [EconomicDependencyWithQuote](EconomicDependencyWithQuote.md) — used in `Quotes`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

