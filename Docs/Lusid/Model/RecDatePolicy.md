# Finbourne.Sdk.Lusid.Model.RecDatePolicy

The date policy of a rec definition: how the effective dates of successive instances may progress, whether each  side reconciles at the latest knowledge or at a pinned asAt, and — for activity-based rec types — how the  activity window is bounded.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAtProgression** | **string** | Optional | How the effective dates of successive instances may progress. Series (the default): each instance&#39;s leftEffectiveAt and rightEffectiveAt must be strictly after the previous instance&#39;s. Unconstrained: no relationship between instances. Immutable once the definition has instances. Available values: Series, Unconstrained. |
| **AsAtPolicy** | [RecAsAtPolicy](RecAsAtPolicy.md) | Optional | *No description available.* |
| **ActivityWindow** | [RecActivityWindow](RecActivityWindow.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecDatePolicy(
    effectiveAtProgression: "...",  // optional — How the effective dates of successive instances may progress. Series (the default): each instance&#39;s leftEffectiveAt and rightEffectiveAt must be strictly after the previous instance&#39;s. Unconstrained: no relationship between instances. Immutable once the definition has instances. Available values: Series, Unconstrained.
    asAtPolicy: new RecAsAtPolicy(...),  // optional
    activityWindow: new RecActivityWindow(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecDatePolicy>(json);
```

- [RecAsAtPolicy](RecAsAtPolicy.md)
- [RecActivityWindow](RecActivityWindow.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

