# Finbourne.Sdk.Lusid.Model.TranslateInstrumentDefinitionsRequest

A collection of instruments to translate, along with the target dialect to translate into.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Instruments** | [Dictionary&lt;string, LusidInstrument&gt;](LusidInstrument.md) | Required | The collection of instruments to translate.                Each instrument definition should be keyed by a unique correlation id. This id is ephemeral  and is not stored by LUSID. It serves only as a way to easily identify each instrument in the response.                Any instrument that is not already in the LUSID dialect should be given as an ExoticInstrument. |
| **Dialect** | **string** | Required | The target dialect that the given instruments should be translated to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslateInstrumentDefinitionsRequest(
    instruments: new LusidInstrument(...),  // required — The collection of instruments to translate.                Each instrument definition should be keyed by a unique correlation id. This id is ephemeral  and is not stored by LUSID. It serves only as a way to easily identify each instrument in the response.                Any instrument that is not already in the LUSID dialect should be given as an ExoticInstrument.
    dialect: "..."  // required — The target dialect that the given instruments should be translated to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslateInstrumentDefinitionsRequest>(json);
```


## Related Models

- [LusidInstrument](LusidInstrument.md) — used in `Instruments`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

