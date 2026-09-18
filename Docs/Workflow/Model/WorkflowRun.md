# Finbourne.Sdk.Workflow.Model.WorkflowRun

Information about the run of the Workflow that created this Task, inherited from the root/ultimate parent Task.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **int** | Required | The id of this run of the Workflow. Assigned once, when the run is instantiated. |
| **AsAtCreated** | **DateTimeOffset** | Required | The version.asAtCreated of the root/ultimate parent Task of this run. |
| **CompletionStatus** | **string** | Required | The completion status of the root/ultimate parent Task of this run: NotStarted, InProgress, or Completed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new WorkflowRun(
    id: 0,  // required — The id of this run of the Workflow. Assigned once, when the run is instantiated.
    asAtCreated: DateTimeOffset.Now,  // required — The version.asAtCreated of the root/ultimate parent Task of this run.
    completionStatus: "..."  // required — The completion status of the root/ultimate parent Task of this run: NotStarted, InProgress, or Completed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WorkflowRun>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

