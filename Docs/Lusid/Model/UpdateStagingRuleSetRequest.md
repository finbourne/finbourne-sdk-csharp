# Finbourne.Sdk.Lusid.Model.UpdateStagingRuleSetRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the staging rule set. |
| **Description** | **string** | Optional | A description for the staging rule set. |
| **Rules** | [List&lt;StagingRule&gt;](StagingRule.md) | Required | The list of staging rules that apply to a specific entity type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateStagingRuleSetRequest(
    displayName: "...",  // required — The name of the staging rule set.
    description: "...",  // optional — A description for the staging rule set.
    rules: new List<StagingRule>()  // required — The list of staging rules that apply to a specific entity type.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateStagingRuleSetRequest>(json);
```

- [StagingRule](StagingRule.md) — used in `Rules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

