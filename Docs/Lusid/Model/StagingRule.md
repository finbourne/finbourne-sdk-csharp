# Finbourne.Sdk.Lusid.Model.StagingRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The ID of the staging rule. |
| **Description** | **string** | Optional | A description for the staging rule. |
| **Status** | **string** | Required | Status of the rule. Available values: Active, Inactive. |
| **MatchCriteria** | [StagingRuleMatchCriteria](StagingRuleMatchCriteria.md) | Required | *No description available.* |
| **ApprovalCriteria** | [StagingRuleApprovalCriteria](StagingRuleApprovalCriteria.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagingRule(
    ruleId: "...",  // required — The ID of the staging rule.
    description: "...",  // optional — A description for the staging rule.
    status: "...",  // required — Status of the rule. Available values: Active, Inactive.
    matchCriteria: new StagingRuleMatchCriteria(...),  // required
    approvalCriteria: new StagingRuleApprovalCriteria(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagingRule>(json);
```

- [StagingRuleMatchCriteria](StagingRuleMatchCriteria.md)
- [StagingRuleApprovalCriteria](StagingRuleApprovalCriteria.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

