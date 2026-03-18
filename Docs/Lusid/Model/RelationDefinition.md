# Finbourne.Sdk.Lusid.Model.RelationDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **RelationDefinitionId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **SourceEntityDomain** | **string** | Optional | The entity domain of the source entity object. |
| **TargetEntityDomain** | **string** | Optional | The entity domain of the target entity object. |
| **DisplayName** | **string** | Optional | The display name of the relation. |
| **OutwardDescription** | **string** | Optional | The description to relate source entity object and target entity object |
| **InwardDescription** | **string** | Optional | The description to relate target entity object and source entity object |
| **LifeTime** | **string** | Optional | Describes how the relations can change over time, allowed values are \&quot;Perpetual\&quot; and \&quot;TimeVariant\&quot; |
| **ConstraintStyle** | **string** | Optional | Describes the uniqueness and cardinality for relations with a specific source entity object and relations under this definition. Allowed values are \&quot;Property\&quot; and \&quot;Collection\&quot;, defaults to \&quot;Collection\&quot; if not specified. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationDefinition(
    varVersion: new ModelVersion(...),  // optional
    relationDefinitionId: new ResourceId(...),  // optional
    sourceEntityDomain: "...",  // optional — The entity domain of the source entity object.
    targetEntityDomain: "...",  // optional — The entity domain of the target entity object.
    displayName: "...",  // optional — The display name of the relation.
    outwardDescription: "...",  // optional — The description to relate source entity object and target entity object
    inwardDescription: "...",  // optional — The description to relate target entity object and source entity object
    lifeTime: "...",  // optional — Describes how the relations can change over time, allowed values are \&quot;Perpetual\&quot; and \&quot;TimeVariant\&quot;
    constraintStyle: "...",  // optional — Describes the uniqueness and cardinality for relations with a specific source entity object and relations under this definition. Allowed values are \&quot;Property\&quot; and \&quot;Collection\&quot;, defaults to \&quot;Collection\&quot; if not specified.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationDefinition>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

