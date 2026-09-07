# Finbourne.Sdk.Lusid.Model.CreateScenarioFromTemplateRequest

Request to create a scenario from a pre-built parameterised template. The template determines the  shape of the scenario's shifts; the parameters supply the targets (e.g. currency, instrument) and  optionally override the template's default shift size.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Template** | **string** | Required | The template to build the scenario from. Use ListScenarioTemplates to discover the available  templates and the parameters each accepts. |
| **Code** | **string** | Required | The code of the scenario to create. |
| **DisplayName** | **string** | Optional | The display name of the created scenario. Defaults to a name derived from the template. |
| **Description** | **string** | Optional | The description of the created scenario. Defaults to a description derived from the template. |
| **Parameters** | **Dictionary&lt;string, string&gt;** | Optional | Template parameters. Which parameters each template requires and accepts - with defaults and  units for the numeric ones - is listed by ListScenarioTemplates. A parameter the template does  not read is rejected rather than ignored, and parameter names are case-sensitive. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateScenarioFromTemplateRequest(
    template: "...",  // required — The template to build the scenario from. Use ListScenarioTemplates to discover the available  templates and the parameters each accepts.
    code: "...",  // required — The code of the scenario to create.
    displayName: "...",  // optional — The display name of the created scenario. Defaults to a name derived from the template.
    description: "...",  // optional — The description of the created scenario. Defaults to a description derived from the template.
    parameters:   // optional — Template parameters. Which parameters each template requires and accepts - with defaults and  units for the numeric ones - is listed by ListScenarioTemplates. A parameter the template does  not read is rejected rather than ignored, and parameter names are case-sensitive.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateScenarioFromTemplateRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

