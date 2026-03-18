# Finbourne.Sdk.Horizon.Model.LusidPropertyDefinitionOverridesByType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayNameOverride** | **string** | Optional | *No description available.* |
| **DescriptionOverride** | **string** | Optional | *No description available.* |
| **EntityType** | **string** | Optional | *No description available.* |
| **EntitySubType** | **List&lt;string&gt;** | Optional | *No description available.* |
| **VendorPackage** | **List&lt;string&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidPropertyDefinitionOverridesByType(
    displayNameOverride: "...",  // optional
    descriptionOverride: "...",  // optional
    entityType: "...",  // optional
    entitySubType: ,  // optional
    vendorPackage:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LusidPropertyDefinitionOverridesByType>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

