# Finbourne.Sdk.Access.Model.GeneratedPolicyComponents

Response object for policy generated from template
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Applications** | **List&lt;string&gt;** | Optional | Applications to which the policy applies |
| **TemplateMetadata** | [TemplateMetadata](TemplateMetadata.md) | Optional | *No description available.* |
| **Selectors** | [List&lt;SelectorDefinition&gt;](SelectorDefinition.md) | Optional | Selectors that this policy will be applied to |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new GeneratedPolicyComponents(
    applications: ,  // optional — Applications to which the policy applies
    templateMetadata: new TemplateMetadata(...),  // optional
    selectors: new List<SelectorDefinition>()  // optional — Selectors that this policy will be applied to
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GeneratedPolicyComponents>(json);
```

- [TemplateMetadata](TemplateMetadata.md)
- [SelectorDefinition](SelectorDefinition.md) — used in `Selectors`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

