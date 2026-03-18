# Finbourne.Sdk.Lusid.Model.CustomEntityFieldDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | The name of the field. |
| **Lifetime** | **string** | Required | Describes how the field’s values can change over time. The available values are: “Perpetual”, “TimeVariant”. |
| **Type** | **string** | Required | The value type for the field. Available values are: “String”, “Boolean”, “DateTime”, “Decimal”. |
| **CollectionType** | **string** | Optional | The collection type for the field. Available values are: “Single”, “Array”. Null value defaults to “Single” |
| **Required** | **bool** | Required | Whether the field is required or not. |
| **Description** | **string** | Optional | An optional description for the field. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomEntityFieldDefinition(
    name: "...",  // required — The name of the field.
    lifetime: "...",  // required — Describes how the field’s values can change over time. The available values are: “Perpetual”, “TimeVariant”.
    type: "...",  // required — The value type for the field. Available values are: “String”, “Boolean”, “DateTime”, “Decimal”.
    collectionType: "...",  // optional — The collection type for the field. Available values are: “Single”, “Array”. Null value defaults to “Single”
    required: true,  // required — Whether the field is required or not.
    description: "..."  // optional — An optional description for the field.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomEntityFieldDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

