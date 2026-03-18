# Finbourne.Sdk.Lusid.Model.RelationshipDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **RelationshipDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SourceEntityType** | **string** | Required | The entity type of the source entity object. |
| **TargetEntityType** | **string** | Required | The entity type of the target entity object. |
| **DisplayName** | **string** | Required | The display name of the relationship. |
| **OutwardDescription** | **string** | Required | The description to relate source entity object and target entity object |
| **InwardDescription** | **string** | Required | The description to relate target entity object and source entity object |
| **LifeTime** | **string** | Required | Describes how the relationships can change over time. |
| **RelationshipCardinality** | **string** | Required | Describes the cardinality of the relationship between source entity and target entity. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationshipDefinition(
    varVersion: new ModelVersion(...),  // optional
    relationshipDefinitionId: new ResourceId(...),  // required
    sourceEntityType: "...",  // required — The entity type of the source entity object.
    targetEntityType: "...",  // required — The entity type of the target entity object.
    displayName: "...",  // required — The display name of the relationship.
    outwardDescription: "...",  // required — The description to relate source entity object and target entity object
    inwardDescription: "...",  // required — The description to relate target entity object and source entity object
    lifeTime: "...",  // required — Describes how the relationships can change over time.
    relationshipCardinality: "...",  // required — Describes the cardinality of the relationship between source entity and target entity.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationshipDefinition>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

