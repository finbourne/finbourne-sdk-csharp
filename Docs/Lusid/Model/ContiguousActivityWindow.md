# Finbourne.Sdk.Lusid.Model.ContiguousActivityWindow

The activity window for a running series of instances: each instance's window starts where the previous  instance's ended, so the series tiles the effective timeline with no gaps and no overlap. Requires the  definition's effectiveAtProgression to be Series.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InitialActivitySinceEffectiveAt** | [RecActivitySinceEffectiveAt](RecActivitySinceEffectiveAt.md) | Required | *No description available.* |
| **WindowType** | **string** | Required | Polymorphic discriminator. Supported types: Contiguous. Contiguous requires effectiveAtProgression Series. Available values: Contiguous, FixedLookback, Explicit, ClosedPeriod, ContiguousAsAt. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ContiguousActivityWindow(
    initialActivitySinceEffectiveAt: new RecActivitySinceEffectiveAt(...),  // required
    windowType: "..."  // required — Polymorphic discriminator. Supported types: Contiguous. Contiguous requires effectiveAtProgression Series. Available values: Contiguous, FixedLookback, Explicit, ClosedPeriod, ContiguousAsAt.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ContiguousActivityWindow>(json);
```


## Related Models

- [RecActivitySinceEffectiveAt](RecActivitySinceEffectiveAt.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

