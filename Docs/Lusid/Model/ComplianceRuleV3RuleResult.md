# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3RuleResult

The aggregate result of one rule across every group it was evaluated over: the rule's overall status  (its worst group outcome) and the per-group results partitioned by outcome.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Status** | **string** | Optional | Available values: Passed, Failed, Warning, MissingData. |
| **Results** | [List&lt;ComplianceRuleV3GroupResult&gt;](ComplianceRuleV3GroupResult.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3RuleResult(
    ruleId: new ResourceId(...),  // optional
    status: "...",  // optional — Available values: Passed, Failed, Warning, MissingData.
    results: new List<ComplianceRuleV3GroupResult>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3RuleResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ComplianceRuleV3GroupResult](ComplianceRuleV3GroupResult.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

