# Finbourne.Sdk.Lusid.Model.CreateRecipeRequest

Specification class to request for the creation/supplementing of a configuration recipe
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecipeCreationMarketDataScopes** | **List&lt;string&gt;** | Required | The scopes in which the recipe creation would look for quotes/data. |
| **RecipeId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **InlineRecipe** | [ConfigurationRecipe](ConfigurationRecipe.md) | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | The asAt date to use |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Required | The market data time, i.e. the recipe generated will look for rules with this effectiveAt. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateRecipeRequest(
    recipeCreationMarketDataScopes: ,  // required — The scopes in which the recipe creation would look for quotes/data.
    recipeId: new ResourceId(...),  // optional
    inlineRecipe: new ConfigurationRecipe(...),  // optional
    asAt: DateTimeOffset.Now,  // optional — The asAt date to use
    effectiveAt: new DateTimeOrCutLabel(...)  // required — The market data time, i.e. the recipe generated will look for rules with this effectiveAt.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateRecipeRequest>(json);
```

- [ResourceId](ResourceId.md)
- [ConfigurationRecipe](ConfigurationRecipe.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

