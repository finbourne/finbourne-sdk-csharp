# Finbourne.Sdk.Horizon.Model.PropertyMapping

Mapping from a set of VendorFields to a LUSID Property
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Property** | [LusidPropertyDefinition](LusidPropertyDefinition.md) | Required | *No description available.* |
| **VendorFields** | [List&lt;VendorField&gt;](VendorField.md) | Required | Fields that will be used to map to this Property Definition |
| **Optionality** | **string** | Required | Whether the Property is Mandatory, Suggested or Optional |
| **EntityType** | **string** | Required | The LUSID Entity this is valid for |
| **EntitySubType** | **string** | Optional | The LUSID Entity sub type this is valid for |
| **TransformationDescription** | **string** | Optional | The transformation, if required, to map from VendorFields to the LUSID Property |
| **Versions** | **List&lt;string&gt;** | Required | The versions of the Vendor integration this mapping is valid for |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new PropertyMapping(
    property: new LusidPropertyDefinition(...),  // required
    vendorFields: new List<VendorField>(),  // required — Fields that will be used to map to this Property Definition
    optionality: "...",  // required — Whether the Property is Mandatory, Suggested or Optional
    entityType: "...",  // required — The LUSID Entity this is valid for
    entitySubType: "...",  // optional — The LUSID Entity sub type this is valid for
    transformationDescription: "...",  // optional — The transformation, if required, to map from VendorFields to the LUSID Property
    versions:   // required — The versions of the Vendor integration this mapping is valid for
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PropertyMapping>(json);
```


## Related Models

- [LusidPropertyDefinition](LusidPropertyDefinition.md)
- [VendorField](VendorField.md) — used in `VendorFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

