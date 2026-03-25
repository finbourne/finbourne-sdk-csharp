# Finbourne.Sdk.Workflow.Model.Task

Defines a Task created based on a Task Definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **Guid** | Required | The unique id for this Task |
| **TaskDefinitionId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **TaskDefinitionVersion** | [TaskDefinitionVersion](TaskDefinitionVersion.md) | Required | *No description available.* |
| **TaskDefinitionDisplayName** | **string** | Required | The display name of the Task Definition used by this Task |
| **State** | **string** | Required | Current State |
| **UltimateParentTask** | [TaskSummary](TaskSummary.md) | Required | *No description available.* |
| **ParentTask** | [TaskSummary](TaskSummary.md) | Optional | *No description available.* |
| **ChildTasks** | [List&lt;TaskSummary&gt;](TaskSummary.md) | Optional | This Task&#39;s child tasks |
| **CorrelationIds** | **List&lt;string&gt;** | Optional | User-provided ID used to link entities and tasks |
| **VarVersion** | [VersionInfo](VersionInfo.md) | Optional | *No description available.* |
| **TerminalState** | **bool** | Required | True if no onward transitions are possible |
| **AsAtLastTransition** | **DateTimeOffset?** | Optional | Last Transition timestamp |
| **Fields** | [List&lt;TaskInstanceField&gt;](TaskInstanceField.md) | Optional | Fields and their latest values - should correspond with the Task Definition field schema |
| **StackingKey** | **string** | Optional | The key used to determine which stack to add the Task to |
| **Stack** | [Stack](Stack.md) | Optional | *No description available.* |
| **ActionLogIdCreated** | **Guid?** | Optional | The Id of the Action that created this Task |
| **ActionLogIdModified** | **Guid?** | Optional | The Id of the Action that last modified this Task |
| **ActionLogIdSubmitted** | **Guid?** | Optional | The Id of the last Action submitted by this Task |
| **HierarchicalPosition** | **string** | Optional | The hierarchical position of this Task: UltimateParent, IntermediateParent, Child, or Standalone |
| **CompletionStatus** | **string** | Optional | The completion status of this Task: NotStarted, InProgress, or Completed |
| **OpenDuration** | **long?** | Optional | Duration in seconds since the Task was created. If the Task is Completed, this is the duration from creation to the last transition. |
| **OpenDurationSinceLastUpdate** | **long?** | Optional | Duration in seconds since the Task was last updated. 0 if the Task is Completed. |
| **OpenDurationSinceLastTransition** | **long?** | Optional | Duration in seconds since the Task last transitioned. 0 if the Task is Completed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new Task(
    id: "...",  // required — The unique id for this Task
    taskDefinitionId: new ResourceId(...),  // required
    taskDefinitionVersion: new TaskDefinitionVersion(...),  // required
    taskDefinitionDisplayName: "...",  // required — The display name of the Task Definition used by this Task
    state: "...",  // required — Current State
    ultimateParentTask: new TaskSummary(...),  // required
    parentTask: new TaskSummary(...),  // optional
    childTasks: new List<TaskSummary>(),  // optional — This Task&#39;s child tasks
    correlationIds: ,  // optional — User-provided ID used to link entities and tasks
    varVersion: new VersionInfo(...),  // optional
    terminalState: true,  // required — True if no onward transitions are possible
    asAtLastTransition: DateTimeOffset.Now,  // optional — Last Transition timestamp
    fields: new List<TaskInstanceField>(),  // optional — Fields and their latest values - should correspond with the Task Definition field schema
    stackingKey: "...",  // optional — The key used to determine which stack to add the Task to
    stack: new Stack(...),  // optional
    actionLogIdCreated: "...",  // optional — The Id of the Action that created this Task
    actionLogIdModified: "...",  // optional — The Id of the Action that last modified this Task
    actionLogIdSubmitted: "...",  // optional — The Id of the last Action submitted by this Task
    hierarchicalPosition: "...",  // optional — The hierarchical position of this Task: UltimateParent, IntermediateParent, Child, or Standalone
    completionStatus: "...",  // optional — The completion status of this Task: NotStarted, InProgress, or Completed
    openDuration: 0L,  // optional — Duration in seconds since the Task was created. If the Task is Completed, this is the duration from creation to the last transition.
    openDurationSinceLastUpdate: 0L,  // optional — Duration in seconds since the Task was last updated. 0 if the Task is Completed.
    openDurationSinceLastTransition: 0L  // optional — Duration in seconds since the Task last transitioned. 0 if the Task is Completed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Task>(json);
```

- [ResourceId](ResourceId.md)
- [TaskDefinitionVersion](TaskDefinitionVersion.md)
- [TaskSummary](TaskSummary.md)
- [TaskSummary](TaskSummary.md)
- [TaskSummary](TaskSummary.md) — used in `ChildTasks`
- [VersionInfo](VersionInfo.md)
- [TaskInstanceField](TaskInstanceField.md) — used in `Fields`
- [Stack](Stack.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

