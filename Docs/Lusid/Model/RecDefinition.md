# Finbourne.Sdk.Lusid.Model.RecDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the rec definition. |
| **Description** | **string** | Optional | A description of the rec definition. |
| **DefinitionType** | **string** | Required | What this definition reconciles, naming the kind of dataset that must be present on at least one side. One of: PortfolioContents, LusidEntity, RelationalData. Only PortfolioContents is currently supported. Available values: PortfolioContents, LusidEntity, RelationalData. |
| **SideNames** | [RecDefSideNames](RecDefSideNames.md) | Optional | *No description available.* |
| **LeftPortfolioSources** | [List&lt;RecDefSource&gt;](RecDefSource.md) | Required | The portfolios, portfolio groups and funds contributing to the left side. Empty when the left side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty. |
| **RightPortfolioSources** | [List&lt;RecDefSource&gt;](RecDefSource.md) | Required | The portfolios, portfolio groups and funds contributing to the right side. Empty when the right side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty. |
| **ValuationRecipes** | [RecDefRecipeIds](RecDefRecipeIds.md) | Optional | *No description available.* |
| **Currencies** | [RecDefCurrencies](RecDefCurrencies.md) | Optional | *No description available.* |
| **Rulesets** | [List&lt;RecDefRuleset&gt;](RecDefRuleset.md) | Required | The types of reconciliation included in the group, each naming the matching ruleset that drives it. At least one entry is required, and each rec type may appear at most once. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDefinition(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the rec definition.
    description: "...",  // optional — A description of the rec definition.
    definitionType: "...",  // required — What this definition reconciles, naming the kind of dataset that must be present on at least one side. One of: PortfolioContents, LusidEntity, RelationalData. Only PortfolioContents is currently supported. Available values: PortfolioContents, LusidEntity, RelationalData.
    sideNames: new RecDefSideNames(...),  // optional
    leftPortfolioSources: new List<RecDefSource>(),  // required — The portfolios, portfolio groups and funds contributing to the left side. Empty when the left side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty.
    rightPortfolioSources: new List<RecDefSource>(),  // required — The portfolios, portfolio groups and funds contributing to the right side. Empty when the right side draws on relational data instead, which requires every ruleset to declare relational data for that side. Both sides cannot be empty.
    valuationRecipes: new RecDefRecipeIds(...),  // optional
    currencies: new RecDefCurrencies(...),  // optional
    rulesets: new List<RecDefRuleset>(),  // required — The types of reconciliation included in the group, each naming the matching ruleset that drives it. At least one entry is required, and each rec type may appear at most once.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [RecDefSideNames](RecDefSideNames.md)
- [RecDefSource](RecDefSource.md) — used in `LeftPortfolioSources`
- [RecDefSource](RecDefSource.md) — used in `RightPortfolioSources`
- [RecDefRecipeIds](RecDefRecipeIds.md)
- [RecDefCurrencies](RecDefCurrencies.md)
- [RecDefRuleset](RecDefRuleset.md) — used in `Rulesets`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

