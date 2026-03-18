# Finbourne.Sdk.Lusid.Model.ReconcileStringRule

Comparison of string values
> **Inherits from:** [ReconciliationRule](ReconciliationRule.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComparisonType** | **string** | Required | The available values are: Exact, Contains, CaseInsensitive, ContainsAnyCase, IsOneOf, IsOneOfCaseInsensitive |
| **OneOfCandidates** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | Optional | For cases of \&quot;IsOneOf\&quot; or \&quot;IsOneOfCaseInsensitive\&quot;, a mapping from the left hand to side to lists of  equivalent alternative values on the right hand side.  Fuzzy matching of strings against one of a set. There can be cases where systems \&quot;A\&quot; and \&quot;B\&quot; might use different terms for the same logical entity. A common case would be  comparison of something like a day count fraction where some convention like the \&quot;actual 365\&quot; convention might be represented as one of [\&quot;A365\&quot;, \&quot;Act365\&quot;, \&quot;Actual365\&quot;] or similar.  This is to allow this kind of fuzzy matching of values. Note that as this is exhaustive comparison across sets it will be slow and should therefore be used sparingly. |
| **AppliesTo** | [AggregateSpec](AggregateSpec.md) | Required | *No description available.* |
| **RuleType** | **string** | Required | The available values are: ReconcileNumericRule, ReconcileDateTimeRule, ReconcileStringRule, ReconcileExact Default: `RuleTypeEnum.ReconcileStringRule` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReconcileStringRule(
    comparisonType: "...",  // required — The available values are: Exact, Contains, CaseInsensitive, ContainsAnyCase, IsOneOf, IsOneOfCaseInsensitive
    oneOfCandidates: ,  // optional — For cases of \&quot;IsOneOf\&quot; or \&quot;IsOneOfCaseInsensitive\&quot;, a mapping from the left hand to side to lists of  equivalent alternative values on the right hand side.  Fuzzy matching of strings against one of a set. There can be cases where systems \&quot;A\&quot; and \&quot;B\&quot; might use different terms for the same logical entity. A common case would be  comparison of something like a day count fraction where some convention like the \&quot;actual 365\&quot; convention might be represented as one of [\&quot;A365\&quot;, \&quot;Act365\&quot;, \&quot;Actual365\&quot;] or similar.  This is to allow this kind of fuzzy matching of values. Note that as this is exhaustive comparison across sets it will be slow and should therefore be used sparingly.
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
var instance = JsonConvert.DeserializeObject<ReconcileStringRule>(json);
```


- [AggregateSpec](AggregateSpec.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

