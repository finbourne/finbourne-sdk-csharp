# Finbourne.Sdk.Access.Model.TemplateSelection

A template selection, identifying a policy template to use for generation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | Scope identifying policy template to use for generation |
| **Code** | **string** | Required | Code identifying policy template to use for generation |
| **SelectorTags** | **List&lt;string&gt;** | Optional | List of selector tags to optionally filter in the template generation  (Eg: Feature, Data, etc) |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new TemplateSelection(
    scope: "...",  // required — Scope identifying policy template to use for generation
    code: "...",  // required — Code identifying policy template to use for generation
    selectorTags:   // optional — List of selector tags to optionally filter in the template generation  (Eg: Feature, Data, etc)
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TemplateSelection>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

