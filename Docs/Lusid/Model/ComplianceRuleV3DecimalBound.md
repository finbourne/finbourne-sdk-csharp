# Finbourne.Sdk.Lusid.Model.ComplianceRuleV3DecimalBound

A check bound value paired with whether a value landing exactly on it satisfies the check.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **decimal** | Required | *No description available.* |
| **Inclusive** | **bool** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleV3DecimalBound(
    value: 0.0d,  // required
    inclusive: true  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleV3DecimalBound>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

