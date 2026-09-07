# Finbourne.Sdk.Lusid.Model.ScenarioTemplateDefinition

One pre-built scenario template: the name to pass to CreateScenarioFromTemplate, what the  template does, and the parameters it accepts. A parameter not listed here is rejected by  the create call, not ignored.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The template name, as accepted by CreateScenarioFromTemplate. |
| **Description** | **string** | Optional | What the template&#39;s scenario does. |
| **Parameters** | [List&lt;ScenarioTemplateParameter&gt;](ScenarioTemplateParameter.md) | Optional | The parameters the template accepts, in the order they are documented. Parameter names are  case-sensitive; supplying one not in this list fails the create call. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioTemplateDefinition(
    name: "...",  // optional — The template name, as accepted by CreateScenarioFromTemplate.
    description: "...",  // optional — What the template&#39;s scenario does.
    parameters: new List<ScenarioTemplateParameter>()  // optional — The parameters the template accepts, in the order they are documented. Parameter names are  case-sensitive; supplying one not in this list fails the create call.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioTemplateDefinition>(json);
```

- [ScenarioTemplateParameter](ScenarioTemplateParameter.md) — used in `Parameters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

