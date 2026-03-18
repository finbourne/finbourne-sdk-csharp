# Finbourne.Sdk.Lusid.Model.TransactionTypePropertyMapping

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Required | The key that uniquely identifies the property. It has the format {domain}/{scope}/{code} |
| **MapFrom** | **string** | Optional | The Property Key of the Property to map from |
| **SetTo** | **string** | Optional | A pointer to the Property being mapped from |
| **TemplateFrom** | **string** | Optional | The template that defines how the property value is constructed from transaction, instrument and portfolio details. |
| **Nullify** | **bool?** | Optional | Flag to unset the Property Key for the mapping |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionTypePropertyMapping(
    propertyKey: "...",  // required — The key that uniquely identifies the property. It has the format {domain}/{scope}/{code}
    mapFrom: "...",  // optional — The Property Key of the Property to map from
    setTo: "...",  // optional — A pointer to the Property being mapped from
    templateFrom: "...",  // optional — The template that defines how the property value is constructed from transaction, instrument and portfolio details.
    nullify: true  // optional — Flag to unset the Property Key for the mapping
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionTypePropertyMapping>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

