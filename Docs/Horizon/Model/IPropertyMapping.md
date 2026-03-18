# Finbourne.Sdk.Horizon.Model.IPropertyMapping

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntitySubType** | **string** | Optional | *No description available.* |
| **EntityType** | **string** | Required | *No description available.* |
| **Optionality** | **string** | Required | *No description available.* |
| **Property** | [LusidPropertyDefinition](LusidPropertyDefinition.md) | Required | *No description available.* |
| **TransformationDescription** | **string** | Optional | *No description available.* |
| **VendorFields** | [List&lt;VendorField&gt;](VendorField.md) | Required | *No description available.* |
| **Versions** | **List&lt;string&gt;** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IPropertyMapping(
    entitySubType: "...",  // optional
    entityType: "...",  // required
    optionality: "...",  // required
    property: new LusidPropertyDefinition(...),  // required
    transformationDescription: "...",  // optional
    vendorFields: new List<VendorField>(),  // required
    versions:   // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IPropertyMapping>(json);
```

- [LusidPropertyDefinition](LusidPropertyDefinition.md)
- [VendorField](VendorField.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

