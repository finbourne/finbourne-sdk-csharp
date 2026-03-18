# Finbourne.Sdk.Lusid.Model.TranslationResult

The result of invoking a translation script.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Entity** | **string** | Required | The serialised entity the translation script produced. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Required | Any properties the translation script produced. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslationResult(
    entity: "...",  // required — The serialised entity the translation script produced.
    properties: new Property(...)  // required — Any properties the translation script produced.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslationResult>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

