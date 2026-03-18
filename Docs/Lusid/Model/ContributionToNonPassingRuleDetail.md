# Finbourne.Sdk.Lusid.Model.ContributionToNonPassingRuleDetail

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **RuleStatus** | **string** | Optional | The status of the non-passing rule. |
| **BreachTaskIds** | **List&lt;string&gt;** | Optional | The task ids associated with the compliance breach for this order&#39;s groups (if failing). |
| **LikelyResponsibleForStatus** | **bool** | Optional | Whether this order is deemed as a likely contributor to the non-passing rule for this group. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ContributionToNonPassingRuleDetail(
    ruleId: new ResourceId(...),  // optional
    ruleStatus: "...",  // optional — The status of the non-passing rule.
    breachTaskIds: ,  // optional — The task ids associated with the compliance breach for this order&#39;s groups (if failing).
    likelyResponsibleForStatus: true  // optional — Whether this order is deemed as a likely contributor to the non-passing rule for this group.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ContributionToNonPassingRuleDetail>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

