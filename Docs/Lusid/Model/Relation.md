# Finbourne.Sdk.Lusid.Model.Relation

Representation of a Relation between a requested entity with the stated entity as RelationedEntityId
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **RelationDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **RelatedEntityId** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **TraversalDirection** | **string** | Required | *No description available.* |
| **TraversalDescription** | **string** | Required | *No description available.* |
| **EffectiveFrom** | **DateTimeOffset** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Relation(
    varVersion: new ModelVersion(...),  // optional
    relationDefinitionId: new ResourceId(...),  // required
    relatedEntityId: ,  // required
    traversalDirection: "...",  // required
    traversalDescription: "...",  // required
    effectiveFrom: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Relation>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

