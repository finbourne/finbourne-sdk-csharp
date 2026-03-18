# Finbourne.Sdk.Lusid.Model.UpsertDataQualityRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleSetKey** | **string** | Optional | *No description available.* |
| **Rule** | [CheckDefinitionRule](CheckDefinitionRule.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertDataQualityRule(
    ruleSetKey: "...",  // optional
    rule: new CheckDefinitionRule(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertDataQualityRule>(json);
```

- [CheckDefinitionRule](CheckDefinitionRule.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

