# Finbourne.Sdk.Access.Model.ForSpec

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtRangeForSpec** | [AsAtRangeForSpec](AsAtRangeForSpec.md) | Optional | *No description available.* |
| **AsAtRelative** | [AsAtRelative](AsAtRelative.md) | Optional | *No description available.* |
| **EffectiveDateHasQuality** | [EffectiveDateHasQuality](EffectiveDateHasQuality.md) | Optional | *No description available.* |
| **EffectiveDateRelative** | [EffectiveDateRelative](EffectiveDateRelative.md) | Optional | *No description available.* |
| **EffectiveRange** | [EffectiveRange](EffectiveRange.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new ForSpec(
    asAtRangeForSpec: new AsAtRangeForSpec(...),  // optional
    asAtRelative: new AsAtRelative(...),  // optional
    effectiveDateHasQuality: new EffectiveDateHasQuality(...),  // optional
    effectiveDateRelative: new EffectiveDateRelative(...),  // optional
    effectiveRange: new EffectiveRange(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ForSpec>(json);
```


## Related Models

- [AsAtRangeForSpec](AsAtRangeForSpec.md)
- [AsAtRelative](AsAtRelative.md)
- [EffectiveDateHasQuality](EffectiveDateHasQuality.md)
- [EffectiveDateRelative](EffectiveDateRelative.md)
- [EffectiveRange](EffectiveRange.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

