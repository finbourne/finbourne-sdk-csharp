# Finbourne.Sdk.Horizon.Model.LusidPropertyToVendorFieldMapping

The mapping of a LUSID Property from the Vendor Field that would populate it
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Property** | [LusidPropertyDefinition](LusidPropertyDefinition.md) | Required | *No description available.* |
| **VendorField** | **string** | Required | *No description available.* |
| **VendorPackage** | **string** | Required | *No description available.* |
| **VendorNamespace** | **string** | Required | *No description available.* |
| **Optionality** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidPropertyToVendorFieldMapping(
    property: new LusidPropertyDefinition(...),  // required
    vendorField: "...",  // required
    vendorPackage: "...",  // required
    vendorNamespace: "...",  // required
    optionality: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidPropertyToVendorFieldMapping>(json);
```


## Related Models

- [LusidPropertyDefinition](LusidPropertyDefinition.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

