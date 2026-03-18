# Finbourne.Sdk.Lusid.Model.CustomEntityResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **EntityType** | **string** | Required | The type of custom entity this is. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **DisplayName** | **string** | Required | A display label for the custom entity. |
| **Description** | **string** | Optional | A description of the custom entity. |
| **Identifiers** | [List&lt;CustomEntityId&gt;](CustomEntityId.md) | Required | The identifiers the custom entity will be upserted with. |
| **Fields** | [List&lt;CustomEntityField&gt;](CustomEntityField.md) | Required | The fields that decorate the custom entity. |
| **Relationships** | [List&lt;Relationship&gt;](Relationship.md) | Required | A set of relationships associated to the custom entity. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties that decorate the custom entity. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    entityType: "...",  // required — The type of custom entity this is.
    varVersion: new ModelVersion(...),  // required
    stagedModifications: new StagedModificationsInfo(...),  // optional
    displayName: "...",  // required — A display label for the custom entity.
    description: "...",  // optional — A description of the custom entity.
    identifiers: new List<CustomEntityId>(),  // required — The identifiers the custom entity will be upserted with.
    fields: new List<CustomEntityField>(),  // required — The fields that decorate the custom entity.
    relationships: new List<Relationship>(),  // required — A set of relationships associated to the custom entity.
    properties: new Property(...),  // optional — The properties that decorate the custom entity.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityResponse>(json);
```

- [ModelVersion](ModelVersion.md)
- [StagedModificationsInfo](StagedModificationsInfo.md)
- [CustomEntityId](CustomEntityId.md) — used in `Identifiers`
- [CustomEntityField](CustomEntityField.md) — used in `Fields`
- [Relationship](Relationship.md) — used in `Relationships`
- [Property](Property.md) — used in `Properties`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

