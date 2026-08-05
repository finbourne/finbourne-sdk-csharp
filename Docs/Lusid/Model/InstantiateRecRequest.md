# Finbourne.Sdk.Lusid.Model.InstantiateRecRequest

The request to instantiate a new rec instance from a rec definition and start its first run. Each  date accepts a date-time or a LUSID cut label, and defaults to the current date-time when omitted.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **LeftEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The left effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. |
| **LeftAsAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The left asAt datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. |
| **RightEffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The right effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. |
| **RightAsAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The right asAt datetime, as a date-time or a LUSID cut label. Defaults to the current date-time. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstantiateRecRequest(
    recDefinitionId: new ResourceId(...),  // required
    leftEffectiveAt: new DateTimeOrCutLabel(...),  // optional — The left effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time.
    leftAsAt: new DateTimeOrCutLabel(...),  // optional — The left asAt datetime, as a date-time or a LUSID cut label. Defaults to the current date-time.
    rightEffectiveAt: new DateTimeOrCutLabel(...),  // optional — The right effective datetime, as a date-time or a LUSID cut label. Defaults to the current date-time.
    rightAsAt: new DateTimeOrCutLabel(...)  // optional — The right asAt datetime, as a date-time or a LUSID cut label. Defaults to the current date-time.
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

