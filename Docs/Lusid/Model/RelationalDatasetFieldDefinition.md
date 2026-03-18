# Finbourne.Sdk.Lusid.Model.RelationalDatasetFieldDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The unique identifier for the field within the dataset. |
| **DisplayName** | **string** | Optional | A user-friendly display name for the field. |
| **Description** | **string** | Optional | A detailed description of the field and its purpose. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Required** | **bool** | Optional | Whether this field is mandatory in the dataset. |
| **Category** | **string** | Required | The intended category of the field (SeriesIdentifier, Value, or Metadata). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelationalDatasetFieldDefinition(
    fieldName: "...",  // required — The unique identifier for the field within the dataset.
    displayName: "...",  // optional — A user-friendly display name for the field.
    description: "...",  // optional — A detailed description of the field and its purpose.
    dataTypeId: new ResourceId(...),  // required
    required: true,  // optional — Whether this field is mandatory in the dataset.
    category: "..."  // required — The intended category of the field (SeriesIdentifier, Value, or Metadata).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelationalDatasetFieldDefinition>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

