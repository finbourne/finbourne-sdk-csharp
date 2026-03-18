# Finbourne.Sdk.Lusid.Model.StagingRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | **string** | Required | The ID of the staging rule. |
| **Description** | **string** | Optional | A description for the staging rule. |
| **Status** | **string** | Required | Whether the rule is &#39;Active&#39; or &#39;Inactive&#39;. |
| **MatchCriteria** | [StagingRuleMatchCriteria](StagingRuleMatchCriteria.md) | Required | *No description available.* |
| **ApprovalCriteria** | [StagingRuleApprovalCriteria](StagingRuleApprovalCriteria.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagingRule(
    ruleId: "...",  // required — The ID of the staging rule.
    description: "...",  // optional — A description for the staging rule.
    status: "...",  // required — Whether the rule is &#39;Active&#39; or &#39;Inactive&#39;.
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

