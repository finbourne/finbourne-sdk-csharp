# Finbourne.Sdk.Lusid.Model.TransactionPropertyMapping

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Required | The key that uniquely identifies the property. It has the format {domain}/{scope}/{code} |
| **MapFrom** | **string** | Optional | The Property Key of the Property to map from |
| **SetTo** | **Object** | Optional | A pointer to the Property being mapped from |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionPropertyMapping(
    propertyKey: "...",  // required — The key that uniquely identifies the property. It has the format {domain}/{scope}/{code}
    mapFrom: "...",  // optional — The Property Key of the Property to map from
    setTo:   // optional — A pointer to the Property being mapped from
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionPropertyMapping>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

