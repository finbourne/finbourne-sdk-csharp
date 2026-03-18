# Finbourne.Sdk.Lusid.Model.ReconciliationRule

Base class for representing reconciliation rules in LUSID.  Reconciliation rules describe how a comparison between two items in the reconciliation should be performed and what constitutes equality.  This does not influence WHAT constitutes a match, but only whether once a line has been matched whether an item within it matches another item.  If a rule is not given for an item, it will default to equality comparison.  This base class should not be directly instantiated; each supported ReconciliationRuleType has a corresponding inherited class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleType** | **string** | Required | The available values are: ReconcileNumericRule, ReconcileDateTimeRule, ReconcileStringRule, ReconcileExact |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconciliationRule(
    ruleType: "..."  // required — The available values are: ReconcileNumericRule, ReconcileDateTimeRule, ReconcileStringRule, ReconcileExact
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReconciliationRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

