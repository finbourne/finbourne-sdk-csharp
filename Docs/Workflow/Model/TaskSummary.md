# Finbourne.Sdk.Workflow.Model.TaskSummary

Summary of a Task created based on a Task Definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **Guid** | Required | The unique id for this Task |
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaskDefinitionVersion** | [TaskDefinitionVersion](TaskDefinitionVersion.md) | Required | *No description available.* |
| **TaskDefinitionDisplayName** | **string** | Required | The display name of the Task Definition used by this Task |
| **State** | **string** | Required | Current State |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new TaskSummary(
    id: "...",  // required — The unique id for this Task
    taskDefinitionId: new ResourceId(...),  // required
    taskDefinitionVersion: new TaskDefinitionVersion(...),  // required
    taskDefinitionDisplayName: "...",  // required — The display name of the Task Definition used by this Task
    state: "..."  // required — Current State
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaskSummary>(json);
```

- [ResourceId](ResourceId.md)
- [TaskDefinitionVersion](TaskDefinitionVersion.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

