# Finbourne.Sdk.Lusid.Model.RecombineStep

> **Inherits from:** [ComplianceStep](ComplianceStep.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Required | The label of the compliance step |
| **Parameters** | [List&lt;ComplianceTemplateParameter&gt;](ComplianceTemplateParameter.md) | Required | Parameters required for the step |
| **ComplianceStepType** | **string** | Required | . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep Default: `ComplianceStepTypeEnum.RecombineStep` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecombineStep(
    label: "...",  // required — The label of the compliance step
    parameters: new List<ComplianceTemplateParameter>(),  // required — Parameters required for the step
    complianceStepType: "..."  // required — . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecombineStep>(json);
```


- [ComplianceTemplateParameter](ComplianceTemplateParameter.md) — used in `Parameters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

