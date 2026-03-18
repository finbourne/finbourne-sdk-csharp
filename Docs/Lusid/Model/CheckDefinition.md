# Finbourne.Sdk.Lusid.Model.CheckDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Optional | The name of the Check Definition. |
| **Description** | **string** | Optional | A description for the Check Definition. |
| **DatasetSchema** | [CheckDefinitionDatasetSchema](CheckDefinitionDatasetSchema.md) | Optional | *No description available.* |
| **RuleSets** | [List&lt;CheckDefinitionRuleSet&gt;](CheckDefinitionRuleSet.md) | Optional | A collection of rule sets for the Check Definition. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the Check Definition. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CheckDefinition(
    id: new ResourceId(...),  // required
    displayName: "...",  // optional — The name of the Check Definition.
    description: "...",  // optional — A description for the Check Definition.
    datasetSchema: new CheckDefinitionDatasetSchema(...),  // optional
    ruleSets: new List<CheckDefinitionRuleSet>(),  // optional — A collection of rule sets for the Check Definition.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    properties: new Property(...),  // optional — A set of properties for the Check Definition.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CheckDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [CheckDefinitionDatasetSchema](CheckDefinitionDatasetSchema.md)
- [CheckDefinitionRuleSet](CheckDefinitionRuleSet.md) — used in `RuleSets`
- [ModelVersion](ModelVersion.md)
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

