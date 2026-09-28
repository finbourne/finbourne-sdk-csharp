# Finbourne.Sdk.Lusid.Model.SeriesIdentifierField

A series identifier field, carrying the same fields as the CreateSeriesIdentifierField that asks for one, so  that a caller reads back what they wrote. The field category is not among them, because every field of this  shape is a series identifier; nor is a required flag, which is not the caller's to set.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The unique identifier for the field within the dataset. |
| **DisplayName** | **string** | Optional | A user-friendly display name for the field. |
| **Description** | **string** | Optional | A detailed description of the field and its purpose. |
| **DataTypeId** | [ResourceId](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SeriesIdentifierField(
    fieldName: "...",  // required — The unique identifier for the field within the dataset.
    displayName: "...",  // optional — A user-friendly display name for the field.
    description: "...",  // optional — A detailed description of the field and its purpose.
    dataTypeId: new ResourceId(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SeriesIdentifierField>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

