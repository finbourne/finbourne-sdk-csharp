# Finbourne.Sdk.Lusid.Model.FieldDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | *No description available.* |
| **IsRequired** | **bool** | Required | *No description available.* |
| **IsUnique** | **bool** | Required | *No description available.* |
| **ValueType** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FieldDefinition(
    key: "...",  // required
    isRequired: true,  // required
    isUnique: true,  // required
    valueType: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FieldDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

