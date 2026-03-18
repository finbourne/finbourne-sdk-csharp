# Finbourne.Sdk.Lusid.Model.CustomDataModelPropertySpecificationWithDisplayName

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | The display name of the property definition. |
| **PropertyKey** | **string** | Required | The property key that is required/allowed on the bound entity. |
| **Required** | **bool** | Optional | Whether property is required or allowed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomDataModelPropertySpecificationWithDisplayName(
    displayName: "...",  // optional — The display name of the property definition.
    propertyKey: "...",  // required — The property key that is required/allowed on the bound entity.
    required: true  // optional — Whether property is required or allowed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomDataModelPropertySpecificationWithDisplayName>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

