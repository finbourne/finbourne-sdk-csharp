# Finbourne.Sdk.Lusid.Model.EntityResolver

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **EntityType** | **string** | Required | The entity type that a specific resolution configuration is applicable to (e.g. Instrument). |
| **Description** | **string** | Optional | Describes what this specific identifier order is used for. |
| **IdentifierMatchingOrder** | [List&lt;IdentifierForResolution&gt;](IdentifierForResolution.md) | Required | Ordered collection of related identifier keys that are used to define which identifier takes priority in resolving an entity. |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EntityResolver(
    id: new ResourceId(...),  // required
    entityType: "...",  // required — The entity type that a specific resolution configuration is applicable to (e.g. Instrument).
    description: "...",  // optional — Describes what this specific identifier order is used for.
    identifierMatchingOrder: new List<IdentifierForResolution>(),  // required — Ordered collection of related identifier keys that are used to define which identifier takes priority in resolving an entity.
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
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
var instance = JsonConvert.DeserializeObject<EntityResolver>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [IdentifierForResolution](IdentifierForResolution.md) — used in `IdentifierMatchingOrder`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

