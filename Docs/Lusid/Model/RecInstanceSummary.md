# Finbourne.Sdk.Lusid.Model.RecInstanceSummary

A lightweight view of the rec instance, nested on each result set. It carries the instance-level  status, which is how a result set surfaces the instance's running/locked state to the dashboard.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [RecInstanceId](RecInstanceId.md) | Required | *No description available.* |
| **RecDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AsAtInstantiated** | **DateTimeOffset** | Required | The asAt datetime at which the instance was first created. |
| **WorkflowTaskInstantiated** | [RecWorkflowTask](RecWorkflowTask.md) | Optional | *No description available.* |
| **Status** | **string** | Required | The instance-level lifecycle rollup. Available values: Running, Failures, ReviewAndApproval, AllApproved, Locked. |
| **AsAtLocked** | **DateTimeOffset?** | Optional | The wall-clock time the lock action was performed. Null when the instance has not been locked. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecInstanceSummary(
    id: new RecInstanceId(...),  // required
    recDefinitionId: new ResourceId(...),  // required
    asAtInstantiated: DateTimeOffset.Now,  // required — The asAt datetime at which the instance was first created.
    workflowTaskInstantiated: new RecWorkflowTask(...),  // optional
    status: "...",  // required — The instance-level lifecycle rollup. Available values: Running, Failures, ReviewAndApproval, AllApproved, Locked.
    asAtLocked: DateTimeOffset.Now  // optional — The wall-clock time the lock action was performed. Null when the instance has not been locked.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecInstanceSummary>(json);
```


## Related Models

- [RecInstanceId](RecInstanceId.md)
- [ResourceId](ResourceId.md)
- [RecWorkflowTask](RecWorkflowTask.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

