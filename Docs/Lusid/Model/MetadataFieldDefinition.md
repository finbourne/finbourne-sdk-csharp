# Finbourne.Sdk.Lusid.Model.MetadataFieldDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The unique identifier for the metadata field. |
| **DisplayName** | **string** | Optional | A user-friendly display name for the metadata field. |
| **Description** | **string** | Optional | A detailed description of the metadata field and its purpose. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new MetadataFieldDefinition(
    fieldName: "...",  // required — The unique identifier for the metadata field.
    displayName: "...",  // optional — A user-friendly display name for the metadata field.
    description: "...",  // optional — A detailed description of the metadata field and its purpose.
    dataTypeId: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<MetadataFieldDefinition>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

