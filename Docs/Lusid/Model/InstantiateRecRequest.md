# Finbourne.Sdk.Lusid.Model.InstantiateRecRequest

The request to instantiate a new rec instance from a rec definition and start its first run. Each  date accepts a date-time or a LUSID cut label, and defaults to the current date-time when omitted.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LeftEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The left effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. When the definition&#39;s datePolicy.effectiveAtProgression is Series, must be strictly after the previous instance&#39;s leftEffectiveAt. |
| **LeftAsAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The left asAt datetime, as a date-time or a LUSID cut label. Must be omitted when the definition&#39;s datePolicy.asAtPolicy.left is Latest, as the system reconciles at the latest knowledge on every run. When it is Explicit, defaults to the current date-time and is pinned on the instance. |
| **RightEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The right effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. When the definition&#39;s datePolicy.effectiveAtProgression is Series, must be strictly after the previous instance&#39;s rightEffectiveAt. |
| **RightAsAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The right asAt datetime, as a date-time or a LUSID cut label. Must be omitted when the definition&#39;s datePolicy.asAtPolicy.right is Latest, as the system reconciles at the latest knowledge on every run. When it is Explicit, defaults to the current date-time and is pinned on the instance. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstantiateRecRequest(
    recDefinitionId: new ResourceId(...),  // required
    leftEffectiveAt: new DateTimeOrCutLabel(...),  // optional — The left effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. When the definition&#39;s datePolicy.effectiveAtProgression is Series, must be strictly after the previous instance&#39;s leftEffectiveAt.
    leftAsAt: new DateTimeOrCutLabel(...),  // optional — The left asAt datetime, as a date-time or a LUSID cut label. Must be omitted when the definition&#39;s datePolicy.asAtPolicy.left is Latest, as the system reconciles at the latest knowledge on every run. When it is Explicit, defaults to the current date-time and is pinned on the instance.
    rightEffectiveAt: new DateTimeOrCutLabel(...),  // optional — The right effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. When the definition&#39;s datePolicy.effectiveAtProgression is Series, must be strictly after the previous instance&#39;s rightEffectiveAt.
    rightAsAt: new DateTimeOrCutLabel(...)  // optional — The right asAt datetime, as a date-time or a LUSID cut label. Must be omitted when the definition&#39;s datePolicy.asAtPolicy.right is Latest, as the system reconciles at the latest knowledge on every run. When it is Explicit, defaults to the current date-time and is pinned on the instance.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstantiateRecRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `LeftEffectiveAt`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `LeftAsAt`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `RightEffectiveAt`
- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `RightAsAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

