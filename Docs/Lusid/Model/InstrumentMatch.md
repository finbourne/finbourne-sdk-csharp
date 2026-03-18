# Finbourne.Sdk.Lusid.Model.InstrumentMatch

A collection of instrument search results
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MasteredInstruments** | [List&lt;InstrumentDefinition&gt;](InstrumentDefinition.md) | Optional | The collection of instruments found by the search which have been mastered within LUSID. |
| **ExternalInstruments** | [List&lt;InstrumentDefinition&gt;](InstrumentDefinition.md) | Optional | The collection of instruments found by the search which have not been mastered within LUSID and instead found via OpenFIGI. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InstrumentMatch(
    masteredInstruments: new List<InstrumentDefinition>(),  // optional — The collection of instruments found by the search which have been mastered within LUSID.
    externalInstruments: new List<InstrumentDefinition>()  // optional — The collection of instruments found by the search which have not been mastered within LUSID and instead found via OpenFIGI.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstrumentMatch>(json);
```


## Related Models

- [InstrumentDefinition](InstrumentDefinition.md) — used in `MasteredInstruments`
- [InstrumentDefinition](InstrumentDefinition.md) — used in `ExternalInstruments`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

