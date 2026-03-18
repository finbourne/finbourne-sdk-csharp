# Finbourne.Sdk.Horizon.Model.VendorProduct

Denormalised information about vendors, the products they provide and the LUSID entity types they can be used to populate.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VendorName** | **string** | Required | *No description available.* |
| **ProductName** | **string** | Required | *No description available.* |
| **VendorProductKey** | **string** | Required | *No description available.* |
| **LusidEntity** | [LusidEntity](LusidEntity.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new VendorProduct(
    vendorName: "...",  // required
    productName: "...",  // required
    vendorProductKey: "...",  // required
    lusidEntity: new LusidEntity(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VendorProduct>(json);
```

- [LusidEntity](LusidEntity.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

