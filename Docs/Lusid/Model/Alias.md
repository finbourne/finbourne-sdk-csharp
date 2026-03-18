# Finbourne.Sdk.Lusid.Model.Alias

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AttributeName** | **string** | Required | The property key, identifier type, or field to be replaced by an alias. |
| **AttributeAlias** | **string** | Required | The alias to replace the property key, identifier type, or field on the bound entity. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Alias(
    attributeName: "...",  // required — The property key, identifier type, or field to be replaced by an alias.
    attributeAlias: "..."  // required — The alias to replace the property key, identifier type, or field on the bound entity.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Alias>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

