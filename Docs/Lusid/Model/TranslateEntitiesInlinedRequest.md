# Finbourne.Sdk.Lusid.Model.TranslateEntitiesInlinedRequest

Request to translate financial entities with a given script body.  The output of the translation is validated against a schema specified in the request.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityPayloads** | [Dictionary&lt;string, TranslationInput&gt;](TranslationInput.md) | Required | Entity payloads to be translated indexed by (ephemeral) unique correlation ids. |
| **ScriptBody** | **string** | Required | The body of the translation script to use for translating the entities. |
| **Schema** | [DialectSchema](DialectSchema.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslateEntitiesInlinedRequest(
    entityPayloads: new TranslationInput(...),  // required — Entity payloads to be translated indexed by (ephemeral) unique correlation ids.
    scriptBody: "...",  // required — The body of the translation script to use for translating the entities.
    schema: new DialectSchema(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslateEntitiesInlinedRequest>(json);
```


## Related Models

- [TranslationInput](TranslationInput.md) — used in `EntityPayloads`
- [DialectSchema](DialectSchema.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

