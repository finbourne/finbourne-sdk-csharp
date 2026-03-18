# Finbourne.Sdk.Lusid.Model.CustomEntityProperties

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Required | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **EntityType** | **string** | Required | The type of custom entity this is. |
| **Identifiers** | [List&lt;CustomEntityId&gt;](CustomEntityId.md) | Required | The identifiers the custom entity will be upserted with. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The properties that decorate the custom entity. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityProperties(
    href: "...",  // required — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    entityType: "...",  // required — The type of custom entity this is.
    identifiers: new List<CustomEntityId>(),  // required — The identifiers the custom entity will be upserted with.
    properties: new Property(...),  // optional — The properties that decorate the custom entity.
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
var instance = JsonConvert.DeserializeObject<CustomEntityProperties>(json);
```

- [CustomEntityId](CustomEntityId.md) — used in `Identifiers`
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

