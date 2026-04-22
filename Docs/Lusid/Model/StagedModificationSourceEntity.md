# Finbourne.Sdk.Lusid.Model.StagedModificationSourceEntity

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Optional | The type of the source entity. |
| **Scope** | **string** | Optional | The scope of the source entity. |
| **EntityUniqueId** | **string** | Optional | The unique Id of the source entity. |
| **DisplayName** | **string** | Optional | The display name of the source entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationSourceEntity(
    entityType: "...",  // optional — The type of the source entity.
    scope: "...",  // optional — The scope of the source entity.
    entityUniqueId: "...",  // optional — The unique Id of the source entity.
    displayName: "..."  // optional — The display name of the source entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationSourceEntity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

