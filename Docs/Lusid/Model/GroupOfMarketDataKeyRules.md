# Finbourne.Sdk.Lusid.Model.GroupOfMarketDataKeyRules

Represents a collection of MarketDataKeyRules that should be resolved together when resolving market data.  That is, market data resolution will always attempt to resolve with all rules in the group  before deciding what market data to return.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MarketDataKeyRuleGroupOperation** | **string** | Required | The operation that will be used to process the collection of market data items and failures found on resolution  into a single market data item or failure to be used.  Supported values: [FirstLatest, AverageOfQuotesFound, AverageOfAllQuotes, FirstMinimum, FirstMaximum] |
| **MarketRules** | [List&lt;MarketDataKeyRule&gt;](MarketDataKeyRule.md) | Required | The rules that should be grouped together in market data resolution. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupOfMarketDataKeyRules(
    marketDataKeyRuleGroupOperation: "...",  // required — The operation that will be used to process the collection of market data items and failures found on resolution  into a single market data item or failure to be used.  Supported values: [FirstLatest, AverageOfQuotesFound, AverageOfAllQuotes, FirstMinimum, FirstMaximum]
    marketRules: new List<MarketDataKeyRule>()  // required — The rules that should be grouped together in market data resolution.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupOfMarketDataKeyRules>(json);
```

- [MarketDataKeyRule](MarketDataKeyRule.md) — used in `MarketRules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

