# Finbourne.Sdk.Lusid.Model.ComplianceRuleTemplate

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Description** | **string** | Optional | The description of the Compliance Template |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | Properties associated with the Compliance Template Variation |
| **Variations** | [List&lt;ComplianceTemplateVariationDto&gt;](ComplianceTemplateVariationDto.md) | Optional | Variation details of a Compliance Template |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRuleTemplate(
    id: new ResourceId(...),  // optional
    description: "...",  // optional — The description of the Compliance Template
    properties: new Property(...),  // optional — Properties associated with the Compliance Template Variation
    variations: new List<ComplianceTemplateVariationDto>(),  // optional — Variation details of a Compliance Template
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested asAt datetime.
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
var instance = JsonConvert.DeserializeObject<ComplianceRuleTemplate>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [Property](Property.md) — used in `Properties`
- [ComplianceTemplateVariationDto](ComplianceTemplateVariationDto.md) — used in `Variations`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

