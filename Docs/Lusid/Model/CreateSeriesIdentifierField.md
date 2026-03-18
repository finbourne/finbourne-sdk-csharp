# Finbourne.Sdk.Lusid.Model.CreateSeriesIdentifierField

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

var instance = new CreateSeriesIdentifierField(
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
var instance = JsonConvert.DeserializeObject<CreateSeriesIdentifierField>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

