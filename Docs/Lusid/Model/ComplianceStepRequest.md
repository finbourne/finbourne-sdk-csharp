# Finbourne.Sdk.Lusid.Model.ComplianceStepRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ComplianceStepTypeRequest** | **string** | Required | . The available values are: FilterStepRequest, GroupByStepRequest, GroupFilterStepRequest, BranchStepRequest, CheckStepRequest, PercentCheckStepRequest |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceStepRequest(
    complianceStepTypeRequest: "..."  // required — . The available values are: FilterStepRequest, GroupByStepRequest, GroupFilterStepRequest, BranchStepRequest, CheckStepRequest, PercentCheckStepRequest
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceStepRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

