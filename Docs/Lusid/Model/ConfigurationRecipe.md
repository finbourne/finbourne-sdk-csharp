# Finbourne.Sdk.Lusid.Model.ConfigurationRecipe

The Configuration or Calculation Recipe controls how LUSID processes a given request.  This can be used to change where market data used in pricing is loaded from and in what order, or which model is used to  price a given instrument as well as how aggregation will process the produced results.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope used when updating or inserting the Configuration Recipe. |
| **Code** | **string** | Required | User given string name (code) to identify the recipe. |
| **Market** | [MarketContext](MarketContext.md) | Optional | *No description available.* |
| **Pricing** | [PricingContext](PricingContext.md) | Optional | *No description available.* |
| **Aggregation** | [AggregationContext](AggregationContext.md) | Optional | *No description available.* |
| **Description** | **string** | Optional | User can assign a description to understand more humanly the recipe. |
| **Holding** | [HoldingContext](HoldingContext.md) | Optional | *No description available.* |
| **Translation** | [TranslationContext](TranslationContext.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ConfigurationRecipe(
    scope: "...",  // required — The scope used when updating or inserting the Configuration Recipe.
    code: "...",  // required — User given string name (code) to identify the recipe.
    market: new MarketContext(...),  // optional
    pricing: new PricingContext(...),  // optional
    aggregation: new AggregationContext(...),  // optional
    description: "...",  // optional — User can assign a description to understand more humanly the recipe.
    holding: new HoldingContext(...),  // optional
    translation: new TranslationContext(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConfigurationRecipe>(json);
```

- [MarketContext](MarketContext.md)
- [PricingContext](PricingContext.md)
- [AggregationContext](AggregationContext.md)
- [HoldingContext](HoldingContext.md)
- [TranslationContext](TranslationContext.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

