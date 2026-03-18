# Finbourne.Sdk.Lusid.Model.StagedModificationStagingRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StagingRuleSetId** | **string** | Optional | System generated unique id for the staging rule set. |
| **RuleId** | **string** | Optional | The ID of the staging rule. |
| **RequiredApprovals** | **int** | Optional | The number of approvals required. If left blank, one approval is needed. |
| **CurrentUserCanDecide** | **bool** | Optional | True or False indicating whether the current user can make a decision on the staged modification. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationStagingRule(
    stagingRuleSetId: "...",  // optional — System generated unique id for the staging rule set.
    ruleId: "...",  // optional — The ID of the staging rule.
    requiredApprovals: 0,  // optional — The number of approvals required. If left blank, one approval is needed.
    currentUserCanDecide: true  // optional — True or False indicating whether the current user can make a decision on the staged modification.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationStagingRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

