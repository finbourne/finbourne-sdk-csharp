# Finbourne.Sdk.Lusid.Model.PortfolioContentsRecDefinitionDetails

A definition reconciling the contents of LUSID portfolios on at least one side, with a relational dataset  permitted on the other.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LeftPortfolioSources** | [List&lt;RecDefSource&gt;](RecDefSource.md) | Required | The portfolios, portfolio groups and funds contributing to the left side. Empty when the left side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty. |
| **RightPortfolioSources** | [List&lt;RecDefSource&gt;](RecDefSource.md) | Required | The portfolios, portfolio groups and funds contributing to the right side. Empty when the right side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty. |
| **ValuationRecipes** | [RecDefRecipeIds](RecDefRecipeIds.md) | Optional | *No description available.* |
| **Currencies** | [RecDefCurrencies](RecDefCurrencies.md) | Optional | *No description available.* |
| **Rulesets** | [List&lt;RecDefRuleset&gt;](RecDefRuleset.md) | Required | The types of reconciliation included in the group, each naming the matching ruleset that drives it. At least one entry is required, and each rec type may appear at most once. |
| **DefinitionType** | **string** | Required | What this definition reconciles, and so which shape of details it carries. PortfolioContents and External are supported; LusidEntity is not yet. Available values: PortfolioContents, LusidEntity, External. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PortfolioContentsRecDefinitionDetails(
    leftPortfolioSources: new List<RecDefSource>(),  // required — The portfolios, portfolio groups and funds contributing to the left side. Empty when the left side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty.
    rightPortfolioSources: new List<RecDefSource>(),  // required — The portfolios, portfolio groups and funds contributing to the right side. Empty when the right side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty.
    valuationRecipes: new RecDefRecipeIds(...),  // optional
    currencies: new RecDefCurrencies(...),  // optional
    rulesets: new List<RecDefRuleset>(),  // required — The types of reconciliation included in the group, each naming the matching ruleset that drives it. At least one entry is required, and each rec type may appear at most once.
    definitionType: "..."  // required — What this definition reconciles, and so which shape of details it carries. PortfolioContents and External are supported; LusidEntity is not yet. Available values: PortfolioContents, LusidEntity, External.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PortfolioContentsRecDefinitionDetails>(json);
```


## Related Models

- [RecDefSource](RecDefSource.md) — used in `LeftPortfolioSources`
- [RecDefSource](RecDefSource.md) — used in `RightPortfolioSources`
- [RecDefRecipeIds](RecDefRecipeIds.md)
- [RecDefCurrencies](RecDefCurrencies.md)
- [RecDefRuleset](RecDefRuleset.md) — used in `Rulesets`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

