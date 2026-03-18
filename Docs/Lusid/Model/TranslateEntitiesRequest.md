# Finbourne.Sdk.Lusid.Model.TranslateEntitiesRequest

Request to translate financial entities with a specified script stored in LUSID,  specified in the request by its id. The output of the translation is validated against a dialect stored in LUSID,  again specified in the request by its id.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityPayloads** | [Dictionary&lt;string, TranslationInput&gt;](TranslationInput.md) | Required | Entity payloads to be translated, indexed by (ephemeral) unique correlation ids. |
| **ScriptId** | [TranslationScriptId](TranslationScriptId.md) | Required | *No description available.* |
| **DialectId** | [DialectId](DialectId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslateEntitiesRequest(
    entityPayloads: new TranslationInput(...),  // required — Entity payloads to be translated, indexed by (ephemeral) unique correlation ids.
    scriptId: new TranslationScriptId(...),  // required
    dialectId: new DialectId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslateEntitiesRequest>(json);
```


## Related Models

- [TranslationInput](TranslationInput.md) — used in `EntityPayloads`
- [TranslationScriptId](TranslationScriptId.md)
- [DialectId](DialectId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

