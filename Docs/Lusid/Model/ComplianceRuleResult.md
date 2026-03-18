# Finbourne.Sdk.Lusid.Model.ComplianceRuleResult

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The unique identifierof a compliance rule |
| **RuleName** | **string** | Required | The User-given name of the rule |
| **RuleDescription** | **string** | Required | The User-given description of the rule |
| **Portfolio** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Passed** | **bool** | Required | The result of an individual compliance run, true if passed |
| **ResultValue** | **decimal** | Required | The calculation result that was used to confirm a pass/fail |
| **RuleInformationMatch** | **string** | Required | The value matched by the rule |
| **RuleInformationKey** | **string** | Required | The property key matched by the rule |
| **RuleLowerLimit** | **decimal** | Required | The lower limit of the rule |
| **RuleUpperLimit** | **decimal** | Required | The upper limit of the rule |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleResult(
    ruleId: "...",  // required — The unique identifierof a compliance rule
    ruleName: "...",  // required — The User-given name of the rule
    ruleDescription: "...",  // required — The User-given description of the rule
    portfolio: new ResourceId(...),  // required
    passed: true,  // required — The result of an individual compliance run, true if passed
    resultValue: 0.0d,  // required — The calculation result that was used to confirm a pass/fail
    ruleInformationMatch: "...",  // required — The value matched by the rule
    ruleInformationKey: "...",  // required — The property key matched by the rule
    ruleLowerLimit: 0.0d,  // required — The lower limit of the rule
    ruleUpperLimit: 0.0d  // required — The upper limit of the rule
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleResult>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

