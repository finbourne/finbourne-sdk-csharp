# Finbourne.Sdk.Lusid.Model.ComplianceRunV3Response

The outcome of a V3 compliance run: the result of each rule that was run.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleResults** | [List&lt;ComplianceRuleV3RuleResult&gt;](ComplianceRuleV3RuleResult.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRunV3Response(
    ruleResults: new List<ComplianceRuleV3RuleResult>(),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRunV3Response>(json);
```


## Related Models

- [ComplianceRuleV3RuleResult](ComplianceRuleV3RuleResult.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

