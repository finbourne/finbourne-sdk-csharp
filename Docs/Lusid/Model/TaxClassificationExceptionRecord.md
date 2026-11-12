# Finbourne.Sdk.Lusid.Model.TaxClassificationExceptionRecord

An instrument the engine could not classify, or a qualifying-investments flip, for the exceptions feed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Luid** | **string** | Required | The LUSID instrument identifier of the instrument the exception was raised for. |
| **InstrumentName** | **string** | Optional | The name of the instrument the exception was raised for. |
| **Exception** | [TaxClassificationException](TaxClassificationException.md) | Required | *No description available.* |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective date the exception was observed at. |
| **AsAt** | **DateTimeOffset** | Required | The asAt time the exception was observed at. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassificationExceptionRecord(
    luid: "...",  // required — The LUSID instrument identifier of the instrument the exception was raised for.
    instrumentName: "...",  // optional — The name of the instrument the exception was raised for.
    exception: new TaxClassificationException(...),  // required
    effectiveAt: DateTimeOffset.Now,  // required — The effective date the exception was observed at.
    asAt: DateTimeOffset.Now  // required — The asAt time the exception was observed at.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassificationExceptionRecord>(json);
```

- [TaxClassificationException](TaxClassificationException.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

