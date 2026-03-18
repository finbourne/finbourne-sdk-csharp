# Finbourne.Sdk.Lusid.Model.IntermediateComplianceStepRequest

> **Inherits from:** [ComplianceStepRequest](ComplianceStepRequest.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComplianceStepTypeRequest** | **string** | Required | . The available values are: FilterStepRequest, GroupByStepRequest, GroupFilterStepRequest, BranchStepRequest, CheckStepRequest, PercentCheckStepRequest *(inherited)* |
| **Label** | **string** | Required | The label of the compliance step |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IntermediateComplianceStepRequest(
    label: "..."  // required — The label of the compliance step
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntermediateComplianceStepRequest>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

