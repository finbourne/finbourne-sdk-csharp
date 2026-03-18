# Finbourne.Sdk.Lusid.Model.TranslationInput

The input to a translation script.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Entity** | **string** | Required | The serialised entity to be passed to the translation script. This could represent e.g. an instrument in any  dialect. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TranslationInput(
    entity: "..."  // required — The serialised entity to be passed to the translation script. This could represent e.g. an instrument in any  dialect.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TranslationInput>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

