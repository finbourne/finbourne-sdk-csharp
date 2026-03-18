# Finbourne.Sdk.Lusid.Model.CustomDataModelIdentifierTypeSpecificationWithDisplayName

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Optional | The display name of the property definition. |
| **IdentifierKey** | **string** | Required | The identifier type that is required/allowed on the bound entity. |
| **Required** | **bool** | Optional | Whether identifier type is required or allowed. |
| **IdentifierType** | **string** | Optional | The name of the identifier type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustomDataModelIdentifierTypeSpecificationWithDisplayName(
    displayName: "...",  // optional — The display name of the property definition.
    identifierKey: "...",  // required — The identifier type that is required/allowed on the bound entity.
    required: true,  // optional — Whether identifier type is required or allowed.
    identifierType: "..."  // optional — The name of the identifier type.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustomDataModelIdentifierTypeSpecificationWithDisplayName>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

