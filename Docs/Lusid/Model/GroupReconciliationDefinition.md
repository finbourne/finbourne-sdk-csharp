# Finbourne.Sdk.Lusid.Model.GroupReconciliationDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Group Reconciliation Definition |
| **Description** | **string** | Optional | The description of the Group Reconciliation Definition |
| **PortfolioEntityIds** | [GroupReconciliationDefinitionPortfolioEntityIds](GroupReconciliationDefinitionPortfolioEntityIds.md) | Optional | *No description available.* |
| **RecipeIds** | [GroupReconciliationDefinitionRecipeIds](GroupReconciliationDefinitionRecipeIds.md) | Optional | *No description available.* |
| **Currencies** | [GroupReconciliationDefinitionCurrencies](GroupReconciliationDefinitionCurrencies.md) | Optional | *No description available.* |
| **TransactionDateWindows** | [TransactionDateWindows](TransactionDateWindows.md) | Optional | *No description available.* |
| **ComparisonRulesetIds** | [GroupReconciliationDefinitionComparisonRulesetIds](GroupReconciliationDefinitionComparisonRulesetIds.md) | Optional | *No description available.* |
| **BreakCodeSource** | [BreakCodeSource](BreakCodeSource.md) | Optional | *No description available.* |
| **PrimarySchedule** | [PrimarySchedule](PrimarySchedule.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDefinition(
    id: new ResourceId(...),  // optional
    displayName: "...",  // optional — The name of the Group Reconciliation Definition
    description: "...",  // optional — The description of the Group Reconciliation Definition
    portfolioEntityIds: new GroupReconciliationDefinitionPortfolioEntityIds(...),  // optional
    recipeIds: new GroupReconciliationDefinitionRecipeIds(...),  // optional
    currencies: new GroupReconciliationDefinitionCurrencies(...),  // optional
    transactionDateWindows: new TransactionDateWindows(...),  // optional
    comparisonRulesetIds: new GroupReconciliationDefinitionComparisonRulesetIds(...),  // optional
    breakCodeSource: new BreakCodeSource(...),  // optional
    primarySchedule: new PrimarySchedule(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [GroupReconciliationDefinitionPortfolioEntityIds](GroupReconciliationDefinitionPortfolioEntityIds.md)
- [GroupReconciliationDefinitionRecipeIds](GroupReconciliationDefinitionRecipeIds.md)
- [GroupReconciliationDefinitionCurrencies](GroupReconciliationDefinitionCurrencies.md)
- [TransactionDateWindows](TransactionDateWindows.md)
- [GroupReconciliationDefinitionComparisonRulesetIds](GroupReconciliationDefinitionComparisonRulesetIds.md)
- [BreakCodeSource](BreakCodeSource.md)
- [PrimarySchedule](PrimarySchedule.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

