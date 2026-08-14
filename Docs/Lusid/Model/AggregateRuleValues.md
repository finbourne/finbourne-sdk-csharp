# Finbourne.Sdk.Lusid.Model.AggregateRuleValues

An aggregate matching rule and its values. The difference is the measured magnitude compared against  any applied tolerance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleName** | **string** | Required | The name of the rule. |
| **LeftValue** | **string** | Optional | The left-side value. |
| **RightValue** | **string** | Optional | The right-side value. |
| **Difference** | **string** | Required | The measured magnitude of the difference, ToString(ABS(leftValue - rightValue)). |
| **AppliedTolerance** | [AggregateToleranceBase](AggregateToleranceBase.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AggregateRuleValues(
    ruleName: "...",  // required — The name of the rule.
    leftValue: "...",  // optional — The left-side value.
    rightValue: "...",  // optional — The right-side value.
    difference: "...",  // required — The measured magnitude of the difference, ToString(ABS(leftValue - rightValue)).
    appliedTolerance: new AggregateToleranceBase(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AggregateRuleValues>(json);
```

- [AggregateToleranceBase](AggregateToleranceBase.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

