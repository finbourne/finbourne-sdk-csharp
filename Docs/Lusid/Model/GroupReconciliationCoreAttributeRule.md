# Finbourne.Sdk.Lusid.Model.GroupReconciliationCoreAttributeRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [GroupReconciliationCoreComparisonRuleOperand](GroupReconciliationCoreComparisonRuleOperand.md) | Required | *No description available.* |
| **Right** | [GroupReconciliationCoreComparisonRuleOperand](GroupReconciliationCoreComparisonRuleOperand.md) | Required | *No description available.* |
| **AllowableStringMappings** | [List&lt;GroupReconciliationComparisonRuleStringValueMap&gt;](GroupReconciliationComparisonRuleStringValueMap.md) | Optional | The string mappings to use when comparing |
| **IsComparisonCaseSensitive** | **bool** | Required | Whether the compare keys and strings mappings case sensitive or not |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationCoreAttributeRule(
    left: new GroupReconciliationCoreComparisonRuleOperand(...),  // required
    right: new GroupReconciliationCoreComparisonRuleOperand(...),  // required
    allowableStringMappings: new List<GroupReconciliationComparisonRuleStringValueMap>(),  // optional — The string mappings to use when comparing
    isComparisonCaseSensitive: true  // required — Whether the compare keys and strings mappings case sensitive or not
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationCoreAttributeRule>(json);
```


## Related Models

- [GroupReconciliationCoreComparisonRuleOperand](GroupReconciliationCoreComparisonRuleOperand.md)
- [GroupReconciliationCoreComparisonRuleOperand](GroupReconciliationCoreComparisonRuleOperand.md)
- [GroupReconciliationComparisonRuleStringValueMap](GroupReconciliationComparisonRuleStringValueMap.md) — used in `AllowableStringMappings`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

