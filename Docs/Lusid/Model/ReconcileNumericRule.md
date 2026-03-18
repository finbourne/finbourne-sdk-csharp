# Finbourne.Sdk.Lusid.Model.ReconcileNumericRule

> **Inherits from:** [ReconciliationRule](ReconciliationRule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComparisonType** | **string** | Required | The available values are: Exact, AbsoluteDifference, RelativeDifference |
| **Tolerance** | **decimal** | Optional | For a numeric type only (i.e. decimal, integer, date or datetime offset possibly controversially), this is the quantity used in the comparison.  The units of the tolerance must be set appropriately for the item being compared.  For a number such as a currency or amount that will be a simple quantity, for a DateTime or DateTimeOffset it should be days. If fewer than a single day then this should be  passed as a fraction. |
| **AppliesTo** | [AggregateSpec](AggregateSpec.md) | Required | *No description available.* |
| **RuleType** | **string** | Required | The available values are: ReconcileNumericRule, ReconcileDateTimeRule, ReconcileStringRule, ReconcileExact Default: `RuleTypeEnum.ReconcileNumericRule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconcileNumericRule(
    comparisonType: "...",  // required — The available values are: Exact, AbsoluteDifference, RelativeDifference
    tolerance: 0.0d,  // optional — For a numeric type only (i.e. decimal, integer, date or datetime offset possibly controversially), this is the quantity used in the comparison.  The units of the tolerance must be set appropriately for the item being compared.  For a number such as a currency or amount that will be a simple quantity, for a DateTime or DateTimeOffset it should be days. If fewer than a single day then this should be  passed as a fraction.
    appliesTo: new AggregateSpec(...),  // required
    ruleType: "..."  // required — The available values are: ReconcileNumericRule, ReconcileDateTimeRule, ReconcileStringRule, ReconcileExact
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconcileNumericRule>(json);
```


- [AggregateSpec](AggregateSpec.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

