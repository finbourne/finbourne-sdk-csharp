# Finbourne.Sdk.Luminesce.Model.InlinedPropertyDesign

Representation of a set of inlined properties for a given provider so that SQL can be generated to be able to inline properties into luminesce
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ProviderName** | **string** | Optional | The provider name for which these properties are to be inlined |
| **ProviderNameExtension** | **string** | Optional | The provider extension name for extended providers |
| **InlinedPropertyItems** | [List&lt;InlinedPropertyItem&gt;](InlinedPropertyItem.md) | Optional | Collection of Inlined properties |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new InlinedPropertyDesign(
    providerName: "...",  // optional — The provider name for which these properties are to be inlined
    providerNameExtension: "...",  // optional — The provider extension name for extended providers
    inlinedPropertyItems: new List<InlinedPropertyItem>()  // optional — Collection of Inlined properties
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InlinedPropertyDesign>(json);
```

- [InlinedPropertyItem](InlinedPropertyItem.md) — used in `InlinedPropertyItems`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

