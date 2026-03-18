# Finbourne.Sdk.Lusid.Model.DeletedEntityResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **EffectiveFrom** | **DateTimeOffset?** | Optional | The effective datetime at which the deletion became valid. May be null in the case where multiple date times are applicable. |
| **AsAt** | **DateTimeOffset** | Required | The asAt datetime at which the deletion was committed to LUSID. |
| **EntityType** | **string** | Optional | The type of the entity that the deleted response applies to. |
| **EntityUniqueId** | **string** | Optional | The unique Id of the entity that the deleted response applies to. |
| **StagedModifications** | [StagedModificationsInfo](StagedModificationsInfo.md) | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DeletedEntityResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    effectiveFrom: DateTimeOffset.Now,  // optional — The effective datetime at which the deletion became valid. May be null in the case where multiple date times are applicable.
    asAt: DateTimeOffset.Now,  // required — The asAt datetime at which the deletion was committed to LUSID.
    entityType: "...",  // optional — The type of the entity that the deleted response applies to.
    entityUniqueId: "...",  // optional — The unique Id of the entity that the deleted response applies to.
    stagedModifications: new StagedModificationsInfo(...),  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DeletedEntityResponse>(json);
```

- [StagedModificationsInfo](StagedModificationsInfo.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

