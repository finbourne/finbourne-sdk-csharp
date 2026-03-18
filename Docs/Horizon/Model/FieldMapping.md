# Finbourne.Sdk.Horizon.Model.FieldMapping

Mapping from a set of Vendor Fields to a LUSID core entity field
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FieldName** | **string** | Required | The LUSID core entity field |
| **DefaultValue** | **string** | Optional | Default value if needed |
| **VendorFields** | [List&lt;VendorField&gt;](VendorField.md) | Required | Fields that will be used to map to this field |
| **TransformationDescription** | **string** | Optional | The transformation, if required, to map from VendorFields to the LUSID Property |
| **EntityType** | **string** | Required | The LUSID Entity this is valid for |
| **EntitySubType** | **string** | Optional | The LUSID Entity sub type this is valid for |
| **Versions** | **List&lt;string&gt;** | Required | The versions of the Vendor integration this mapping is valid for |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new FieldMapping(
    fieldName: "...",  // required — The LUSID core entity field
    defaultValue: "...",  // optional — Default value if needed
    vendorFields: new List<VendorField>(),  // required — Fields that will be used to map to this field
    transformationDescription: "...",  // optional — The transformation, if required, to map from VendorFields to the LUSID Property
    entityType: "...",  // required — The LUSID Entity this is valid for
    entitySubType: "...",  // optional — The LUSID Entity sub type this is valid for
    versions:   // required — The versions of the Vendor integration this mapping is valid for
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FieldMapping>(json);
```

- [VendorField](VendorField.md) — used in `VendorFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

