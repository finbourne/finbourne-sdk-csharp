# Finbourne.Sdk.Lusid.Model.CoreRuleValues

A core matching rule and the values that pin a rec result to its reconciled position. These values  contribute to the result id.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleName** | **string** | Required | The name of the rule. |
| **LeftValue** | **string** | Optional | The left-side value. |
| **RightValue** | **string** | Optional | The right-side value. |
| **AppliedTolerance** | [ToleranceBase](ToleranceBase.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CoreRuleValues(
    ruleName: "...",  // required — The name of the rule.
    leftValue: "...",  // optional — The left-side value.
    rightValue: "...",  // optional — The right-side value.
    appliedTolerance: new ToleranceBase(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CoreRuleValues>(json);
```

- [ToleranceBase](ToleranceBase.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

