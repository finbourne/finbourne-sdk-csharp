# Finbourne.Sdk.Lusid.Model.CompleteRelationship

Representation of a relationship containing details of source and target entities, and both outward and inward descriptions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **RelationshipDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SourceEntity** | [RelatedEntity](RelatedEntity.md) | Required | *No description available.* |
| **TargetEntity** | [RelatedEntity](RelatedEntity.md) | Required | *No description available.* |
| **OutwardDescription** | **string** | Required | Description of the relationship based on relationship definition&#39;s outward description. |
| **InwardDescription** | **string** | Required | Description of the relationship based on relationship definition&#39;s inward description. |
| **EffectiveFrom** | **DateTimeOffset** | Optional | The effective datetime from which the relationship is valid. |
| **EffectiveUntil** | **DateTimeOffset** | Optional | The effective datetime to which the relationship is valid until. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CompleteRelationship(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    varVersion: new ModelVersion(...),  // optional
    relationshipDefinitionId: new ResourceId(...),  // required
    sourceEntity: new RelatedEntity(...),  // required
    targetEntity: new RelatedEntity(...),  // required
    outwardDescription: "...",  // required — Description of the relationship based on relationship definition&#39;s outward description.
    inwardDescription: "...",  // required — Description of the relationship based on relationship definition&#39;s inward description.
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime from which the relationship is valid.
    effectiveUntil: DateTimeOffset.Now  // optional — The effective datetime to which the relationship is valid until.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CompleteRelationship>(json);
```

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)
- [RelatedEntity](RelatedEntity.md)
- [RelatedEntity](RelatedEntity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

