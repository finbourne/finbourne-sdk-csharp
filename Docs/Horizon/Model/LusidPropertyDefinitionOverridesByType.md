# Finbourne.Sdk.Horizon.Model.LusidPropertyDefinitionOverridesByType

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayNameOverride** | **string** | Optional | *No description available.* |
| **DescriptionOverride** | **string** | Optional | *No description available.* |
| **EntityType** | **string** | Optional | *No description available.* |
| **EntitySubType** | **List&lt;string&gt;** | Optional | *No description available.* |
| **VendorPackage** | **List&lt;string&gt;** | Optional | *No description available.* |
| **EffectiveFromOverride** | **string** | Optional | ISO-8601 instant to use as the property value&#39;s effectiveFrom instead of the date the integration derives, e.g. \&quot;0001-01-01T00:00:00Z\&quot;. Only accepted for integrations reporting supportsEffectiveFromOverride, and only for TimeVariant property definitions. Omit to leave any stored value untouched; send an empty string to clear it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new LusidPropertyDefinitionOverridesByType(
    displayNameOverride: "...",  // optional
    descriptionOverride: "...",  // optional
    entityType: "...",  // optional
    entitySubType: ,  // optional
    vendorPackage: ,  // optional
    effectiveFromOverride: "..."  // optional — ISO-8601 instant to use as the property value&#39;s effectiveFrom instead of the date the integration derives, e.g. \&quot;0001-01-01T00:00:00Z\&quot;. Only accepted for integrations reporting supportsEffectiveFromOverride, and only for TimeVariant property definitions. Omit to leave any stored value untouched; send an empty string to clear it.
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

