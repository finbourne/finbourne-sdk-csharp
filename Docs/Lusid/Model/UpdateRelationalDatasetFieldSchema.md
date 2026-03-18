# Finbourne.Sdk.Lusid.Model.UpdateRelationalDatasetFieldSchema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Add** | [RelationalDatasetFieldsToAdd](RelationalDatasetFieldsToAdd.md) | Optional | *No description available.* |
| **Update** | [RelationalDatasetFieldsToUpdate](RelationalDatasetFieldsToUpdate.md) | Optional | *No description available.* |
| **Remove** | [RelationalDatasetFieldsToRemove](RelationalDatasetFieldsToRemove.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateRelationalDatasetFieldSchema(
    add: new RelationalDatasetFieldsToAdd(...),  // optional
    update: new RelationalDatasetFieldsToUpdate(...),  // optional
    remove: new RelationalDatasetFieldsToRemove(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateRelationalDatasetFieldSchema>(json);
```


## Related Models

- [RelationalDatasetFieldsToAdd](RelationalDatasetFieldsToAdd.md)
- [RelationalDatasetFieldsToUpdate](RelationalDatasetFieldsToUpdate.md)
- [RelationalDatasetFieldsToRemove](RelationalDatasetFieldsToRemove.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

