# Finbourne.Sdk.Lusid.Model.CustomEntityType

Representation of a Custom Entity Type on the LUSID API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **EntityTypeName** | **string** | Required | The name provided when the custom entity type was created. This has been prefixed with “~” and returned as “entityType”, which is the identifier for the custom entity type. |
| **DisplayName** | **string** | Required | A display label for the custom entity type. |
| **Description** | **string** | Optional | A description for the custom entity type. |
| **EntityType** | **string** | Required | The identifier for the custom entity type, derived from the “entityTypeName” provided on creation. |
| **FieldSchema** | [List&lt;CustomEntityFieldDefinition&gt;](CustomEntityFieldDefinition.md) | Required | The description of the fields on the custom entity type. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityType(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    entityTypeName: "...",  // required — The name provided when the custom entity type was created. This has been prefixed with “~” and returned as “entityType”, which is the identifier for the custom entity type.
    displayName: "...",  // required — A display label for the custom entity type.
    description: "...",  // optional — A description for the custom entity type.
    entityType: "...",  // required — The identifier for the custom entity type, derived from the “entityTypeName” provided on creation.
    fieldSchema: new List<CustomEntityFieldDefinition>(),  // required — The description of the fields on the custom entity type.
    varVersion: new ModelVersion(...),  // required
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityType>(json);
```

- [CustomEntityFieldDefinition](CustomEntityFieldDefinition.md) — used in `FieldSchema`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

