# Finbourne.Sdk.Horizon.Model.LusidEntity

Information about the LUSID entity this data can be used with
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityType** | **string** | Required | The entity type |
| **EntityTypeDisplayName** | **string** | Required | The display name for the entity type. |
| **EntitySubType** | **string** | Optional | The entity sub-type |
| **EntitySubTypeDisplayName** | **string** | Optional | Display name for the entity sub-type |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidEntity(
    entityType: "...",  // required — The entity type
    entityTypeDisplayName: "...",  // required — The display name for the entity type.
    entitySubType: "...",  // optional — The entity sub-type
    entitySubTypeDisplayName: "..."  // optional — Display name for the entity sub-type
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidEntity>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

