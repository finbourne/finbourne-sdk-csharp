# Finbourne.Sdk.Lusid.Model.TranslationScript

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [TranslationScriptId](TranslationScriptId.md) | Required | *No description available.* |
| **Body** | **string** | Required | Body of the translation script, i.e. the actual translation code. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslationScript(
    id: new TranslationScriptId(...),  // required
    body: "...",  // required — Body of the translation script, i.e. the actual translation code.
    varVersion: new ModelVersion(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslationScript>(json);
```


## Related Models

- [TranslationScriptId](TranslationScriptId.md)
- [ModelVersion](ModelVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

