# Finbourne.Sdk.Lusid.Model.ComplianceRuleResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Name** | **string** | Optional | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Active** | **bool** | Optional | *No description available.* |
| **TemplateId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Variation** | **string** | Optional | *No description available.* |
| **PortfolioGroupId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Parameters** | [Dictionary&lt;string, ComplianceParameter&gt;](ComplianceParameter.md) | Optional | *No description available.* |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleResponse(
    id: new ResourceId(...),  // optional
    name: "...",  // optional
    description: "...",  // optional
    active: true,  // optional
    templateId: new ResourceId(...),  // optional
    variation: "...",  // optional
    portfolioGroupId: new ResourceId(...),  // optional
    parameters: new ComplianceParameter(...),  // optional
    properties: new PerpetualProperty(...),  // optional
    varVersion: new ModelVersion(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRuleResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [ComplianceParameter](ComplianceParameter.md)
- [PerpetualProperty](PerpetualProperty.md)
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

