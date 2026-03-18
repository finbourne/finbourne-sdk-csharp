# Finbourne.Sdk.Lusid.Model.ComplianceStep

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComplianceStepType** | **string** | Required | . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceStep(
    complianceStepType: "..."  // required — . The available values are: FilterStep, GroupByStep, GroupFilterStep, BranchStep, RecombineStep, CheckStep, PercentCheckStep
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceStep>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

