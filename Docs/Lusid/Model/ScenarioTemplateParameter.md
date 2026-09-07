# Finbourne.Sdk.Lusid.Model.ScenarioTemplateParameter

One parameter of a scenario template: its name (case-sensitive), whether it must be supplied,  what it means, and - for optional numeric parameters - the default used when omitted and the  unit the value is read in.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The parameter name, as supplied in the create request&#39;s Parameters dictionary. Case-sensitive. |
| **Required** | **bool** | Optional | Whether the parameter must be supplied. |
| **Description** | **string** | Optional | What the parameter means to this template. |
| **DefaultValue** | **string** | Optional | The value used when the parameter is omitted. Null for required parameters. |
| **Unit** | **string** | Optional | The unit a numeric value is read in: &#39;BasisPoints&#39;, &#39;PercentagePoints&#39; or &#39;Fraction&#39;  (0.20 meaning +20%). The templates do NOT share one unit - read this per template.  Null for non-numeric parameters. |
| **ExclusiveGroup** | **string** | Optional | Parameters of a template sharing an ExclusiveGroup are alternatives: exactly one of them must  be supplied. Group members are not individually Required and carry no default. Null for  parameters that stand alone. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ScenarioTemplateParameter(
    name: "...",  // optional — The parameter name, as supplied in the create request&#39;s Parameters dictionary. Case-sensitive.
    required: true,  // optional — Whether the parameter must be supplied.
    description: "...",  // optional — What the parameter means to this template.
    defaultValue: "...",  // optional — The value used when the parameter is omitted. Null for required parameters.
    unit: "...",  // optional — The unit a numeric value is read in: &#39;BasisPoints&#39;, &#39;PercentagePoints&#39; or &#39;Fraction&#39;  (0.20 meaning +20%). The templates do NOT share one unit - read this per template.  Null for non-numeric parameters.
    exclusiveGroup: "..."  // optional — Parameters of a template sharing an ExclusiveGroup are alternatives: exactly one of them must  be supplied. Group members are not individually Required and carry no default. Null for  parameters that stand alone.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ScenarioTemplateParameter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

