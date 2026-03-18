# Finbourne.Sdk.Access.Model.GeneratePolicyFromTemplateRequest

Generate policy from template
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **TemplateSelection** | [List&lt;TemplateSelection&gt;](TemplateSelection.md) | Required | List of template selection, identifying policy templates to use for generation |
| **Selectors** | [List&lt;SelectorDefinition&gt;](SelectorDefinition.md) | Optional | List of additional selectors to be included in the policy |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new GeneratePolicyFromTemplateRequest(
    templateSelection: new List<TemplateSelection>(),  // required — List of template selection, identifying policy templates to use for generation
    selectors: new List<SelectorDefinition>()  // optional — List of additional selectors to be included in the policy
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GeneratePolicyFromTemplateRequest>(json);
```


## Related Models

- [TemplateSelection](TemplateSelection.md) — used in `TemplateSelection`
- [SelectorDefinition](SelectorDefinition.md) — used in `Selectors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

