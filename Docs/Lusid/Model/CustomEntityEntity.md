# Finbourne.Sdk.Lusid.Model.CustomEntityEntity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Required | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **EntityUniqueId** | **string** | Required | The unique id of the entity. |
| **AsAtVersionNumber** | **int?** | Optional | The integer version number for the entity (the entity was created at version 1) |
| **Status** | **string** | Required | The status of the entity at the current time. |
| **AsAtDeleted** | **DateTimeOffset?** | Optional | The asAt datetime at which the entity was deleted. |
| **UserIdDeleted** | **string** | Optional | The unique id of the user who deleted the entity. |
| **RequestIdDeleted** | **string** | Optional | The unique request id of the command that deleted the entity. |
| **EffectiveAtCreated** | **DateTimeOffset?** | Optional | The EffectiveAt this Entity is created, if entity does not currently exist in EffectiveAt. |
| **PrevailingCustomEntity** | [CustomEntityResponse](CustomEntityResponse.md) | Optional | *No description available.* |
| **DeletedCustomEntity** | [CustomEntityResponse](CustomEntityResponse.md) | Optional | *No description available.* |
| **PreviewedStatus** | **string** | Optional | The status of the previewed entity. |
| **PreviewedCustomEntity** | [CustomEntityResponse](CustomEntityResponse.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityEntity(
    href: "...",  // required — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    entityUniqueId: "...",  // required — The unique id of the entity.
    asAtVersionNumber: 0,  // optional — The integer version number for the entity (the entity was created at version 1)
    status: "...",  // required — The status of the entity at the current time.
    asAtDeleted: DateTimeOffset.Now,  // optional — The asAt datetime at which the entity was deleted.
    userIdDeleted: "...",  // optional — The unique id of the user who deleted the entity.
    requestIdDeleted: "...",  // optional — The unique request id of the command that deleted the entity.
    effectiveAtCreated: DateTimeOffset.Now,  // optional — The EffectiveAt this Entity is created, if entity does not currently exist in EffectiveAt.
    prevailingCustomEntity: new CustomEntityResponse(...),  // optional
    deletedCustomEntity: new CustomEntityResponse(...),  // optional
    previewedStatus: "...",  // optional — The status of the previewed entity.
    previewedCustomEntity: new CustomEntityResponse(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityEntity>(json);
```

- [CustomEntityResponse](CustomEntityResponse.md)
- [CustomEntityResponse](CustomEntityResponse.md)
- [CustomEntityResponse](CustomEntityResponse.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

