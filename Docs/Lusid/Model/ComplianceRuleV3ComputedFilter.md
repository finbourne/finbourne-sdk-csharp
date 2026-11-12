# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3ComputedFilter

An optional inner test selecting survivors before the measure: an optional grouping, the measure to  compute per group, and the check the group's measure must satisfy.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **GroupBy** | **List&lt;string&gt;** | Optional | *No description available.* |
| **Measure** | [ComplianceRuleV3Measure](ComplianceRuleV3Measure.md) | Required | *No description available.* |
| **Check** | [ComplianceRuleV3Check](ComplianceRuleV3Check.md) | Required | *No description available.* |
| **SelectOutsideBounds** | **bool** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3ComputedFilter(
    groupBy: ,  // optional
    measure: new ComplianceRuleV3Measure(...),  // required
    check: new ComplianceRuleV3Check(...),  // required
    selectOutsideBounds: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3ComputedFilter>(json);
```

- [ComplianceRuleV3Measure](ComplianceRuleV3Measure.md)
- [ComplianceRuleV3Check](ComplianceRuleV3Check.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

