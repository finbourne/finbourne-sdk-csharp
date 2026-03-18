# Finbourne.Sdk.Workflow.Model.BatchUpdateTasksRequest

A request to update multiple Tasks
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UpdateTasks** | [List&lt;UpdateTaskWithIdAndTriggerRequest&gt;](UpdateTaskWithIdAndTriggerRequest.md) | Optional | A Dictionary of task IDs to UpdateTaskRequest |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new BatchUpdateTasksRequest(
    updateTasks: new List<UpdateTaskWithIdAndTriggerRequest>()  // optional — A Dictionary of task IDs to UpdateTaskRequest
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BatchUpdateTasksRequest>(json);
```


## Related Models

- [UpdateTaskWithIdAndTriggerRequest](UpdateTaskWithIdAndTriggerRequest.md) — used in `UpdateTasks`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

