# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3CheckBound

A single bound of a check: a hard limit that must hold, plus an optional soft limit that raises a  warning without failing the rule.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Hard** | [ComplianceRuleV3DecimalBound](ComplianceRuleV3DecimalBound.md) | Required | *No description available.* |
| **Soft** | [ComplianceRuleV3DecimalBound](ComplianceRuleV3DecimalBound.md) | Optional | *No description available.* |
| **HardProperty** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3CheckBound(
    hard: new ComplianceRuleV3DecimalBound(...),  // required
    soft: new ComplianceRuleV3DecimalBound(...),  // optional
    hardProperty: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3CheckBound>(json);
```


## Related Models

- [ComplianceRuleV3DecimalBound](ComplianceRuleV3DecimalBound.md)
- [ComplianceRuleV3DecimalBound](ComplianceRuleV3DecimalBound.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

