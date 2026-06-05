# Finbourne.Sdk.Lusid.Model.UpdateMarketDataFieldConfigurationRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Add** | [MetadataFieldsToAdd](MetadataFieldsToAdd.md) | Optional | *No description available.* |
| **Update** | [MetadataFieldsToUpdate](MetadataFieldsToUpdate.md) | Optional | *No description available.* |
| **Remove** | [MetadataFieldsToRemove](MetadataFieldsToRemove.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateMarketDataFieldConfigurationRequest(
    add: new MetadataFieldsToAdd(...),  // optional
    update: new MetadataFieldsToUpdate(...),  // optional
    remove: new MetadataFieldsToRemove(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateMarketDataFieldConfigurationRequest>(json);
```


## Related Models

- [MetadataFieldsToAdd](MetadataFieldsToAdd.md)
- [MetadataFieldsToUpdate](MetadataFieldsToUpdate.md)
- [MetadataFieldsToRemove](MetadataFieldsToRemove.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

