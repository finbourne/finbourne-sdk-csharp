# Finbourne.Sdk.Lusid.Model.Relationship

Representation of a Relationship between a requested entity with the stated entity as RelatedEntityId
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **RelationshipDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RelatedEntity** | [RelatedEntity](RelatedEntity.md) | Required | *No description available.* |
| **TraversalDirection** | **string** | Required | Direction of relationship between the requested entity and related entity. This can be &#39;In&#39; or &#39;Out&#39;. Read more about relationships traversal direction in LUSID Knowledge Base here https://support.lusid.com/knowledgebase/article/KA-01679. |
| **TraversalDescription** | **string** | Required | Description of the relationship based on relationship&#39;s traversal direction. If &#39;TraversalDirection&#39; is &#39;Out&#39;, this description would be &#39;OutwardDescription&#39; from the associated relationship definition. If &#39;TraversalDirection&#39; is &#39;In&#39;, this description would be &#39;InwardDescription&#39; from the associated relationship definition. |
| **EffectiveFrom** | **DateTimeOffset** | Optional | The effective datetime from which the relationship is valid. |
| **EffectiveUntil** | **DateTimeOffset** | Optional | The effective datetime until which the relationship is valid. If no future deletions are present or an effective until has not been set for the relationship, this will be indefinite and represented by the maximum date. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Relationship(
    varVersion: new ModelVersion(...),  // optional
    relationshipDefinitionId: new ResourceId(...),  // required
    relatedEntity: new RelatedEntity(...),  // required
    traversalDirection: "...",  // required — Direction of relationship between the requested entity and related entity. This can be &#39;In&#39; or &#39;Out&#39;. Read more about relationships traversal direction in LUSID Knowledge Base here https://support.lusid.com/knowledgebase/article/KA-01679.
    traversalDescription: "...",  // required — Description of the relationship based on relationship&#39;s traversal direction. If &#39;TraversalDirection&#39; is &#39;Out&#39;, this description would be &#39;OutwardDescription&#39; from the associated relationship definition. If &#39;TraversalDirection&#39; is &#39;In&#39;, this description would be &#39;InwardDescription&#39; from the associated relationship definition.
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime from which the relationship is valid.
    effectiveUntil: DateTimeOffset.Now  // optional — The effective datetime until which the relationship is valid. If no future deletions are present or an effective until has not been set for the relationship, this will be indefinite and represented by the maximum date.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Relationship>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)
- [RelatedEntity](RelatedEntity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

