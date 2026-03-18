# Finbourne.Sdk.Lusid.Model.TranslationContext

Options for overriding default scripted translation configuration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisableScriptedTranslation** | **bool** | Optional | *No description available.* |
| **ScriptMap** | [ScriptMapReference](ScriptMapReference.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslationContext(
    disableScriptedTranslation: true,  // optional
    scriptMap: new ScriptMapReference(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslationContext>(json);
```

- [ScriptMapReference](ScriptMapReference.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

