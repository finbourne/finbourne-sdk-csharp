# Finbourne.Sdk.Lusid.Model.AggregateMatchingRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleName** | **string** | Required | The reference name of the rule. |
| **LeftFormula** | **string** | Required | Derivation formula evaluated against the left side of the reconciliation. |
| **LeftOperation** | **string** | Required | Group-level operation applied to the left side&#39;s per-item values during reconciliation, e.g. Sum, Average, Count. Available values: Sum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears. |
| **RightFormula** | **string** | Required | Derivation formula evaluated against the right side of the reconciliation. |
| **RightOperation** | **string** | Required | Group-level operation applied to the right side&#39;s per-item values during reconciliation, e.g. Sum, Average, Count. Available values: Sum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregateMatchingRule(
    ruleName: "...",  // required — The reference name of the rule.
    leftFormula: "...",  // required — Derivation formula evaluated against the left side of the reconciliation.
    leftOperation: "...",  // required — Group-level operation applied to the left side&#39;s per-item values during reconciliation, e.g. Sum, Average, Count. Available values: Sum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears.
    rightFormula: "...",  // required — Derivation formula evaluated against the right side of the reconciliation.
    rightOperation: "..."  // required — Group-level operation applied to the right side&#39;s per-item values during reconciliation, e.g. Sum, Average, Count. Available values: Sum, Proportion, Average, Count, Min, Max, Value, SumOfPositiveValues, SumOfNegativeValues, SumOfAbsoluteValues, ProportionOfAbsoluteValues, SumCumulativeInAdvance, SumCumulativeInArrears.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregateMatchingRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

