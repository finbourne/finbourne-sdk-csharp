# Finbourne.Sdk.Horizon.Model.SetInstanceOptionalPropertyMappingResponse

Response for SetInstanceOptionalPropertyMapping.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyOverrides** | [Dictionary&lt;string, LusidPropertyDefinitionOverridesByType&gt;](LusidPropertyDefinitionOverridesByType.md) | Required | The full, current optional property mapping for the instance, after the write. |
| **Warnings** | **List&lt;string&gt;** | Required | Advisory warnings about a write that succeeded regardless, e.g. a future-dated effectiveFromOverride, or another enabled instance of the same integration holding a different effectiveFromOverride for the same property. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new SetInstanceOptionalPropertyMappingResponse(
    propertyOverrides: new LusidPropertyDefinitionOverridesByType(...),  // required — The full, current optional property mapping for the instance, after the write.
    warnings:   // required — Advisory warnings about a write that succeeded regardless, e.g. a future-dated effectiveFromOverride, or another enabled instance of the same integration holding a different effectiveFromOverride for the same property.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetInstanceOptionalPropertyMappingResponse>(json);
```


## Related Models

- [LusidPropertyDefinitionOverridesByType](LusidPropertyDefinitionOverridesByType.md) — used in `PropertyOverrides`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

