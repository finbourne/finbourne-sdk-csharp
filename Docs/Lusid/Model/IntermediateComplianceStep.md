# Finbourne.Sdk.Lusid.Model.IntermediateComplianceStep

> **Inherits from:** [ComplianceStep](ComplianceStep.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComplianceStepType** | **string** | Required | . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep *(inherited)* |
| **Label** | **string** | Required | The label of the compliance step |
| **GroupedParameters** | **Dictionary&lt;string, List&lt;ComplianceTemplateParameter&gt;&gt;** | Required | Parameters required for the step |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IntermediateComplianceStep(
    label: "...",  // required — The label of the compliance step
    groupedParameters:   // required — Parameters required for the step
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntermediateComplianceStep>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

