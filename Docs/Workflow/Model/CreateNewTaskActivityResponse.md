# Finbourne.Sdk.Workflow.Model.CreateNewTaskActivityResponse

Read only Create new task response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Type** | **string** | Optional | Type of task activity |
| **InitialTrigger** | **string** | Optional | Trigger to supply to all tasks to be made |
| **CorrelationIds** | [List&lt;EventHandlerMapping&gt;](EventHandlerMapping.md) | Optional | The event to correlation ID mappings |
| **TaskFields** | [Dictionary&lt;string, FieldMapping&gt;](FieldMapping.md) | Optional | The event to task field mappings |
| **ScheduleDependentTaskFields** | [Dictionary&lt;string, ScheduledTimeAdjustment&gt;](ScheduledTimeAdjustment.md) | Optional | The Schedule dependent task field mappings. Only relevant if a Finbourne.Workflow.WebApi.Common.Dto.Json.EventHandlers.ScheduleMatchingPattern is specified |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Workflow.Model;

var instance = new CreateNewTaskActivityResponse(
    type: "...",  // optional — Type of task activity
    initialTrigger: "...",  // optional — Trigger to supply to all tasks to be made
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
var instance = JsonConvert.DeserializeObject<CreateNewTaskActivityResponse>(json);
```

- [EventHandlerMapping](EventHandlerMapping.md) — used in `CorrelationIds`
- [FieldMapping](FieldMapping.md) — used in `TaskFields`
- [ScheduledTimeAdjustment](ScheduledTimeAdjustment.md) — used in `ScheduleDependentTaskFields`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

