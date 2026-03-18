# Finbourne.Sdk.Lusid.Model.TranslationScriptId

Id of the Translation Script.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | Scope of the translation script. |
| **Code** | **string** | Required | Code of the translation script. |
| **VarVersion** | **string** | Required | Semantic Version of the translation script of the form MAJOR.MINOR.PATCH. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslationScriptId(
    scope: "...",  // required — Scope of the translation script.
    code: "...",  // required — Code of the translation script.
    varVersion: "..."  // required — Semantic Version of the translation script of the form MAJOR.MINOR.PATCH.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslationScriptId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

