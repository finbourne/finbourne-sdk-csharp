# Finbourne.Sdk.Workflow.Model.UpdateMatchingTasksActivity

Update all matching tasks based on filter matches
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Required | The type of task activity |
| **Filter** | **string** | Optional | The filter that matches on existing tasks |
| **Trigger** | **string** | Required | Trigger to supply to all tasks that have been matched |
| **CorrelationIds** | [List&lt;EventHandlerMapping&gt;](EventHandlerMapping.md) | Optional | The event to correlation ID mappings |
| **TaskFields** | [Dictionary&lt;string, FieldMapping&gt;](FieldMapping.md) | Optional | The event to task field mappings |
| **ScheduleDependentTaskFields** | [Dictionary&lt;string, ScheduledTimeAdjustment&gt;](ScheduledTimeAdjustment.md) | Optional | The Schedule dependent task field mappings. Only relevant if a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern is specified |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new UpdateMatchingTasksActivity(
    type: "...",  // required — The type of task activity
    filter: "...",  // optional — The filter that matches on existing tasks
    trigger: "...",  // required — Trigger to supply to all tasks that have been matched
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
var instance = JsonConvert.DeserializeObject<UpdateMatchingTasksActivity>(json);
```

- [EventHandlerMapping](EventHandlerMapping.md) — used in `CorrelationIds`
- [FieldMapping](FieldMapping.md) — used in `TaskFields`
- [ScheduledTimeAdjustment](ScheduledTimeAdjustment.md) — used in `ScheduleDependentTaskFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

