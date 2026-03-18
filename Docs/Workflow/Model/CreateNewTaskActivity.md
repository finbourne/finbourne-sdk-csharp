# Finbourne.Sdk.Workflow.Model.CreateNewTaskActivity

Define a Task Activity that creates a new task
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InitialTrigger** | **string** | Optional | Trigger to supply to all tasks to be made |
| **Type** | **string** | Required | The type of task activity |
| **CorrelationIds** | [List&lt;EventHandlerMapping&gt;](EventHandlerMapping.md) | Optional | The event to correlation ID mappings |
| **TaskFields** | [Dictionary&lt;string, FieldMapping&gt;](FieldMapping.md) | Optional | The event to task field mappings |
| **ScheduleDependentTaskFields** | [Dictionary&lt;string, ScheduledTimeAdjustment&gt;](ScheduledTimeAdjustment.md) | Optional | The Schedule dependent task field mappings. Only relevant if a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern is specified |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateNewTaskActivity(
    initialTrigger: "...",  // optional — Trigger to supply to all tasks to be made
    type: "...",  // required — The type of task activity
    correlationIds: new List<EventHandlerMapping>(),  // optional — The event to correlation ID mappings
    taskFields: new FieldMapping(...),  // optional — The event to task field mappings
    scheduleDependentTaskFields: new ScheduledTimeAdjustment(...)  // optional — The Schedule dependent task field mappings. Only relevant if a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern is specified
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateNewTaskActivity>(json);
```

- [EventHandlerMapping](EventHandlerMapping.md) — used in `CorrelationIds`
- [FieldMapping](FieldMapping.md) — used in `TaskFields`
- [ScheduledTimeAdjustment](ScheduledTimeAdjustment.md) — used in `ScheduleDependentTaskFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

