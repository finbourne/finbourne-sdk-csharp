# Finbourne.Sdk.Lusid.Model.RecActivityWindow

Base class for the activity windows that give the date range a rec definition's activity-based  reconciliations cover. Polymorphic by windowType; each supported type has a corresponding inherited class.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InitialActivitySinceEffectiveAt** | [RecActivitySinceEffectiveAt](RecActivitySinceEffectiveAt.md) | Required | *No description available.* |
| **WindowType** | **string** | Required | Polymorphic discriminator. Supported types: Contiguous. Contiguous requires effectiveAtProgression Series. Available values: Contiguous, FixedLookback, Explicit, ClosedPeriod, ContiguousAsAt. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecActivityWindow(
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
var instance = JsonConvert.DeserializeObject<RecActivityWindow>(json);
```


## Related Models

- [RecActivitySinceEffectiveAt](RecActivitySinceEffectiveAt.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

