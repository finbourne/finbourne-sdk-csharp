# Finbourne.Sdk.Lusid.Model.UpdateGroupReconciliationDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the Group Reconciliation Definition |
| **Description** | **string** | Optional | The description of the Group Reconciliation Definition |
| **PortfolioEntityIds** | [GroupReconciliationDefinitionPortfolioEntityIds](GroupReconciliationDefinitionPortfolioEntityIds.md) | Required | *No description available.* |
| **RecipeIds** | [GroupReconciliationDefinitionRecipeIds](GroupReconciliationDefinitionRecipeIds.md) | Optional | *No description available.* |
| **Currencies** | [GroupReconciliationDefinitionCurrencies](GroupReconciliationDefinitionCurrencies.md) | Optional | *No description available.* |
| **TransactionDateWindows** | [TransactionDateWindows](TransactionDateWindows.md) | Optional | *No description available.* |
| **ComparisonRulesetIds** | [GroupReconciliationDefinitionComparisonRulesetIds](GroupReconciliationDefinitionComparisonRulesetIds.md) | Optional | *No description available.* |
| **BreakCodeSource** | [BreakCodeSource](BreakCodeSource.md) | Optional | *No description available.* |
| **PrimarySchedule** | [PrimarySchedule](PrimarySchedule.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateGroupReconciliationDefinitionRequest(
    displayName: "...",  // required — The name of the Group Reconciliation Definition
    description: "...",  // optional — The description of the Group Reconciliation Definition
    portfolioEntityIds: new GroupReconciliationDefinitionPortfolioEntityIds(...),  // required
    recipeIds: new GroupReconciliationDefinitionRecipeIds(...),  // optional
    currencies: new GroupReconciliationDefinitionCurrencies(...),  // optional
    transactionDateWindows: new TransactionDateWindows(...),  // optional
    comparisonRulesetIds: new GroupReconciliationDefinitionComparisonRulesetIds(...),  // optional
    breakCodeSource: new BreakCodeSource(...),  // optional
    primarySchedule: new PrimarySchedule(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateGroupReconciliationDefinitionRequest>(json);
```

- [GroupReconciliationDefinitionPortfolioEntityIds](GroupReconciliationDefinitionPortfolioEntityIds.md)
- [GroupReconciliationDefinitionRecipeIds](GroupReconciliationDefinitionRecipeIds.md)
- [GroupReconciliationDefinitionCurrencies](GroupReconciliationDefinitionCurrencies.md)
- [TransactionDateWindows](TransactionDateWindows.md)
- [GroupReconciliationDefinitionComparisonRulesetIds](GroupReconciliationDefinitionComparisonRulesetIds.md)
- [BreakCodeSource](BreakCodeSource.md)
- [PrimarySchedule](PrimarySchedule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

