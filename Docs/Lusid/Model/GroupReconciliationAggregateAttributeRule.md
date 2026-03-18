# Finbourne.Sdk.Lusid.Model.GroupReconciliationAggregateAttributeRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [GroupReconciliationAggregateComparisonRuleOperand](GroupReconciliationAggregateComparisonRuleOperand.md) | Required | *No description available.* |
| **Right** | [GroupReconciliationAggregateComparisonRuleOperand](GroupReconciliationAggregateComparisonRuleOperand.md) | Required | *No description available.* |
| **Tolerance** | [GroupReconciliationComparisonRuleTolerance](GroupReconciliationComparisonRuleTolerance.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationAggregateAttributeRule(
    left: new GroupReconciliationAggregateComparisonRuleOperand(...),  // required
    right: new GroupReconciliationAggregateComparisonRuleOperand(...),  // required
    tolerance: new GroupReconciliationComparisonRuleTolerance(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationAggregateAttributeRule>(json);
```


## Related Models

- [GroupReconciliationAggregateComparisonRuleOperand](GroupReconciliationAggregateComparisonRuleOperand.md)
- [GroupReconciliationAggregateComparisonRuleOperand](GroupReconciliationAggregateComparisonRuleOperand.md)
- [GroupReconciliationComparisonRuleTolerance](GroupReconciliationComparisonRuleTolerance.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

