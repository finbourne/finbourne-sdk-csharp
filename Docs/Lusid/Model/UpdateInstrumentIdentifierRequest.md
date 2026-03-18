# Finbourne.Sdk.Lusid.Model.UpdateInstrumentIdentifierRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The allowable instrument identifier to update, insert or remove e.g. &#39;Figi&#39;. |
| **Value** | **string** | Optional | The new value of the allowable instrument identifier. If unspecified the identifier will be removed from the instrument. |
| **EffectiveAt** | [DateTimeOrCutLabel](DateTimeOrCutLabel.md) | Optional | The effective datetime from which the identifier should be updated, inserted or removed. Defaults to the current LUSID system datetime if not specified. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateInstrumentIdentifierRequest(
    type: "...",  // required — The allowable instrument identifier to update, insert or remove e.g. &#39;Figi&#39;.
    value: "...",  // optional — The new value of the allowable instrument identifier. If unspecified the identifier will be removed from the instrument.
    effectiveAt: new DateTimeOrCutLabel(...)  // optional — The effective datetime from which the identifier should be updated, inserted or removed. Defaults to the current LUSID system datetime if not specified.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateInstrumentIdentifierRequest>(json);
```

- [DateTimeOrCutLabel](DateTimeOrCutLabel.md) — used in `EffectiveAt`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

