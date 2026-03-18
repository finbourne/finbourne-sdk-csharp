# Finbourne.Sdk.Lusid.Model.CheckDefinitionRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleKey** | **string** | Optional | The key of the Rule. |
| **DisplayName** | **string** | Optional | The name of the Rule. |
| **Description** | **string** | Optional | A description for the Rule. |
| **RuleFormula** | **string** | Optional | The formula for the rule. |
| **Severity** | **int** | Optional | Severity of the rule if formaula is not satisfied. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CheckDefinitionRule(
    ruleKey: "...",  // optional — The key of the Rule.
    displayName: "...",  // optional — The name of the Rule.
    description: "...",  // optional — A description for the Rule.
    ruleFormula: "...",  // optional — The formula for the rule.
    severity: 0  // optional — Severity of the rule if formaula is not satisfied.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CheckDefinitionRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

