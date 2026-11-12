# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3Check

The limits a measure's result is checked against: an optional upper bound, an optional lower bound, and  the unit both are expressed in.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Unit** | **string** | Required | Available values: Absolute, Percentage. |
| **Upper** | [ComplianceRuleV3CheckBound](ComplianceRuleV3CheckBound.md) | Optional | *No description available.* |
| **Lower** | [ComplianceRuleV3CheckBound](ComplianceRuleV3CheckBound.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3Check(
    unit: "...",  // required — Available values: Absolute, Percentage.
    upper: new ComplianceRuleV3CheckBound(...),  // optional
    lower: new ComplianceRuleV3CheckBound(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3Check>(json);
```

- [ComplianceRuleV3CheckBound](ComplianceRuleV3CheckBound.md)
- [ComplianceRuleV3CheckBound](ComplianceRuleV3CheckBound.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

