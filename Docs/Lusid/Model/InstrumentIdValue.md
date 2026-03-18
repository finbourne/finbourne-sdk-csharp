# Finbourne.Sdk.Lusid.Model.InstrumentIdValue

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | The value of the identifier. |
| **EffectiveAt** | **DateTimeOffset** | Optional | The effective datetime from which the identifier will be valid. If left unspecified the default value is the beginning of time. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentIdValue(
    value: "...",  // required — The value of the identifier.
    effectiveAt: DateTimeOffset.Now  // optional — The effective datetime from which the identifier will be valid. If left unspecified the default value is the beginning of time.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentIdValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

