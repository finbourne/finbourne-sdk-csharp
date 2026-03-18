# Finbourne.Sdk.Lusid.Model.GroupFilterStep

> **Inherits from:** [ComplianceStep](ComplianceStep.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Required | The label of the compliance step |
| **LimitCheckParameters** | [List&lt;ComplianceTemplateParameter&gt;](ComplianceTemplateParameter.md) | Required | Parameters required for an absolute limit check |
| **ComplianceStepType** | **string** | Required | . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep Default: `ComplianceStepTypeEnum.GroupFilterStep` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupFilterStep(
    label: "...",  // required — The label of the compliance step
    limitCheckParameters: new List<ComplianceTemplateParameter>(),  // required — Parameters required for an absolute limit check
    complianceStepType: "..."  // required — . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupFilterStep>(json);
```


- [ComplianceTemplateParameter](ComplianceTemplateParameter.md) — used in `LimitCheckParameters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

