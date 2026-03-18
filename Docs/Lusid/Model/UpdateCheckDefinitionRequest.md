# Finbourne.Sdk.Lusid.Model.UpdateCheckDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the Check Definition. |
| **Description** | **string** | Required | A description for the Check Definition. |
| **DatasetSchema** | [CheckDefinitionDatasetSchema](CheckDefinitionDatasetSchema.md) | Optional | *No description available.* |
| **RuleSets** | [List&lt;UpdateCheckDefinitionRuleSet&gt;](UpdateCheckDefinitionRuleSet.md) | Required | A collection of rule sets for the Check Definition. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Check Definition. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateCheckDefinitionRequest(
    displayName: "...",  // required — The name of the Check Definition.
    description: "...",  // required — A description for the Check Definition.
    datasetSchema: new CheckDefinitionDatasetSchema(...),  // optional
    ruleSets: new List<UpdateCheckDefinitionRuleSet>(),  // required — A collection of rule sets for the Check Definition.
    properties: new Property(...)  // optional — A set of properties for the Check Definition.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateCheckDefinitionRequest>(json);
```

- [CheckDefinitionDatasetSchema](CheckDefinitionDatasetSchema.md)
- [UpdateCheckDefinitionRuleSet](UpdateCheckDefinitionRuleSet.md) — used in `RuleSets`
- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

