# Finbourne.Sdk.Lusid.Model.FilterStepRequest

> **Inherits from:** [ComplianceStepRequest](ComplianceStepRequest.md)

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Label** | **string** | Required | The label of the compliance step |
| **ComplianceStepTypeRequest** | **string** | Required | . The available values are: FilterStepRequest, GroupByStepRequest, GroupFilterStepRequest, BranchStepRequest, CheckStepRequest, PercentCheckStepRequest Default: `ComplianceStepTypeRequestEnum.FilterStepRequest` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FilterStepRequest(
    label: "...",  // required — The label of the compliance step
    complianceStepTypeRequest: "..."  // required — . The available values are: FilterStepRequest, GroupByStepRequest, GroupFilterStepRequest, BranchStepRequest, CheckStepRequest, PercentCheckStepRequest
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FilterStepRequest>(json);
```




[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

