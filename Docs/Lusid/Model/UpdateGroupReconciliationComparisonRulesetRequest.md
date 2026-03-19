# Finbourne.Sdk.Lusid.Model.UpdateGroupReconciliationComparisonRulesetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the ruleset |
| **ReconciliationType** | **string** | Required | The type of reconciliation to perform. \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot; |
| **Filters** | [GroupReconciliationFilters](GroupReconciliationFilters.md) | Optional | *No description available.* |
| **CoreAttributeRules** | [List&lt;GroupReconciliationCoreAttributeRule&gt;](GroupReconciliationCoreAttributeRule.md) | Required | The core comparison rules |
| **AggregateAttributeRules** | [List&lt;GroupReconciliationAggregateAttributeRule&gt;](GroupReconciliationAggregateAttributeRule.md) | Required | The aggregate comparison rules |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateGroupReconciliationComparisonRulesetRequest(
    displayName: "...",  // required — The name of the ruleset
    reconciliationType: "...",  // required — The type of reconciliation to perform. \&quot;Holding\&quot; | \&quot;Transaction\&quot; | \&quot;Valuation\&quot;
    filters: new GroupReconciliationFilters(...),  // optional
    coreAttributeRules: new List<GroupReconciliationCoreAttributeRule>(),  // required — The core comparison rules
    aggregateAttributeRules: new List<GroupReconciliationAggregateAttributeRule>()  // required — The aggregate comparison rules
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateGroupReconciliationComparisonRulesetRequest>(json);
```

- [GroupReconciliationFilters](GroupReconciliationFilters.md)
- [GroupReconciliationCoreAttributeRule](GroupReconciliationCoreAttributeRule.md) — used in `CoreAttributeRules`
- [GroupReconciliationAggregateAttributeRule](GroupReconciliationAggregateAttributeRule.md) — used in `AggregateAttributeRules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

