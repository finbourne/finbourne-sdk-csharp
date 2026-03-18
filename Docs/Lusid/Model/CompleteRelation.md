# Finbourne.Sdk.Lusid.Model.CompleteRelation

Representation of a relation containing details of source and target entities, and both outward and inward descriptions.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | *No description available.* |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **RelationDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **SourceEntityId** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **TargetEntityId** | **Dictionary&lt;string, string&gt;** | Required | *No description available.* |
| **OutwardDescription** | **string** | Required | *No description available.* |
| **InwardDescription** | **string** | Required | *No description available.* |
| **EffectiveFrom** | **DateTimeOffset** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CompleteRelation(
    href: "...",  // optional
    varVersion: new ModelVersion(...),  // optional
    relationDefinitionId: new ResourceId(...),  // required
    sourceEntityId: ,  // required
    targetEntityId: ,  // required
    outwardDescription: "...",  // required
    inwardDescription: "...",  // required
    effectiveFrom: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CompleteRelation>(json);
```

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

