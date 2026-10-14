# Finbourne.Sdk.Lusid.Model.SwingSpreadApplied

The stored spread applied to a share class's baseline price and the tier it came from.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Bps** | **decimal** | Required | The spread applied, in basis points. |
| **TierMatched** | [SwingSpreadTierBounds](SwingSpreadTierBounds.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SwingSpreadApplied(
    bps: 0.0d,  // required — The spread applied, in basis points.
    tierMatched: new SwingSpreadTierBounds(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SwingSpreadApplied>(json);
```

- [SwingSpreadTierBounds](SwingSpreadTierBounds.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

