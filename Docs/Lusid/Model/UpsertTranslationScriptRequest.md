# Finbourne.Sdk.Lusid.Model.UpsertTranslationScriptRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [TranslationScriptId](TranslationScriptId.md) | Required | *No description available.* |
| **Body** | **string** | Required | Body of the translation script, i.e. the actual translation code. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertTranslationScriptRequest(
    id: new TranslationScriptId(...),  // required
    body: "..."  // required — Body of the translation script, i.e. the actual translation code.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertTranslationScriptRequest>(json);
```


## Related Models

- [TranslationScriptId](TranslationScriptId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

