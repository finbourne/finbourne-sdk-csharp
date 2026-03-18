# Finbourne.Sdk.Lusid.Model.UpdateCheckDefinitionRuleSet

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RuleSetKey** | **string** | Optional | The Key of the Rule Set. |
| **DisplayName** | **string** | Optional | The name of the Rule Set. |
| **Description** | **string** | Optional | A description for the Rule Set. |
| **RuleSetFilter** | **string** | Optional | A filter for the Rule Set to filter entity instances the rule set applies to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateCheckDefinitionRuleSet(
    ruleSetKey: "...",  // optional — The Key of the Rule Set.
    displayName: "...",  // optional — The name of the Rule Set.
    description: "...",  // optional — A description for the Rule Set.
    ruleSetFilter: "..."  // optional — A filter for the Rule Set to filter entity instances the rule set applies to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateCheckDefinitionRuleSet>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

