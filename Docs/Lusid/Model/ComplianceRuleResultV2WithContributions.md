# Finbourne.Sdk.Lusid.Model.ComplianceRuleResultV2WithContributions

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstigatedAt** | **DateTimeOffset** | Required | *No description available.* |
| **CompletedAt** | **DateTimeOffset** | Required | *No description available.* |
| **Schedule** | **string** | Required | Available values: PreTrade, PostTrade, PreAndPostTrade. |
| **RuleResult** | [ComplianceSummaryRuleResultWithContributions](ComplianceSummaryRuleResultWithContributions.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleResultV2WithContributions(
    runId: new ResourceId(...),  // required
    instigatedAt: DateTimeOffset.Now,  // required
    completedAt: DateTimeOffset.Now,  // required
    schedule: "...",  // required — Available values: PreTrade, PostTrade, PreAndPostTrade.
    ruleResult: new ComplianceSummaryRuleResultWithContributions(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleResultV2WithContributions>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceSummaryRuleResultWithContributions](ComplianceSummaryRuleResultWithContributions.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

